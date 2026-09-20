# Research: isManuallyApproved and Project review (issue #3)

Question (rdavila00/freeCodeCamp#3): what does `isManuallyApproved` do today, who sets it, how are certification project submissions stored/validated/displayed, and what must a Teacher Project review (approved / needs-changes / rejected, with Feedback, Class members only, no effect on certification) avoid colliding with?

Line numbers are as of this branch (based on `main` at `7b91ccb287`).

## 1. `isManuallyApproved` today

**Storage.** Field on the embedded composite type `CompletedChallenge`, inside `user.completedChallenges` (an embedded MongoDB array, not a separate collection): `api/prisma/schema.prisma:21-30` (`isManuallyApproved Boolean? // Undefined` at :27; `solution` :28, `githubLink` :25, `files` :24). Mirrored in hand-written TS types at `api/src/utils/common-challenge-functions.ts:64-73` and `api/src/utils/normalize.ts:164-175`.

**Who sets it: one write site, and only to `false`.**
- `api/src/routes/protected/challenge.ts:1359-1362` (`postModernChallengeCompleted`): when `challengeType === challengeTypes.multifileCertProject` (value 14, `packages/shared/src/config/challenge-types.ts:16`) it sets `completedChallenge.isManuallyApproved = false` and `user.needsModeration = true`.
- Nothing in this repo ever sets it to `true`. A repo-wide grep finds it only in the schema, that write, the TS types, response schemas and tests. Approval is presumably done out-of-band (moderator tooling or DB edit). This is an inference from absence; confirm with maintainers.
- `user.needsModeration` (`schema.prisma:160`) is the paired flag. It is persisted via `needsModeration: needsModeration || undefined` (`common-challenge-functions.ts:223-225`; a TODO there notes its tri-state problem) and selected at `challenge.ts:62`. Nothing else in `api/src` or `client/src` reads it.

**Who reads it: nobody with logic.** It is only passed through to clients in response schemas:
- session user: `api/src/schemas/user/get-session-user.ts:41`
- public profile: `api/src/schemas/users/get-public-profile.ts:38`
- certificate claim/verify responses: `api/src/schemas/certificate/certificate-verify.ts:48,81,119`

The client has no references to `isManuallyApproved`. Certificate claiming does not check it (section 3). Today it is a dormant moderation marker, not a gate.

**Tests pinning it:** `api/src/routes/protected/challenge.test.ts:1236-1243, 1300-1307, 1449-1456, 1517-1524` (multifile cert project completion yields `isManuallyApproved: false` and `needsModeration: true`), `api/src/utils/normalize.test.ts:120`, `api/src/routes/helpers/challenge-helpers.test.ts:32`.

## 2. How certification project submissions are stored, validated, displayed

Two submission shapes.

**A. URL projects** (`POST /project-completed`, `api/src/routes/protected/challenge.ts:78-193`)
- Schema `api/src/schemas/challenge/project-completed.ts:4-11`: `id` ObjectId, optional `challengeType`, `solution` string (max 1024), optional `githubLink`.
- Validation (`challenge.ts:104-141`): backEndProject requires `solution` and a valid URL `githubLink`; other types require `solution` to be a URL if present (403 "That does not appear to be a valid challenge submission."). Exam ids rejected (:99-107). CodeRoad/CodeAlly/freeCodeCampOS cert projects require prerequisite completion (:143-160).
- `challengeType` is trusted from the client (TODO at :90-91).
- Stored as `{challengeType, solution, githubLink, id, completedDate}` (:162-168) via `updateUserChallengeData`.
- Client builds the body in `client/src/templates/Challenges/redux/completion-epic.js:167-175`; `githubLink` is only sent for backEndProject.

**B. Multifile/code cert projects** (`POST /modern-challenge-completed`, `challenge.ts:260-302`, handler `postModernChallengeCompleted` :1330-1381)
- The client submitter type for multifileCertProject is `'tests'` (`packages/shared/src/config/challenge-types.ts:161`), so there is no separate project endpoint.
- `files` are kept only for "savable" challenge ids; otherwise omitted (`common-challenge-functions.ts:135-152`, picking `contents,key,index,name,path,ext`). `challengeType` is persisted only for the cert-project id lists (`challenge.ts:1364-1370`).
- Sets `isManuallyApproved=false` and `needsModeration=true` (above).

**Resubmission overwrites.** In `updateUserChallengeData` (`common-challenge-functions.ts:135-215`), if the challenge is already completed the whole array element is replaced by the new submission, keeping only the old `completedDate` (`finalChallenge` ~:166-171; `.map` replacement ~:177-183). Any field on that element not re-supplied by the submit path (a future review field, or a previously `true` `isManuallyApproved`) is wiped on resubmit. `needsModeration` is never reset to false by the API.

**Normalisation/response.** `normalizeChallenges` (`api/src/utils/normalize.ts:178-`) strips nulls and normalises date/type. Response schemas type `solution`, `githubLink`, `files`, `isManuallyApproved` as optional (e.g. `certificate-verify.ts:33-48`).

**Display.**
- `client/src/utils/solution-display-type.ts:14-35` picks a mode from `solution/githubLink/challengeFiles/challengeType/examResults`: `showMultifileProjectSolution`, `showUserCode`, `showProjectAndGithubLinks`, `showProjectLink`, `showExamResults`, `noSolutionToDisplay`, `none`.
- Rendered by `client/src/components/solution-display-widget/index.tsx` (links at :57-67, :143-153), used in the settings certification table (`client/src/components/settings/certification.tsx:17,189-193,294`) and the public profile timeline (`client/src/components/profile/components/time-line.tsx:23,204-223`, code modal via `SolutionViewer`).
- Public profile exposure of solutions is governed by profile privacy (`ProfileUI`, `schema.prisma:68`, and `get-public-profile.ts`); a review needs its own visibility rule.

## 3. Certification does not depend on approval

Claiming (`api/src/routes/protected/certificate.ts:228-340`) only checks that every required challenge id exists in `completedChallenges` (`hasCompletedTests`, :63-69; call :305-309), then pushes a new `{id, completedDate, challengeType}` entry for the cert itself (:337-343) and sets the cert boolean. `isManuallyApproved` and `needsModeration` are not consulted. A Teacher review stored anywhere that does not alter `completedChallenges` membership therefore cannot affect certification, by construction.

## 4. What a Teacher Project review must avoid colliding with

1. **Do not reuse `isManuallyApproved`.** It is a boolean (cannot express approved/needs-changes/rejected plus Feedback), is written `false` for every multifile cert project submission, is exposed on public-profile and session-user payloads, and is tied to a site-staff moderation process (paired with `needsModeration`). Overloading it risks false "approved" states and leaks teacher opinions publicly.
2. **Do not store the review inside `user.completedChallenges[]`.** Elements are fully replaced on resubmission, are read by certificate logic, are serialised into public-profile/verify responses, and are typed in hand-maintained TS types (`common-challenge-functions.ts:64`, `normalize.ts:164`) plus typebox schemas in three places. A separate Prisma `model` (keyed by student, challenge id, class, reviewer; status enum; feedback) fits existing conventions (`schema.prisma:200-270` use `model` for non-user data; embedded `type`s are for user sub-documents).
3. **Resubmission semantics.** `completedDate` is preserved on resubmit (~:166-171), so it does NOT identify a submission version. Decide whether a resubmit supersedes/invalidates a review, and consider recording the reviewed `solution`/`githubLink`/file hash on the review.
4. **`needsModeration` is site-wide staff state.** Teacher actions must not set or clear it.
5. **Submission shapes differ.** URL projects store `solution`/`githubLink`; multifile store `files`; some legacy records store code in `solution` (comment at `solution-display-type.ts:26-27`). Only savable ids retain `files`, so verify a project's submission is reviewable before promising review of code.
6. **Client-trusted `challengeType`** (`challenge.ts:90-91`): derive which challenges are reviewable from server-side curriculum data, not the request.
7. **Authorisation.** Reading another user's solution today goes through profile privacy. Class-member-only access is a new path; put endpoints under protected routes and check Class membership rather than relying on public-profile visibility.
8. **Naming.** "Project review" must not be confused with `challengeTypes.review` (`completion-epic.js:295`), an unrelated challenge type, nor with `needsModeration`.

## 5. Open questions / limits
- Where `isManuallyApproved = true` is set in production is not visible in this repo (likely external tooling); not verified.
- `CONTEXT.md` (mentioned in the brief) is untracked in the main checkout and absent from this worktree, so domain terms were not cross-checked against it.
- Research only; no application code changed.
