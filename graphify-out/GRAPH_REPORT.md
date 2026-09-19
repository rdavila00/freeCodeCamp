# Graph Report - freeCodeCamp  (2026-09-19)

## Corpus Check
- Large corpus: 701 files · ~528,490 words. Semantic extraction will be expensive (many Claude tokens). Consider running on a subfolder.

## Summary
- 4906 nodes · 12690 edges · 193 communities (175 shown, 18 thin omitted)
- Extraction: 95% EXTRACTED · 5% INFERRED · 0% AMBIGUOUS · INFERRED: 650 edges (avg confidence: 0.85)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- Settings Pages
- Chapter Icons
- API Route Tests
- Client Dependencies
- Client Package Manifest
- API App Setup
- Flash Messages
- Settings Actions
- Daily Challenge Types
- App Mount & Email Tests
- UI Primitives
- Fill-in-the-Blank Steps
- Challenge Node Types
- Prisma & Fastify
- Daily Challenge Routes
- Company Logos
- Profile Certifications
- Landing & 404 Pages
- Challenge Routes
- Donation Forms
- Dev Auth Plugin
- API Package Manifest
- Email Options
- CodeAlly & Tokens
- Client Dev Dependencies
- Analytics Events
- Settings Tests
- Exam Environment Routes
- Icons & Buttons
- Help & Socrates Icons
- Community 30
- Community 31
- Community 32
- Community 33
- Community 34
- Community 35
- Community 36
- Community 37
- Community 38
- Community 39
- Community 40
- Community 41
- Community 42
- Community 43
- Community 44
- Community 45
- Community 46
- Community 47
- Community 48
- Community 49
- Community 50
- Community 51
- Community 52
- Community 53
- Community 54
- Community 55
- Community 56
- Community 57
- Community 58
- Community 59
- Community 60
- Community 61
- Community 62
- Community 63
- Community 64
- Community 65
- Community 66
- Community 67
- Community 68
- Community 69
- Community 70
- Community 71
- Community 72
- Community 73
- Community 74
- Community 75
- Community 76
- Community 77
- Community 78
- Community 79
- Community 80
- Community 81
- Community 82
- Community 83
- Community 84
- Community 85
- Community 86
- Community 87
- Community 88
- Community 89
- Community 90
- Community 91
- Community 92
- Community 93
- Community 94
- Community 95
- Community 96
- Community 97
- Community 98
- Community 99
- Community 100
- Community 101
- Community 102
- Community 103
- Community 104
- Community 105
- Community 106
- Community 107
- Community 108
- Community 109
- Community 110
- Community 111
- Community 112
- Community 113
- Community 114
- Community 115
- Community 116
- Community 117
- Community 118
- Community 119
- Community 120
- Community 121
- Community 122
- Community 123
- Community 124
- Community 125
- Community 126
- Community 127
- Community 128
- Community 129
- Community 130
- Community 131
- Community 132
- Community 133
- Community 134
- Community 135
- Community 136
- Community 137
- Community 138
- Community 139
- Community 140
- Community 141
- Community 142
- Community 143
- Community 144
- Community 145
- Community 146
- Community 147
- Community 148
- Community 149
- Community 150
- Community 151
- Community 152
- Community 153
- Community 154
- Community 155
- Community 156
- Community 157
- Community 158
- Community 159
- Community 160
- Community 161
- Community 162
- Community 163
- Community 164
- Community 165
- Community 166
- Community 167
- Community 168
- Community 169
- Community 170
- Community 171
- Community 172
- Community 173
- Community 174
- Community 175
- Community 176
- Community 177
- Community 178
- Community 179
- Community 180
- Community 181
- Community 182
- Community 183
- Community 184
- Community 185
- Community 186
- Community 187
- Community 188
- Community 189

## God Nodes (most connected - your core abstractions)
1. `react` - 435 edges
2. `react-i18next` - 208 edges
3. `@freecodecamp/ui` - 146 edges
4. `react-redux` - 124 edges
5. `FlashMessages` - 98 edges
6. `@testing-library/react` - 96 edges
7. `@fastify/type-provider-typebox` - 86 edges
8. `createFlashMessage()` - 78 edges
9. `reselect` - 60 edges
10. `createStore()` - 57 edges

## Surprising Connections (you probably didn't know these)
- `mapDispatchToProps()` --indirect_call--> `createFlashMessage()`  [INFERRED]
  client/src/client-only-routes/show-certification.tsx → client/src/components/Flash/redux/index.ts
- `Benefits()` --calls--> `callGA()`  [EXTRACTED]
  client/src/components/Donation/donation-modal-body.tsx → client/src/analytics/call-ga.ts
- `DonationFormRow()` --calls--> `callGA()`  [EXTRACTED]
  client/src/components/Donation/multi-tier-donation-form.tsx → client/src/analytics/call-ga.ts
- `postChargeSaga()` --indirect_call--> `callGA()`  [INFERRED]
  client/src/redux/donation-saga.js → client/src/analytics/call-ga.ts
- `executeChallengeSaga()` --indirect_call--> `callGA()`  [INFERRED]
  client/src/templates/Challenges/redux/execute-challenge-saga.js → client/src/analytics/call-ga.ts

## Import Cycles
- None detected.

## Communities (193 total, 18 thin omitted)

### Community 0 - "Settings Pages"
Cohesion: 0.04
Nodes (75): mapDispatchToProps, mapStateToProps, TODO: update types for actions, ShowSettingsProps, mapDispatchToProps, mapStateToProps, ShowUpdateEmailProps, mapDispatchToProps (+67 more)

### Community 1 - "Chapter Icons"
Cohesion: 0.04
Nodes (42): ChapterIcon(), ChapterIconProps, iconMap, A1ChineseIcon(), A1SpanishIcon(), A2ChineseIcon(), A2EnglishIcon(), A2SpanishIcon() (+34 more)

### Community 2 - "API Route Tests"
Cohesion: 0.04
Nodes (76): NOTE: message may not necessarily be a part of the api compatability guarantee., post(), TODO: use matcher for date near now, TODO: Enable, once these are no longer "upcoming"., TODO: create a mock challenges array specific to these tests., TODO: Revisit this test after deciding if we need/want to fetch the, chargeStripeCardReqBody, chargeStripeReqBody (+68 more)

### Community 3 - "Client Dependencies"
Cohesion: 0.02
Nodes (96): dependencies, algoliasearch, assert, babel-plugin-preval, babel-plugin-prismjs, @babel/plugin-proposal-export-default-from, @babel/plugin-proposal-function-bind, @babel/plugin-transform-runtime (+88 more)

### Community 4 - "Client Package Manifest"
Cohesion: 0.02
Nodes (87): author, bugs, url, description, homepage, date-fns, date-fns-tz, dotenv (+79 more)

### Community 5 - "API App Setup"
Cohesion: 0.04
Nodes (61): ajv, build(), buildOptions, FastifyInstanceWithTypeProvider, TODO: Old API returns 403s for failed validation. We now return 400 (default)…, TODO: bounce unauthed requests before checking CSRF token. This will, TODO: The route should not handle its own AuthZ, shouldSendLog (+53 more)

### Community 6 - "Flash Messages"
Cohesion: 0.03
Nodes (79): FlashMessages, AccountDeleted, AddNameSuccess, AlreadyClaimed, CertClaimSuccess, CertificateMissing, CertsClaimable, CertsPrivate (+71 more)

### Community 7 - "Settings Actions"
Cohesion: 0.07
Nodes (73): createFlashMessage(), CertificationSettings(), ProjectsFor(), LegacyFullStack(), deleteAccount, resetMyEditorLayout, resetMyEditorLayoutComplete, resetMyEditorLayoutError (+65 more)

### Community 8 - "Daily Challenge Types"
Cohesion: 0.07
Nodes (59): DailyCodingChallengeLanguageData, DailyCodingChallengeNode, DailyCodingChallengePageContext, PageContext, SavedChallenge, SavedChallengeFiles, client_src_templates_challenges_classic_classic, mergeChallengeFiles() (+51 more)

### Community 9 - "App Mount & Email Tests"
Cohesion: 0.04
Nodes (52): AppMountNotifier(), AppMountNotifierProps, appMount, SurveyResponse, SurveyResults, isProcessingSelector(), msUsernameSelector(), updateMyKeyboardShortcuts (+44 more)

### Community 10 - "UI Primitives"
Cohesion: 0.04
Nodes (48): Caret(), DropDown(), GreenNotCompleted(), GreenNotCompletedProps, mapStateToProps, ProfilePrivacy, ProfilePrivacyComponent(), submitNewProfileSettings() (+40 more)

### Community 11 - "Fill-in-the-Blank Steps"
Cohesion: 0.05
Nodes (51): FillInTheBlank, FillInTheBlankInputType, RdbStep1InstructionsProps, RdbStep2Instructions(), RdbStep2InstructionsProps, Assignments(), AssignmentsProps, Props (+43 more)

### Community 12 - "Challenge Node Types"
Cohesion: 0.04
Nodes (59): ClosedCaptionsIcon(), AllChallengeNode, BilibiliIds, BlockBasedSuperBlockStructure, CertTest, CharacterPosition, Characters, Dialogue (+51 more)

### Community 13 - "Prisma & Fastify"
Cohesion: 0.06
Nodes (43): extendClient(), fastify, FastifyInstance, prismaPlugin, TODO: It would be nice to split this up into multiple update functions,, TODO: Multiple extended clients can be used for different restrictions (e.g.…, TODO: Could be used to add other _easily forgotten_ fields like…, NOTE: raw ops are untouched, as it is meant to be a direct passthrough to… (+35 more)

### Community 14 - "Daily Challenge Routes"
Cohesion: 0.06
Nodes (51): dailyCodingChallengeRoutes(), all, challengeLanguage, dailyCodingChallenge, date, day, manyChallengesResponse, month (+43 more)

### Community 15 - "Company Logos"
Cohesion: 0.05
Nodes (42): AlibabaLogo(), AmazonLogo(), AppleLogo(), AsSeenInText(), GoogleLogo(), client_src_assets_images_components_index_alibabalogo, client_src_assets_images_components_index_amazonlogo, client_src_assets_images_components_index_applelogo (+34 more)

### Community 16 - "Profile Certifications"
Cohesion: 0.05
Nodes (41): CertButtonProps, Certificates(), CertificationProps, ExperienceDisplay(), ExperienceDisplayProps, formatDate(), sampleExperience, CalendarData (+33 more)

### Community 17 - "Landing & 404 Pages"
Cohesion: 0.07
Nodes (34): client_src_assets_images_footer_ads_apple_store_badge, client_src_assets_images_footer_ads_google_play_badge, CardUpdateAlertHandler(), CardUpdateAlertHandlerProps, DonateCompletionProps, client_src_components_footer_footer, bottomLinks, Footer() (+26 more)

### Community 18 - "Challenge Routes"
Cohesion: 0.06
Nodes (51): challengeRoutes(), challengeTokenRoutes(), JwtPayload, postCoderoadChallengeCompleted(), postDailyCodingChallengeCompleted(), postModernChallengeCompleted(), postSaveChallenge(), TODO: log error if msTrophyId not found? (+43 more)

### Community 19 - "Donation Forms"
Cohesion: 0.06
Nodes (43): PatreonLogo(), DonateCompletion(), DonateFormComponentState, DonateFormProps, mapDispatchToProps, mapStateToProps, PostCharge, client_src_components_donation_donation (+35 more)

### Community 20 - "Dev Auth Plugin"
Cohesion: 0.06
Nodes (37): devAuth(), handleRedirects(), signInSchema, trimTrailingSlash(), fastify, FastifyInstance, plugin(), cors() (+29 more)

### Community 21 - "API Package Manifest"
Cohesion: 0.04
Nodes (50): author, bugs, url, description, engines, node, npm, homepage (+42 more)

### Community 22 - "Email Options"
Cohesion: 0.07
Nodes (38): mapStateToProps(), mapStateToProps(), EmailListOptInProps, EmailOptions(), EmailOptionsProps, EmailSignUpAlertProps, mapDispatchToProps, mapStateToProps() (+30 more)

### Community 23 - "CodeAlly & Tokens"
Cohesion: 0.07
Nodes (38): updateUserToken, partiallyCompletedChallengesSelector(), userTokenSelector(), client_src_templates_challenges_codeally_codeally, CodespacesInstructions(), LocalInstructions(), ChallengeWithId, isCodeAllyProjectCompleted() (+30 more)

### Community 24 - "Client Dev Dependencies"
Cohesion: 0.04
Nodes (49): devDependencies, autoprefixer, babel-plugin-macros, @babel/plugin-syntax-dynamic-import, core-js, dotenv, eslint, eslint-plugin-flowtype (+41 more)

### Community 25 - "Analytics Events"
Cohesion: 0.05
Nodes (41): callGA(), CallSocratesEvent, ChallengeSubmitButtonClickEvent, ChallengeTestCodeButtonClickEvent, DonationEvent, DonationEventAction, DonationRelatedEvent, DonationRelatedEventAction (+33 more)

### Community 26 - "Settings Tests"
Cohesion: 0.06
Nodes (33): baseUser, Intro(), loggedInProps, loggedOutProps, renderWithRedux(), renderWithStore(), renderExperience(), client_src_components_profile_components_fixtures_completed_challenges (+25 more)

### Community 27 - "Exam Environment Routes"
Cohesion: 0.08
Nodes (45): examEnvironmentOpenRoutes(), examEnvironmentValidatedTokenRoutes(), getExamAttemptHandler(), getExamAttemptsByExamIdHandler(), getExamAttemptsHandler(), getExamChallenge(), getExams(), JwtPayload (+37 more)

### Community 28 - "Icons & Buttons"
Cohesion: 0.07
Nodes (28): CalendarIcon(), DailyCodingChallengeIcon(), LinkButton(), ArchivedWarning(), CatalogItem(), CatalogItemProps, getMonthDayUsCentral(), DailyCodingChallengeNotFound() (+20 more)

### Community 29 - "Help & Socrates Icons"
Cohesion: 0.08
Nodes (30): MAX_MOBILE_WIDTH, Help(), OutlineLightbulb(), Socrates(), saveChallenge, CertificateNode, SuperBlockStructure, curriculumData (+22 more)

### Community 30 - "Community 30"
Cohesion: 0.07
Nodes (40): completedExamChallenge, completedExamChallengeAllCorrect, completedExamChallengeOneCorrect, completedExamChallengeTwoCorrect, completedTrophyChallenges, examChallengeId, examJson, ExamSubmission (+32 more)

### Community 31 - "Community 31"
Cohesion: 0.08
Nodes (34): ERRORS, assertIsString(), auth(), getAuthedUser(), handleExamEnvironmentTokenAuth(), AuthResult, fastify, FastifyInstance (+26 more)

### Community 32 - "Community 32"
Cohesion: 0.07
Nodes (21): classroomGetUserDataSchema, classroomGetUserIdSchema, deprecatedEndpoints, chargeStripe, resubscribe, unsubscribe, sentryPostEvent, confirmEmail (+13 more)

### Community 33 - "Community 33"
Cohesion: 0.10
Nodes (29): actionTypes, ns, serverStatusChange, setTheme, createAppMountSaga(), parseMessagesSaga(), delay(), failedUpdateEpic() (+21 more)

### Community 34 - "Community 34"
Cohesion: 0.07
Nodes (39): ExamTokenResponse, GenerateExamResponseWithData, PostData, postUpdate$(), addDonation(), ApiUser, ApiUserResponse, Cert (+31 more)

### Community 35 - "Community 35"
Cohesion: 0.11
Nodes (32): nullableFlags, splitUser(), examEnvironmentTokenHandler(), getExamEnvironmentToken(), TODO: `findUnique` once db migration forces unique usernames, TODO: DRY this (the creation of the response body) and, userGetRoutes(), blockedUserAgentParts (+24 more)

### Community 36 - "Community 36"
Cohesion: 0.06
Nodes (30): client_i18n_locales_english_intro, client_i18n_locales_english_links, client_i18n_locales_english_meta_tags, client_i18n_locales_english_translations, ShowProjectLinks(), user, Language, LanguagePair (+22 more)

### Community 37 - "Community 37"
Cohesion: 0.08
Nodes (28): client_src_components_helpers_index_loader, MissingPrerequisites(), useAllPrerequisiteChallenges(), Attempts(), AttemptsProps, ExamTokenControls(), getLatest(), getRecommendedOs() (+20 more)

### Community 38 - "Community 38"
Cohesion: 0.07
Nodes (21): Reset(), SupporterBadgeEmblem(), SupporterBadge(), TopContributorBadgeEmblem(), LoginProps, mapStateToProps, DonateButtonProps, mapDispatchToProps (+13 more)

### Community 39 - "Community 39"
Cohesion: 0.09
Nodes (22): auth0Client, Auth0ErrorSchema, fastify, FastifyInstance, TODO: use a schema to validate the query params., findOrCreateUser(), TODO: handle the case where there are multiple users with the same email., donateRoutes() (+14 more)

### Community 40 - "Community 40"
Cohesion: 0.13
Nodes (31): FormFields(), FormFieldsProps, FormOptions, FormValues, fromLong(), isLoopback(), isPrivate(), isV6Format() (+23 more)

### Community 41 - "Community 41"
Cohesion: 0.08
Nodes (34): Block, BlockBasedCurriculumIntros, CatalogCourse, catalogDashedNames, ChapterBasedCurriculumIntros, Curriculum, CurriculumIntros, CurriculumProps (+26 more)

### Community 42 - "Community 42"
Cohesion: 0.09
Nodes (20): certSlug, certificateVerify, modernChallengeCompleted, msTrophyChallengeCompleted, projectCompleted, saveChallenge, submitQuizAttempt, chargeStripeCard (+12 more)

### Community 43 - "Community 43"
Cohesion: 0.08
Nodes (26): CertsToProjects, CertificationIcon(), initSolutionState, mapDispatchToProps, ShowProjectLinksProps, SolutionState, client_src_components_layouts_project_links, localeCode (+18 more)

### Community 44 - "Community 44"
Cohesion: 0.10
Nodes (31): ShowUser(), handleSubmit(), NavLinks(), clearExamResults, deleteUserToken, fetchProfileForUserComplete, fetchProfileForUserError, fetchUserComplete (+23 more)

### Community 45 - "Community 45"
Cohesion: 0.09
Nodes (30): SearchBar, initialState, isSearchBarFocusedSelector(), isSearchDropdownEnabledSelector(), ns, reducer, searchQuerySelector(), toggleSearchDropdown (+22 more)

### Community 46 - "Community 46"
Cohesion: 0.09
Nodes (28): connector, easing, ProgressInner(), ProgressInnerProps, useIsInViewport(), mapDispatchToProps, mapStateToProps, ProgressProps (+20 more)

### Community 47 - "Community 47"
Cohesion: 0.12
Nodes (33): disableBuildOnError, executeChallengeComplete, initLogs, logsToConsole, setProjectPreviewLoading, updateConsole, updateLogs, updateTests (+25 more)

### Community 48 - "Community 48"
Cohesion: 0.06
Nodes (35): dependencies, ajv, ajv-formats, bson, date-fns, date-fns-tz, dotenv, fast-uri (+27 more)

### Community 49 - "Community 49"
Cohesion: 0.09
Nodes (23): CommunityAchievementsText(), CtaText(), CurrentInitiativesText(), DonationFaqText(), FaqItemProps, GetSupporterBenefitsText(), SupportBenefitsText(), ThankYouMessage() (+15 more)

### Community 50 - "Community 50"
Cohesion: 0.09
Nodes (30): ExamResultsModal(), ExamResultsModalProps, mapDispatchToProps, mapStateToProps(), stopExam, GeneratedExamQuestion, GeneratedExamResults, PrerequisiteChallenge (+22 more)

### Community 51 - "Community 51"
Cohesion: 0.07
Nodes (31): Dimensions, ResizeProps, DescriptionZoneState, EditableRegionState, EditorProps, EditorState, loadMonacoJson(), loadMonacoTypescript() (+23 more)

### Community 52 - "Community 52"
Cohesion: 0.10
Nodes (26): DesktopLayout(), mapDispatchToProps, mapStateToProps, Pane, reflexProps, mapDispatchToProps, mapStateToProps, MobileLayoutState (+18 more)

### Community 53 - "Community 53"
Cohesion: 0.08
Nodes (23): client_src_assets_images_donation_bear_animation, client_src_assets_images_new_bear_animation, client_src_assets_images_supporter_bear, client_src_assets_images_supporter_bear_block, Benefits(), DonationModalBody(), DonationModalBodyProps, DonateModal() (+15 more)

### Community 54 - "Community 54"
Cohesion: 0.09
Nodes (23): client_src_assets_images_ribbon, Cert, CertificateDisplay(), CertificateDisplayProps, DonationSection(), localeCode, mapDispatchToProps(), ShareCertBtns() (+15 more)

### Community 55 - "Community 55"
Cohesion: 0.12
Nodes (21): ShowSettings(), CertificationLayout, CertificationProps, mapDispatchToProps, mapStateToProps, deleteUserTokenComplete, fetchUser, hardGoTo (+13 more)

### Community 56 - "Community 56"
Cohesion: 0.08
Nodes (20): baseProps, loggedInProps, loggedOutProps, mockT, store, baseUser, MockImage, baseUser (+12 more)

### Community 57 - "Community 57"
Cohesion: 0.15
Nodes (27): openDonationModal, postChargeComplete, postChargeError, postChargeProcessing, preventSectionDonationRequests, updateCardError, updateCardRedirecting, createDonationSaga() (+19 more)

### Community 58 - "Community 58"
Cohesion: 0.10
Nodes (22): actionTypes, ns, updateMyEmailComplete, updateMyEmailError, defaultFetchState, initialState, reducer, sagas (+14 more)

### Community 59 - "Community 59"
Cohesion: 0.10
Nodes (22): createInitialEditorState(), defineMonacoThemes(), Editor(), addContentChangeListener(), addWidgetsToRegions(), createBreadcrumb(), createDescription(), focusIfTargetEditor() (+14 more)

### Community 60 - "Community 60"
Cohesion: 0.15
Nodes (25): DROPPED_LOG_MESSAGE_PREFIXES, DROPPED_LOG_MESSAGES, DROPPED_LOG_ROUTES, hashUnit(), isAuditLog(), isDroppedLogMessage(), makeShouldSendLog(), makeTracesSampler() (+17 more)

### Community 61 - "Community 61"
Cohesion: 0.10
Nodes (19): RedFail(), GreenPass(), GreenPassProps, Initial(), ChallengeTest, ChallengeTitleProps, baseProps, DispatchProps (+11 more)

### Community 62 - "Community 62"
Cohesion: 0.11
Nodes (22): propsForOnlySolution, store, Archive(), daysInMonth, previousDate, renderArchive(), todayUsCentral, [year, month, day] (+14 more)

### Community 63 - "Community 63"
Cohesion: 0.09
Nodes (19): configPath, destDir, env, envPath, filesToCopy, srcDir, createCdnUrl(), download() (+11 more)

### Community 64 - "Community 64"
Cohesion: 0.09
Nodes (24): EX_SMALL_VIEWPORT_HEIGHT, GITHUB_LOCATION, SEARCH_EXPOSED_WIDTH, DefaultLayout(), DefaultLayoutProps, DispatchProps, mapStateToProps, StateProps (+16 more)

### Community 65 - "Community 65"
Cohesion: 0.16
Nodes (18): generateGithubLink(), epics, rootEpic, actionTypes, ns, createQuestionEpic(), editableRegionsToMarkdown(), filesToMarkdown() (+10 more)

### Community 66 - "Community 66"
Cohesion: 0.12
Nodes (22): ExactMatchFeedbackProps, alignWords(), compareTexts(), Comparison, ComparisonResult, ComparisonWord, Extra, matchTexts() (+14 more)

### Community 67 - "Community 67"
Cohesion: 0.15
Nodes (19): cookieUpdate(), Options, cookies(), api_src_plugins_cookies_cookieserializeoptions, fastify, FastifyReply, sign(), unsign() (+11 more)

### Community 68 - "Community 68"
Cohesion: 0.10
Nodes (22): filterDeprecated(), generateRandomExam(), getRandomElement(), DbAnswerJoi, DbPrerequisitesJoi, DbQuestionJoi, examFromDbSchema, examResultsSchema (+14 more)

### Community 69 - "Community 69"
Cohesion: 0.11
Nodes (13): ToggleCheck(), KeyboardShortcutsProps, KeyboardShortcutsSettings(), MiscSettingsProps, ScrollbarWidthSettings(), SocratesProps, SocratesSettings(), SoundProps (+5 more)

### Community 70 - "Community 70"
Cohesion: 0.10
Nodes (22): actRE, alertListeners, createContent(), createFrame(), createHeader(), createRunnerScript(), getContentDocument(), helperVersion (+14 more)

### Community 71 - "Community 71"
Cohesion: 0.13
Nodes (20): client_src_templates_challenges_classic_xterm_original, TODO: prevent user from moving cursor outside the current input line and, registerServiceWorker(), XtermTerminal(), createTerminal(), Code, getPythonWorker(), interruptCodeExecution() (+12 more)

### Community 72 - "Community 72"
Cohesion: 0.13
Nodes (18): isRestricted(), ALLOWED_DOMAINS_MAP, commonImageExtensions, getWaitMessage(), getWaitPeriod(), isPictureWithProtocol(), isValidPictureUrl(), TODO: combine emailVerifyTTL and emailAuthLinkTTL? I'm not sure why (+10 more)

### Community 73 - "Community 73"
Cohesion: 0.17
Nodes (23): TimelineInnerProps, TimelineProps, Props, ChallengeMeta, ChallengeNode, CompletedChallenge, Test, ShowCodeAllyProps (+15 more)

### Community 74 - "Community 74"
Cohesion: 0.14
Nodes (21): linkMsUsername, setIsProcessing, setMsUsername, submitSurvey, submitSurveyComplete, unlinkMsUsername, createMsUsernameSaga(), linkMsUsernameSaga() (+13 more)

### Community 75 - "Community 75"
Cohesion: 0.12
Nodes (21): ChallengeData, HotkeysProps, mapDispatchToProps, mapStateToProps, TODO: 'enter' on its own also disables HotKeys, but default behaviour, detectOS(), isDismissedFor30Days(), MobileAppModal() (+13 more)

### Community 76 - "Community 76"
Cohesion: 0.17
Nodes (19): fullStackCertificateIds, getFallbackFullStackDate(), isKnownCertSlug(), fullStackChallenges, assertTestsExist(), CertLookup, createCertLookup(), getCertBySlug() (+11 more)

### Community 77 - "Community 77"
Cohesion: 0.12
Nodes (12): FreeCodeCampLogo(), InputReset(), Magnifier(), MenuButton(), MenuButtonProps, SearchBarOptimized, UniversalNavProps, client_src_components_helpers_index_skeletonsprite (+4 more)

### Community 78 - "Community 78"
Cohesion: 0.09
Nodes (16): baseUser, renderWithStore(), renderWithUser(), TestUser, defaultProfileUI, createTestStore(), examResults, renderExamResultsModal() (+8 more)

### Community 79 - "Community 79"
Cohesion: 0.19
Nodes (21): allowSectionDonationRequests, setRenderStartTime, submitComplete, updateComplete, updateFailed, submitChallengeComplete, submitChallengeError, completionEpic() (+13 more)

### Community 80 - "Community 80"
Cohesion: 0.11
Nodes (18): FlashActionTypes, CreateFlashMessage, RemoveFlashMessage, flashMessageSelector(), initialState, reducer(), ReducerBase, ReducerPayload (+10 more)

### Community 81 - "Community 81"
Cohesion: 0.11
Nodes (20): backend, classic, codeAlly, createChallengePages(), exam, examDownload, fillInTheBlank, freeCodeCampOs (+12 more)

### Community 82 - "Community 82"
Cohesion: 0.10
Nodes (21): devDependencies, dotenv-cli, eslint, eslint-plugin-jsdoc, @freecodecamp/curriculum, @freecodecamp/eslint-config, @freecodecamp/shared, msw (+13 more)

### Community 83 - "Community 83"
Cohesion: 0.12
Nodes (13): client_config_cert_and_project_map_livecerts, Block, SuperBlockIntro(), client_src_templates_introduction_intro, resetExpansion, toggleBlock, ChallengeNode, FetchState (+5 more)

### Community 84 - "Community 84"
Cohesion: 0.19
Nodes (20): byId(), createEmptyExperienceItem(), Experience(), ExperienceField, ExperienceItemProps, ExperienceProps, ExperienceSettings(), ExperienceValidation (+12 more)

### Community 85 - "Community 85"
Cohesion: 0.14
Nodes (13): client_src_components_sidebar_panel_index_useactiveheading, client_src_components_sidebar_panel_index_usestickyscrolloffset, SidebarPanel, SidebarPanelItemProps, SidebarPanelProps, useActiveHeading(), useStickyScrollOffset(), buildContentOutlineItems() (+5 more)

### Community 86 - "Community 86"
Cohesion: 0.12
Nodes (7): store, wrapPageElement, createRedirect(), stripe, browser-cookies, @gatsbyjs/reach-router, @stripe/stripe-js

### Community 87 - "Community 87"
Cohesion: 0.17
Nodes (19): client_i18n_locales_english_motivation, findExtraneousKeys(), findMissingKeys(), flattenAnObject(), introSchemaKeys, introSchemaValidation(), linksSchemaKeys, linksSchemaValidation() (+11 more)

### Community 88 - "Community 88"
Cohesion: 0.10
Nodes (20): scripts, build, clean, copy:scripts, create:env, create:external-curriculum, create:i18n, create:search-placeholder (+12 more)

### Community 89 - "Community 89"
Cohesion: 0.15
Nodes (15): NoHitsSuggestion(), NoHitsSuggestionProps, SearchBarFooter(), SearchBarFooterProps, algoliaIndices, { clientLocale }, newsIndex, searchPageUrl (+7 more)

### Community 90 - "Community 90"
Cohesion: 0.18
Nodes (14): Share(), ShareTemplate(), ShareProps, ShareRedirectProps, blueSkyData, facebookData, hashtag, nextLine (+6 more)

### Community 91 - "Community 91"
Cohesion: 0.13
Nodes (17): clearEnvExam(), config, exam, examAttempt, examAttemptSansSubmissionTime, examEnvironmentChallenge, examId, generatedExam (+9 more)

### Community 92 - "Community 92"
Cohesion: 0.15
Nodes (11): CapIcon(), CommunityIcon(), CurriculumIcon(), DumbbellIcon(), FreeIcon(), SuperBlockIcon(), Benefits(), BenefitsItem (+3 more)

### Community 93 - "Community 93"
Cohesion: 0.13
Nodes (11): Loader(), LoaderProps, ResetProgressModal(), ResetProgressModalProps, Status, defaultProps, mockOnHide, mockOnResetComplete (+3 more)

### Community 94 - "Community 94"
Cohesion: 0.18
Nodes (14): EditorTabs, EditorTabsProps, mapDispatchToProps, mapStateToProps, mapStateToProps, MultifileEditor(), MultifileEditorProps, TODO: the tabs mess up the rendering (scroll doesn't work properly and (+6 more)

### Community 95 - "Community 95"
Cohesion: 0.21
Nodes (10): examEnvironmentGetExamChallenge, examEnvAttempt, examEnvironmentGetExamAttempt, examEnvironmentGetExamAttempts, examEnvironmentGetExamAttemptsByExamId, examEnvironmentPostExamAttempt, examEnvironmentPostExamGeneratedExam, examEnvironmentExams (+2 more)

### Community 96 - "Community 96"
Cohesion: 0.16
Nodes (16): AchievementsError, canSubmitCodeRoadCertProject(), decodeBase64(), decodeFiles(), encodeBase64(), getMSProfile(), MSProfileError, MSProfileSuccess (+8 more)

### Community 97 - "Community 97"
Cohesion: 0.22
Nodes (16): ChallengeFailedEvent, saveChallengeComplete, ChallengeFiles, createSaveChallengeSaga(), saveChallengeSaga(), executeCancellableChallengeSaga(), challengeDataSelector(), postSaveChallenge() (+8 more)

### Community 98 - "Community 98"
Cohesion: 0.19
Nodes (14): client_src_assets_images_freecodecamp_404, client_src_components_fourohfour_404, FourOhFour(), CURRENT_CHALLENGE_KEY, updateSuccessMessage, createCurrentChallengeSaga(), currentChallengeSaga(), updateSuccessMessageSaga() (+6 more)

### Community 99 - "Community 99"
Cohesion: 0.19
Nodes (17): answerCurrentQuestion(), answerCurrentQuestionAndGoNext(), completedExamRequirements, data, examTitle, expectExamLandingPage(), expectQuestionNumber(), expectStartedExamHeader() (+9 more)

### Community 100 - "Community 100"
Cohesion: 0.12
Nodes (10): coderoadChallengeCompleted, exam, TODO: Standardize error responses - e.g. { type, message }, createStripePaymentIntent, updateMyAbout, updateMyEmail, updateMyPrivacyTerms, updateMySocials (+2 more)

### Community 101 - "Community 101"
Cohesion: 0.12
Nodes (12): allCerts, allStandardCerts, CurrentCert, currentCerts, FilteredCert, fullstackCert, LegacyCert, legacyCerts (+4 more)

### Community 102 - "Community 102"
Cohesion: 0.15
Nodes (12): LanguageGlobe(), createLanguageRedirect(), LanguageList(), LanguageListProps, locales, mapDispatchToProps, LandingTop(), HTML() (+4 more)

### Community 103 - "Community 103"
Cohesion: 0.15
Nodes (6): DangerZone(), DangerZoneProps, DeleteModal(), DeleteModalProps, ResetModal(), ResetModalProps

### Community 104 - "Community 104"
Cohesion: 0.23
Nodes (14): createSessionCompletedChallengesSaga(), SessionCompletedChallengesSaga(), AfterSave, BeforeSave, CURRENT_COUNT_KEY, getCurrentCount(), getSavedCount(), getSessionChallengeData() (+6 more)

### Community 105 - "Community 105"
Cohesion: 0.12
Nodes (16): completedChallengesIds, currentBlockIds, fakeCompletedChallengesIds, mockBuildEnabledSelector, mockChallengeDataSelector, mockChallengeMetaSelector, mockChallengeTestsSelector, mockCompletedChallengesIdsSelector (+8 more)

### Community 106 - "Community 106"
Cohesion: 0.15
Nodes (12): CustomMonacoEditor(), MonacoEditor, InteractiveEditor(), InteractiveFile, Props, TODO: Consider making active file first file in markdown, htmlFile, jsFile (+4 more)

### Community 107 - "Community 107"
Cohesion: 0.12
Nodes (16): compilerOptions, allowJs, emitDecoratorMetadata, esModuleInterop, experimentalDecorators, forceConsistentCasingInFileNames, jsx, lib (+8 more)

### Community 108 - "Community 108"
Cohesion: 0.23
Nodes (12): isSocratesOnSelector(), askSocratesComplete, askSocratesError, askSocratesSaga(), createAskSocratesSaga(), hasContent(), serverErrorKeyMap, baseState (+4 more)

### Community 109 - "Community 109"
Cohesion: 0.16
Nodes (10): AuthOrProfile(), avatarHasClass(), Component, createTestStore(), defaultUser, mockUseMediaQuery, profileNavItem(), renderHeader() (+2 more)

### Community 110 - "Community 110"
Cohesion: 0.15
Nodes (12): baseConfig, baseLanguageOptions, packages_eslint_config_base, packages_eslint_config_base_config, packages_eslint_config_base_configreact, packages_eslint_config_base_configtestinglibrary, packages_eslint_config_base_configtypechecked, packages_eslint_config_base_jsfiles (+4 more)

### Community 111 - "Community 111"
Cohesion: 0.13
Nodes (13): mockChallenges, todayDateParam, todaysChallenge, todayUsCentral, todayUtcMidnight, tomorrowDateParam, tomorrowsChallenge, tomorrowUtcMidnight (+5 more)

### Community 112 - "Community 112"
Cohesion: 0.16
Nodes (14): config, _, blockCreator, buildChallenges(), {
  getBlockCreator,
  getSuperblocks,
  superBlockToFilename
}, getBlockMetadata(), {
  getContentDir,
  getBlockStructure,
  getSuperblockStructure,
  CURRICULUM_DIR
}, { getSuperOrder } (+6 more)

### Community 113 - "Community 113"
Cohesion: 0.28
Nodes (9): errorHandlerSaga(), ErrorData, HandledError, handledErrorSymbol, isHandledError(), unwrapHandledError(), wrapHandledError(), reportClientSideError() (+1 more)

### Community 114 - "Community 114"
Cohesion: 0.22
Nodes (14): savedChallengesSelector(), noStoredCodeFound, clearCodeEpic(), getCode(), getLegacyCode(), isFilesAllPoly(), legacyPrefixes, legacyToFile() (+6 more)

### Community 115 - "Community 115"
Cohesion: 0.19
Nodes (10): attachContentWidgetEvents(), dispatchVerticalScrollWheel(), findHorizontalScroller(), handleVerticalScroll(), InteractiveTouchState, isInteractiveTarget(), TouchGestureMode, TouchGestureState (+2 more)

### Community 116 - "Community 116"
Cohesion: 0.14
Nodes (14): scripts, build, clean, develop, exam-env:seed, exam-env:test, lint, postinstall (+6 more)

### Community 117 - "Community 117"
Cohesion: 0.14
Nodes (11): chargeStripeReqBody, createStripePaymentIntentReqBody, mockAttachPaymentMethod, mockCheckoutSessionCreate, mockCustomerCreate, mockCustomerUpdate, mockSubCreate, mockSubRetrieve (+3 more)

### Community 118 - "Community 118"
Cohesion: 0.15
Nodes (8): { createSuperBlockIntroPages }, env, MonacoWebpackPlugin, onCreateWebpackConfig(), client_utils_gatsby_index_createsuperblockintropages, envData, home_ramond_projects_proto_codecamp_freecodecamp_client_config_env_json, monaco-editor-webpack-plugin

### Community 119 - "Community 119"
Cohesion: 0.23
Nodes (9): onRenderBody(), store, wrapPageElement, webmanifestComponents, isMathJaxAllowed(), mathJaxSrc, getheadTagComponents(), getPostBodyComponents() (+1 more)

### Community 120 - "Community 120"
Cohesion: 0.16
Nodes (11): __dirname, __filename, Intro, SuperBlockInfo, browserScriptDist, destJsDir, srcJsDir, getCurriculum() (+3 more)

### Community 121 - "Community 121"
Cohesion: 0.21
Nodes (10): FourOhFourPage(), Certification(), layoutSelector(), LayoutSelectorProps, challengePageContext, getComponentNameAndProps(), NameAndProps, TODO: rather than testing which props passed from layoutSelector to the (+2 more)

### Community 122 - "Community 122"
Cohesion: 0.15
Nodes (12): ChallengeNode, consoleSpy, createLocation(), createPageProps(), i18nSpy, mockT, Scenario, scenarios (+4 more)

### Community 123 - "Community 123"
Cohesion: 0.25
Nodes (10): baseChallenge, bothLinks, invalidGithubLink, legacySolution, multifilePythonSolution, multifileSolution, onlyGithubLink, onlySolution (+2 more)

### Community 124 - "Community 124"
Cohesion: 0.22
Nodes (9): postSentryEventHandler(), sentryRoutes(), base64URLEncode(), challenge, Result, UpdateReplyType, UpdateReqType, verifier (+1 more)

### Community 125 - "Community 125"
Cohesion: 0.22
Nodes (9): client_config_growthbook_features_default, { clientLocale, growthbookUri }, GrowthBookWrapper, mapStateToProps, parseGrowthBookUrl(), StateProps, UserAttributes, Window (+1 more)

### Community 126 - "Community 126"
Cohesion: 0.21
Nodes (9): currentInitImpl(), init(), MinimalUser, mockInit, mockSetAttributes, mockSetPayload, setAttributes(), setPayload() (+1 more)

### Community 127 - "Community 127"
Cohesion: 0.24
Nodes (12): Hooks, BuildChallengeData, challengeHasPreview(), getDocumentTitle(), TODO: Fully type BuildChallengeData, updatePreview(), updateProjectPreview(), Context (+4 more)

### Community 128 - "Community 128"
Cohesion: 0.15
Nodes (12): env, outputs, env, extends, //, $schema, env, outputs (+4 more)

### Community 129 - "Community 129"
Cohesion: 0.20
Nodes (8): examChallengeCompleted, updateMyProfileUI, examResults, experience, profileUI, getSessionUser, languages, getPublicProfile

### Community 130 - "Community 130"
Cohesion: 0.17
Nodes (11): compilerOptions, allowJs, esModuleInterop, forceConsistentCasingInFileNames, module, noEmit, noUncheckedIndexedAccess, resolveJsonModule (+3 more)

### Community 131 - "Community 131"
Cohesion: 0.23
Nodes (9): makeMapStateToProps(), mapDispatchToProps, ShowProfileOrFourOhFour(), ShowProfileOrFourOhFourProps, Socials, ProfilePageProps, fetchProfileForUser, userProfileFetchStateSelector() (+1 more)

### Community 132 - "Community 132"
Cohesion: 0.18
Nodes (10): alwaysDisabledFunding, ButtonsProps, ButtonStyle, getScriptOptions(), mapStateToProps, PaypalButton(), PaypalButtonProps, {
  paypalClientId,
  deploymentEnv
} (+2 more)

### Community 133 - "Community 133"
Cohesion: 0.27
Nodes (8): convertToHanzi(), normalize(), PinyinToHanziInput(), PinyinToHanziInputProps, convertToPinyinWithTones(), PinyinToneInput(), PinyinToneInputProps, pinyin-tone

### Community 134 - "Community 134"
Cohesion: 0.22
Nodes (8): MicrosoftLogo(), ExamNav(), client_src_components_header_header, connector, mapStateToProps, Props, PropsFromRedux, examInProgressSelector()

### Community 135 - "Community 135"
Cohesion: 0.25
Nodes (6): TimelineInner(), renderCompletion(), renderViewButton(), viewExamResults(), viewProject(), viewSolution()

### Community 136 - "Community 136"
Cohesion: 0.24
Nodes (3): UsernameSettings, submitNewUsername, validateUsername

### Community 137 - "Community 137"
Cohesion: 0.18
Nodes (10): @freecodecamp/loop-protect, @freecodecamp/strip-comments, monaco-editor/esm/vs/base/common/platform.js, *.png, sha-1, *.svg, @types/lodash-es, @types/react-redux (+2 more)

### Community 138 - "Community 138"
Cohesion: 0.20
Nodes (9): DailyCodingChallengeLanguages, ActionRow(), ActionRowProps, ClassicLayoutProps, InteractiveEditorProps, ReviewChallengeProps, ReviewWithInteractiveEditorProps, DesktopLayoutProps (+1 more)

### Community 139 - "Community 139"
Cohesion: 0.20
Nodes (6): baseChallengeMeta, baseProps, envMock, mockSubmitChallenge, passingTests, mockCurriculumData

### Community 140 - "Community 140"
Cohesion: 0.29
Nodes (9): DAILY_LIMITS, getDailyLimit(), hasContent(), isFetchNetworkError(), isUpstreamTimeout(), NETWORK_ERROR_CODES, socratesRoutes(), SOCRATES_API_KEY (+1 more)

### Community 141 - "Community 141"
Cohesion: 0.20
Nodes (9): compilerOptions, noEmit, outDir, rootDir, sourceMap, exclude, extends, include (+1 more)

### Community 142 - "Community 142"
Cohesion: 0.20
Nodes (9): env, extends, //, $schema, tasks, build, test, env (+1 more)

### Community 143 - "Community 143"
Cohesion: 0.29
Nodes (8): client_src_components_flash_flash, Flash(), handleClose(), FlashProps, TODO: Standardize the value of `type`., removeFlashMessage(), mapDispatchToProps(), FlashState

### Community 144 - "Community 144"
Cohesion: 0.31
Nodes (5): CodeAllyDown(), LegacyLinks(), LegacyLinksProps, isExamCert(), isRelationalDbCert()

### Community 145 - "Community 145"
Cohesion: 0.22
Nodes (9): FetchState, LearnLayout(), LearnLayoutProps, mapDispatchToProps, mapStateToProps, client_src_components_layouts_prism, client_src_components_layouts_prism_night, tryToShowDonationModal (+1 more)

### Community 146 - "Community 146"
Cohesion: 0.36
Nodes (7): SearchHits(), SearchHitsProps, Suggestion(), SuggestionProps, Hit, instantsearch.js, react-instantsearch

### Community 147 - "Community 147"
Cohesion: 0.31
Nodes (5): ChallengesRedirect(), ChallengesRedirectProps, Challenges(), toLearnPath(), ToLearnPathKwargs

### Community 148 - "Community 148"
Cohesion: 0.33
Nodes (6): VersionData, VersionData, VersionEndpoint(), getVersion(), getVersionObject(), VersionInfo

### Community 149 - "Community 149"
Cohesion: 0.24
Nodes (8): client_src_redux_prop_types_challengefile, SavedChallengeFile, cssChallenge, htmlChallenge, jsChallenge, savedCssChallenge, savedHtmlChallenge, savedJsChallenge

### Community 150 - "Community 150"
Cohesion: 0.31
Nodes (9): answerSurveyQuestions(), expectedSurveyResults, expectSubmitButtonDisabled(), expectSubmitButtonEnabled(), getSubmitButton(), openSurvey(), ResizeObserverMock, setupSurveyAlert() (+1 more)

### Community 151 - "Community 151"
Cohesion: 0.29
Nodes (8): alertKeyByVariant, alertVariants, createPreviewAlertListener(), parsePreviewAlert(), PreviewAlertMessage, previewAlertMessageType, PreviewAlertVariant, validMessage

### Community 152 - "Community 152"
Cohesion: 0.20
Nodes (9): availableSuperBlocksSchema, availableSuperBlocksValidator(), blockBasedCurriculumSchema, blockSchema, catalogSchema, catalogValidator(), chapterBasedCurriculumSchema, slugRE (+1 more)

### Community 153 - "Community 153"
Cohesion: 0.28
Nodes (5): ShowUpdateEmail(), handleSubmit(), EmailSettings(), handleSubmit(), updateMyEmail

### Community 155 - "Community 155"
Cohesion: 0.28
Nodes (6): StagingWarningModal(), ResizeObserverMockInstance, mockUseSelector, ResizeObserverMockInstance, react-dom, store

### Community 156 - "Community 156"
Cohesion: 0.25
Nodes (6): createFramer(), listenForPreviewAlerts(), mountFrame(), updateProxyConsole(), format(), util

### Community 157 - "Community 157"
Cohesion: 0.42
Nodes (7): buildExtCurriculumDataV2(), buildBlockBasedCurriculum(), buildChallengeFiles(), buildChapterBasedCurriculum(), parseCurriculumData(), writeToFile(), catalogCourses()

### Community 158 - "Community 158"
Cohesion: 0.25
Nodes (4): MONGOHQ_URL, prisma, prisma, NOTE: This is not strictly true. E.g. If a `Boolean` becomes an `Int`, Prisma…

### Community 159 - "Community 159"
Cohesion: 0.39
Nodes (4): DefaultAvatar(), AvatarRenderer(), AvatarRendererProps, borderColorPicker()

### Community 160 - "Community 160"
Cohesion: 0.32
Nodes (3): ShowUnsubscribed(), ShowUnsubscribedProps, UnsubscribedWithIdProps

### Community 161 - "Community 161"
Cohesion: 0.29
Nodes (7): calculateStreaks(), Stats(), multipleEntriesInOneDay, oldStreakCalendar, props, recentStreakCalendar, twoStreakCalendar

### Community 162 - "Community 162"
Cohesion: 0.25
Nodes (6): challengeMounted, initialState, previewMounted, TODO: figure out why silentRun is necessary. Without it, we get timeout, resetChallenge, redux-saga-test-plan

### Community 163 - "Community 163"
Cohesion: 0.43
Nodes (5): configure(), initializeMathJax(), mathJaxScriptLoader(), superBlocksWithMathJax, scriptLoader()

### Community 164 - "Community 164"
Cohesion: 0.25
Nodes (8): SuperBlockStage, Chinese, Core, English, Extra, Legacy, Professional, Spanish

### Community 165 - "Community 165"
Cohesion: 0.38
Nodes (4): devAnalyticsId, prodAnalyticsId, gtmId, react-gtm-module

### Community 166 - "Community 166"
Cohesion: 0.29
Nodes (6): graphql, Link, navigate, StaticQuery, useStaticQuery, withPrefix

### Community 167 - "Community 167"
Cohesion: 0.43
Nodes (4): getChildren(), hasChildren(), renderNodes(), Trans()

### Community 168 - "Community 168"
Cohesion: 0.29
Nodes (3): MobileLayout, mockProps, renderMobileLayout()

### Community 169 - "Community 169"
Cohesion: 0.40
Nodes (3): OfflineWarning(), timeout(), OfflineWarningProps

### Community 170 - "Community 170"
Cohesion: 0.40
Nodes (3): createDefaultHelpModalProps(), renderHelpModal(), ResizeObserverMockInstance

### Community 171 - "Community 171"
Cohesion: 0.40
Nodes (4): Preview(), PreviewProps, mainPreviewId, previewSandbox

### Community 177 - "Community 177"
Cohesion: 0.50
Nodes (3): askSocrates, socratesHint, usageFields

### Community 178 - "Community 178"
Cohesion: 0.67
Nodes (4): handleDocumentNotFound(), initMainFrame(), initProjectPreviewFrame(), waitForFrame()

### Community 182 - "Community 182"
Cohesion: 0.67
Nodes (3): engines, node, pnpm

### Community 183 - "Community 183"
Cohesion: 0.67
Nodes (3): repository, type, url

## Knowledge Gaps
- **1542 isolated node(s):** `config`, `navigate`, `graphql`, `Link`, `withPrefix` (+1537 more)
  These have ≤1 connection - possible missing edges or undocumented components. (Counts symbols only; 2046 node(s) total have ≤1 connection when file, concept and rationale nodes are included.)
- **18 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `react` connect `Chapter Icons` to `Settings Pages`, `Client Package Manifest`, `Daily Challenge Types`, `App Mount & Email Tests`, `UI Primitives`, `Fill-in-the-Blank Steps`, `Challenge Node Types`, `Daily Challenge Routes`, `Company Logos`, `Profile Certifications`, `Landing & 404 Pages`, `Donation Forms`, `Email Options`, `CodeAlly & Tokens`, `Analytics Events`, `Settings Tests`, `Icons & Buttons`, `Help & Socrates Icons`, `Community 36`, `Community 37`, `Community 38`, `Community 40`, `Community 43`, `Community 45`, `Community 46`, `Community 49`, `Community 50`, `Community 51`, `Community 52`, `Community 53`, `Community 54`, `Community 55`, `Community 56`, `Community 61`, `Community 62`, `Community 64`, `Community 66`, `Community 69`, `Community 71`, `Community 73`, `Community 75`, `Community 77`, `Community 78`, `Community 83`, `Community 84`, `Community 85`, `Community 86`, `Community 89`, `Community 90`, `Community 92`, `Community 93`, `Community 94`, `Community 98`, `Community 99`, `Community 102`, `Community 103`, `Community 105`, `Community 106`, `Community 109`, `Community 119`, `Community 121`, `Community 122`, `Community 125`, `Community 126`, `Community 131`, `Community 132`, `Community 133`, `Community 134`, `Community 138`, `Community 139`, `Community 143`, `Community 144`, `Community 145`, `Community 146`, `Community 147`, `Community 148`, `Community 150`, `Community 155`, `Community 159`, `Community 160`, `Community 161`, `Community 166`, `Community 167`, `Community 168`, `Community 169`, `Community 170`, `Community 171`?**
  _High betweenness centrality (0.204) - this node is a cross-community bridge._
- **Why does `react-i18next` connect `Landing & 404 Pages` to `Settings Pages`, `Chapter Icons`, `Client Package Manifest`, `Community 132`, `Community 134`, `Daily Challenge Types`, `App Mount & Email Tests`, `UI Primitives`, `Community 138`, `Fill-in-the-Blank Steps`, `Challenge Node Types`, `Daily Challenge Routes`, `Community 143`, `Community 144`, `Company Logos`, `Profile Certifications`, `Donation Forms`, `Community 146`, `Email Options`, `CodeAlly & Tokens`, `Community 150`, `Analytics Events`, `Settings Tests`, `Community 155`, `Icons & Buttons`, `Help & Socrates Icons`, `Community 159`, `Community 160`, `Community 36`, `Community 37`, `Community 38`, `Community 40`, `Community 169`, `Community 43`, `Community 171`, `Community 45`, `Community 46`, `Community 49`, `Community 50`, `Community 51`, `Community 52`, `Community 53`, `Community 54`, `Community 61`, `Community 64`, `Community 66`, `Community 69`, `Community 71`, `Community 73`, `Community 75`, `Community 77`, `Community 83`, `Community 84`, `Community 86`, `Community 89`, `Community 90`, `Community 92`, `Community 93`, `Community 98`, `Community 99`, `Community 102`, `Community 103`, `Community 109`, `Community 119`?**
  _High betweenness centrality (0.057) - this node is a cross-community bridge._
- **Why does `FlashMessages` connect `Flash Messages` to `Settings Pages`, `Community 97`, `Community 74`, `Company Logos`, `Community 80`, `Community 143`, `Community 50`, `Community 114`, `CodeAlly & Tokens`, `Community 47`, `Community 150`, `Community 55`, `Community 54`?**
  _High betweenness centrality (0.054) - this node is a cross-community bridge._
- **What connects `config`, `navigate`, `graphql` to the rest of the system?**
  _1542 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `Settings Pages` be split into smaller, more focused modules?**
  _Cohesion score 0.03587516087516088 - nodes in this community are weakly interconnected._
- **Should `Chapter Icons` be split into smaller, more focused modules?**
  _Cohesion score 0.03595959595959596 - nodes in this community are weakly interconnected._
- **Should `API Route Tests` be split into smaller, more focused modules?**
  _Cohesion score 0.03728070175438596 - nodes in this community are weakly interconnected._