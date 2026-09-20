# Research: how quizzes work and what scoring can be captured

Answers rdavila00/freeCodeCamp#2. Feeds the teacher/class map (#1). Terms (Learner, Class member, Sharing consent, Assigned item) are from `CONTEXT.md`.
Sources are repo code at commit `15c8e19261` plus the published `@freecodecamp/ui@6.0.1` type declarations. Line numbers are for this branch.

## Summary

1. A quiz is a `challengeType: 8` challenge. Content lives in Markdown, the client picks one of several variants at random, and grading happens entirely in the browser.
2. Completion is recorded by the generic `/modern-challenge-completed` route, which stores only `{id, challengeType, completedDate}`. It carries no score.
3. `QuizAttempt` (`challengeId`, `quizId`, `timestamp`) is written by a separate `POST /submit-quiz-attempt`. **Nothing in `client/` calls that endpoint.** The only references are the API route, its schema, fixtures and tests. So today no quiz attempt appears to be recorded in practice.
4. Score and pass/fail are already computed on the client (`useQuiz` returns `correctAnswerCount` and `grade`; the pass threshold is 90%). Capturing them means sending extra fields and trusting the client. There is no server-side grading.
5. Recommendation: capture only for Class members, and only against Assigned items. Details and caveats are below.

## How quizzes are built

- The challenge type constant is `quiz = 8` (`packages/shared/src/config/challenge-types.ts:10`). Its submit strategy is `'tests'` (`:156`), the same as ordinary modern challenges.
- Content is one Markdown file per quiz block. Example: `curriculum/challenges/english/blocks/quiz-basic-html/66df3b712c41c499e9d31e5b.md`. It has `challengeType: 8` (line 4) and a `# --quizzes--` section holding four `## --quiz--` variants (lines 14, 456, 898, 1376). Each variant has 20 questions, each with text, three distractors and one answer. The description says "at least 18 of the 20" (line 10), which is 90%.
- The Markdown is parsed by `tools/challenge-parser/parser/index.js` into `quizzes[].questions[]`, exposed to the page by GraphQL at `client/src/templates/Challenges/quiz/show.tsx:431-448`.
- A quiz variant has no stable identity. `quizId` is `Math.floor(Math.random() * quizzes.length)` (`show.tsx:141`), a random array index chosen on mount, not stable across content edits.

## How a quiz is taken and graded (client)

All in `client/src/templates/Challenges/quiz/show.tsx`:

- Answers are shuffled per question (`:177`). The correct answer is given value `4` (`:174`) and distractors 1 to 3, so the correct answer is in the client bundle.
- `useQuiz` from `@freecodecamp/ui` does the grading (`:211-229`). Its declaration exposes `validated`, `grade`, `correctAnswerCount`, `passingPercent`, `onSuccess`, `onFailure` (`dist/quiz/use-quiz.d.ts`, `@freecodecamp/ui@6.0.1`). `passingPercent: 90` is hard-coded (`:223`).
- "Finish Quiz" opens a confirmation modal (`:257-263`). Confirming calls `validateAnswers()` and locks the quiz (`:265-269`). The Learner sees `correctAnswerCount` out of total (`:328-334`); nothing stores that number.
- On pass, `onSuccess` opens the completion modal and sets `isPassed` (`:224-227`). On fail, the Learner can only leave (`:296-299`). A retry is a fresh page mount, so it draws a new random variant and new shuffle.

## How a completion is submitted and recorded

- The completion modal dispatches the shared submit flow. `client/src/templates/Challenges/redux/completion-epic.js:255-278` resolves `submitTypes[8] = 'tests'` to `submitModern`.
- For signed-in users, `submitModern` posts to `/encoded/modern-challenge-completed` (`completion-epic.js:153`) with `{id, challengeType}`. Anonymous users skip the server call (`:265-272`).
- API handler: `api/src/routes/protected/challenge.ts:260-300`, which calls `postModernChallengeCompleted`. It stores a `CompletedChallenge` (`api/prisma/schema.prisma:21-30`): `id`, `challengeType`, `completedDate`, plus file and solution fields quizzes do not use.
- Only a pass reaches this route because Submit-and-go only shows when `isPassed` (`show.tsx:378-395`). The server does not verify that.

## What `QuizAttempt` is and where it is (not) used

- Schema: `api/prisma/schema.prisma:96-100`, embedded array on `user` (`:110`).
- Write path: `POST /submit-quiz-attempt`, `api/src/routes/protected/challenge.ts:915-970`. Body schema: `api/src/schemas/challenge/submit-quiz-attempt.ts:5-12`.
  - One row per challenge. If a row exists for `challengeId` it is overwritten via `updateMany` (`challenge.ts:947-963`), so history is lost.
  - It emits a Sentry counter `quiz.attempt_submitted` (`:966`).
- Read path: `quizAttempts` is returned in the session user (`api/src/routes/protected/user.ts:815`, `api/src/schemas/user/get-session-user.ts:53-59`).
- Callers: none in `client/`. A search for `submit-quiz-attempt` / `quizAttempt` outside `node_modules` finds only API files (schema, `schemas.ts`, routes, fixtures, tests). The endpoint came in `ba70f5d253` ("feat(api): add /submit-quiz-attempt endpoint (#57201)"). Confirm with maintainers whether a client caller is planned or lives elsewhere.

## Where a score and pass/fail could come from

| Value | Source | Trust |
|---|---|---|
| Correct count | `useQuiz().correctAnswerCount` (`show.tsx:215`) | Client-computed |
| Percent | `useQuiz().grade` (declared in `use-quiz.d.ts`; unit not stated there) | Client-computed |
| Total | `quiz.length` (`show.tsx:333`) | Client |
| Pass/fail | `onSuccess` / `onFailure` (`show.tsx:224-228`), threshold 90 | Client |
| Variant | `quizId` random index (`show.tsx:141`) | Client |
| Per-question answers | `quizData[i].selectedAnswer` (`show.tsx:232`) | Client |

Server-side grading is possible in principle, since the Markdown is available at build time, but the server currently receives no answers and answer order is shuffled client-side, so the client would have to send per-question answer identity. That is a larger change than adding a number. A client-reported score is the same trust level as the existing pass gate, which the server already accepts unverified. Whether that is enough for Teacher-facing data is a product decision.

## What capturing would change for every Learner

Assuming the existing route gains score fields and `show.tsx` calls it after `validateAnswers()`:

- **Client:** one extra request per finished quiz for signed-in Learners. It should not block completion.
- **API:** body schema gains e.g. `correctAnswerCount`, `total`, `passed`. Fields must be optional for old clients. The Prisma type `QuizAttempt` gains optional fields because existing embedded documents lack them. The session-user response schema (`get-session-user.ts:53-59`) must be extended or Fastify serialization strips the new fields.
- **Data volume:** `quizAttempts` is embedded on the user and sent in every session-user payload. Moving from one-row-per-challenge to one-row-per-attempt grows it without bound for every user. If history is needed, prefer a separate collection over the embedded array.
- **Privacy:** scores are learning data. Per `CONTEXT.md`, a Teacher may see a Class member's data only under Sharing consent, on Assigned items, from the join date. Universal capture creates records no consent covers, and they must then be excluded from teacher queries by rule.
- **Learner-visible behaviour:** none required. But the overwrite semantic means a failed retry after a pass could replace a stored pass, so "latest" versus "best" must be defined. `completedChallenges` still shows completion.
- **Tests:** `api/src/routes/protected/challenge.test.ts:2861+` and `user.test.ts` assert the current shape and overwrite behaviour and would need updates.

## All Learners or only Class members?

**Recommendation: capture score data only for Class members, scoped to Assigned items.**

- A Teacher sees activity only on assigned items and only from the join date (`CONTEXT.md`, "Assigned item"). Data captured outside that can never be shown.
- Consent is per Class and revocable. Capturing only where a membership and Sharing consent exist keeps storage aligned with consent.
- Cost: the API must check membership at submit time. A Learner who joins after already taking a quiz has no score for it and must retake. That matches "from the join date onward" but should be accepted explicitly.
- Alternative: capture for everyone and filter at read time. It avoids the join-late gap and gives Learners their own history, but stores data for the whole user base that mostly has no consumer, and needs a retention justification.
- Middle path: keep the small "latest attempt" summary for everyone (the field already exists) and write full history only for Class members.

## Open questions

1. Is the missing client call to `/submit-quiz-attempt` intentional? Confirm before building on it.
2. Is client-reported score acceptable for Teacher views, or is server-side grading required?
3. Per-attempt history or latest only? Teachers likely want attempt count and best/latest score.
4. Should an attempt made before joining ever count toward an Assignment?
5. `quizId` is a positional index. Store a stable variant id or content hash if scores must survive content edits.
6. Confirm the unit and rounding of `useQuiz().grade` in the `@freecodecamp/ui` source (only the `.d.ts` was read).
