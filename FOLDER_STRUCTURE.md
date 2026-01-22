# React Native EdTech App - Folder Structure

## 📁 Complete Project Structure

```
edtech-mobile-app/
│
├── android/                          # Android native code
│   ├── app/
│   │   ├── src/
│   │   │   ├── main/
│   │   │   │   ├── java/com/edtech/
│   │   │   │   │   ├── modules/
│   │   │   │   │   │   ├── TestTimerModule.kt       # Native test timer
│   │   │   │   │   │   ├── AnalyticsModule.kt       # Native analytics
│   │   │   │   │   │   ├── BiometricModule.kt       # Biometric auth
│   │   │   │   │   │   ├── CameraModule.kt          # Advanced camera
│   │   │   │   │   │   └── EncryptionModule.kt      # Secure storage
│   │   │   │   │   ├── services/
│   │   │   │   │   │   ├── TestTimerService.kt      # Background timer
│   │   │   │   │   │   └── SyncService.kt           # Background sync
│   │   │   │   │   ├── workers/
│   │   │   │   │   │   └── SyncWorker.kt            # WorkManager sync
│   │   │   │   │   └── MainApplication.kt
│   │   │   │   └── AndroidManifest.xml
│   │   └── build.gradle
│   └── build.gradle
│
├── ios/                              # iOS native code
│   ├── EdTech/
│   │   ├── Modules/
│   │   │   ├── TestTimerModule.swift           # Native test timer
│   │   │   ├── AnalyticsModule.swift           # Native analytics
│   │   │   ├── BiometricModule.swift           # Face/Touch ID
│   │   │   ├── CameraModule.swift              # Advanced camera
│   │   │   └── EncryptionModule.swift          # Keychain storage
│   │   ├── Services/
│   │   │   ├── BackgroundSyncManager.swift     # Background tasks
│   │   │   └── TestTimerManager.swift          # Timer management
│   │   ├── AppDelegate.swift
│   │   └── Info.plist
│   └── Podfile
│
├── src/                              # React Native source code
│   │
│   ├── app/                          # App initialization
│   │   ├── App.tsx                   # Root component
│   │   ├── Navigation.tsx            # Navigation setup
│   │   └── Providers.tsx             # Context providers
│   │
│   ├── core/                         # Core utilities & config
│   │   ├── api/
│   │   │   ├── client.ts             # Axios instance with interceptors
│   │   │   ├── websocket.ts          # Socket.io client
│   │   │   └── endpoints.ts          # API endpoint definitions
│   │   ├── config/
│   │   │   ├── constants.ts          # App constants
│   │   │   ├── env.ts                # Environment variables
│   │   │   └── firebase.ts           # Firebase config
│   │   ├── database/
│   │   │   ├── schema.ts             # WatermelonDB schema
│   │   │   ├── migrations.ts         # Database migrations
│   │   │   └── index.ts              # Database setup
│   │   ├── storage/
│   │   │   ├── mmkv.ts               # MMKV storage wrapper
│   │   │   └── secure-storage.ts     # Encrypted storage
│   │   ├── native-modules/
│   │   │   ├── TestTimer.ts          # Bridge to native timer
│   │   │   ├── Analytics.ts          # Bridge to native analytics
│   │   │   └── Biometric.ts          # Bridge to biometric
│   │   └── utils/
│   │       ├── logger.ts             # Centralized logging
│   │       ├── error-handler.ts      # Global error handling
│   │       ├── date.ts               # Date utilities
│   │       └── validators.ts         # Common validators
│   │
│   ├── features/                     # Feature modules
│   │   │
│   │   ├── auth/
│   │   │   ├── components/
│   │   │   │   ├── LoginForm.tsx
│   │   │   │   ├── OTPInput.tsx
│   │   │   │   └── BiometricPrompt.tsx
│   │   │   ├── screens/
│   │   │   │   ├── LoginScreen.tsx
│   │   │   │   ├── SignupScreen.tsx
│   │   │   │   └── OTPVerificationScreen.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useAuth.ts
│   │   │   │   └── useBiometric.ts
│   │   │   ├── stores/
│   │   │   │   └── authStore.ts              # Zustand store
│   │   │   ├── services/
│   │   │   │   └── authService.ts
│   │   │   ├── models/
│   │   │   │   └── User.ts
│   │   │   └── types/
│   │   │       └── auth.types.ts
│   │   │
│   │   ├── dashboard/
│   │   │   ├── components/
│   │   │   │   ├── DailyTargetCard.tsx
│   │   │   │   ├── PerformanceChart.tsx
│   │   │   │   ├── WeakTopicsList.tsx
│   │   │   │   ├── StreakWidget.tsx
│   │   │   │   └── RankPrediction.tsx
│   │   │   ├── screens/
│   │   │   │   └── DashboardScreen.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useDashboardData.ts
│   │   │   │   └── useStreakCalculator.ts
│   │   │   ├── stores/
│   │   │   │   └── dashboardStore.ts
│   │   │   ├── services/
│   │   │   │   └── dashboardService.ts
│   │   │   └── types/
│   │   │       └── dashboard.types.ts
│   │   │
│   │   ├── tests/
│   │   │   ├── components/
│   │   │   │   ├── QuestionCard.tsx
│   │   │   │   ├── Timer.tsx
│   │   │   │   ├── QuestionPalette.tsx
│   │   │   │   ├── AnswerSheet.tsx
│   │   │   │   └── SubmitConfirmation.tsx
│   │   │   ├── screens/
│   │   │   │   ├── TestListScreen.tsx
│   │   │   │   ├── TestScreen.tsx
│   │   │   │   ├── ReviewScreen.tsx
│   │   │   │   └── ResultScreen.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useTestTimer.ts
│   │   │   │   ├── useTestNavigation.ts
│   │   │   │   ├── useAutoSave.ts
│   │   │   │   └── useTestAttempt.ts
│   │   │   ├── stores/
│   │   │   │   ├── testStore.ts
│   │   │   │   └── answerStore.ts
│   │   │   ├── services/
│   │   │   │   ├── testService.ts
│   │   │   │   └── testRepository.ts          # Offline storage
│   │   │   ├── models/
│   │   │   │   ├── Test.ts
│   │   │   │   ├── Question.ts
│   │   │   │   └── TestAttempt.ts
│   │   │   └── types/
│   │   │       └── test.types.ts
│   │   │
│   │   ├── analytics/
│   │   │   ├── components/
│   │   │   │   ├── AccuracyChart.tsx
│   │   │   │   ├── TimeHeatmap.tsx
│   │   │   │   ├── TopicAnalysis.tsx
│   │   │   │   ├── ComparisonGraph.tsx
│   │   │   │   └── InsightCard.tsx
│   │   │   ├── screens/
│   │   │   │   ├── AnalyticsScreen.tsx
│   │   │   │   └── DetailedAnalysisScreen.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useAnalytics.ts
│   │   │   │   └── useNativeAnalytics.ts      # Bridge to native
│   │   │   ├── services/
│   │   │   │   └── analyticsService.ts
│   │   │   └── types/
│   │   │       └── analytics.types.ts
│   │   │
│   │   ├── ai-tutor/
│   │   │   ├── components/
│   │   │   │   ├── ChatBubble.tsx
│   │   │   │   ├── ChatInput.tsx
│   │   │   │   ├── VoiceRecorder.tsx
│   │   │   │   ├── ImageUploader.tsx
│   │   │   │   └── StreamingResponse.tsx
│   │   │   ├── screens/
│   │   │   │   └── AITutorScreen.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useAIChat.ts
│   │   │   │   ├── useVoiceInput.ts
│   │   │   │   └── useImageUpload.ts
│   │   │   ├── services/
│   │   │   │   ├── aiService.ts
│   │   │   │   └── speechToText.ts
│   │   │   └── types/
│   │   │       └── ai.types.ts
│   │   │
│   │   ├── chat/
│   │   │   ├── components/
│   │   │   │   ├── MessageList.tsx
│   │   │   │   ├── MessageInput.tsx
│   │   │   │   └── TypingIndicator.tsx
│   │   │   ├── screens/
│   │   │   │   ├── ChatListScreen.tsx
│   │   │   │   └── ChatScreen.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useChat.ts
│   │   │   │   └── useRealtime.ts
│   │   │   ├── services/
│   │   │   │   ├── chatService.ts
│   │   │   │   └── websocketService.ts
│   │   │   └── types/
│   │   │       └── chat.types.ts
│   │   │
│   │   ├── study-planner/
│   │   │   ├── components/
│   │   │   │   ├── DailyPlanCard.tsx
│   │   │   │   ├── TopicSchedule.tsx
│   │   │   │   └── RevisionAlerts.tsx
│   │   │   ├── screens/
│   │   │   │   └── StudyPlannerScreen.tsx
│   │   │   ├── hooks/
│   │   │   │   └── useStudyPlan.ts
│   │   │   ├── services/
│   │   │   │   └── plannerService.ts
│   │   │   └── types/
│   │   │       └── planner.types.ts
│   │   │
│   │   ├── profile/
│   │   │   ├── components/
│   │   │   │   ├── ProfileHeader.tsx
│   │   │   │   ├── StatsOverview.tsx
│   │   │   │   └── SettingsItem.tsx
│   │   │   ├── screens/
│   │   │   │   ├── ProfileScreen.tsx
│   │   │   │   └── SettingsScreen.tsx
│   │   │   └── types/
│   │   │       └── profile.types.ts
│   │   │
│   │   └── onboarding/
│   │       ├── components/
│   │       │   ├── OnboardingSlide.tsx
│   │       │   └── GoalSelector.tsx
│   │       ├── screens/
│   │       │   └── OnboardingScreen.tsx
│   │       └── types/
│   │           └── onboarding.types.ts
│   │
│   ├── shared/                       # Shared components & utilities
│   │   ├── components/
│   │   │   ├── ui/
│   │   │   │   ├── Button.tsx
│   │   │   │   ├── Card.tsx
│   │   │   │   ├── Input.tsx
│   │   │   │   ├── Modal.tsx
│   │   │   │   ├── BottomSheet.tsx
│   │   │   │   ├── LoadingSpinner.tsx
│   │   │   │   ├── ErrorBoundary.tsx
│   │   │   │   ├── Toast.tsx
│   │   │   │   └── Skeleton.tsx
│   │   │   ├── layout/
│   │   │   │   ├── Screen.tsx
│   │   │   │   ├── Container.tsx
│   │   │   │   └── KeyboardAvoidingView.tsx
│   │   │   └── feedback/
│   │   │       ├── EmptyState.tsx
│   │   │       ├── ErrorState.tsx
│   │   │       └── OfflineIndicator.tsx
│   │   ├── hooks/
│   │   │   ├── useNetworkStatus.ts
│   │   │   ├── useKeyboard.ts
│   │   │   ├── useDebounce.ts
│   │   │   ├── useThrottle.ts
│   │   │   ├── useInterval.ts
│   │   │   └── useAppState.ts
│   │   └── animations/
│   │       ├── fadeIn.ts
│   │       ├── slideUp.ts
│   │       └── spring.ts
│   │
│   ├── design-system/                # Design tokens & theme
│   │   ├── tokens/
│   │   │   ├── colors.ts
│   │   │   ├── typography.ts
│   │   │   ├── spacing.ts
│   │   │   ├── shadows.ts
│   │   │   └── borderRadius.ts
│   │   ├── theme.ts                  # Theme configuration
│   │   └── ThemeProvider.tsx
│   │
│   ├── navigation/                   # Navigation configuration
│   │   ├── types.ts                  # Navigation types
│   │   ├── routes.ts                 # Route constants
│   │   ├── RootNavigator.tsx         # Root stack
│   │   ├── AuthNavigator.tsx         # Auth stack
│   │   ├── MainNavigator.tsx         # Main tab navigator
│   │   └── linking.ts                # Deep linking config
│   │
│   ├── services/                     # Global services
│   │   ├── sync/
│   │   │   ├── SyncManager.ts
│   │   │   ├── SyncQueue.ts
│   │   │   └── ConflictResolver.ts
│   │   ├── notification/
│   │   │   ├── NotificationService.ts
│   │   │   └── FCMService.ts
│   │   ├── analytics/
│   │   │   ├── AnalyticsService.ts
│   │   │   └── CrashlyticsService.ts
│   │   └── performance/
│   │       └── PerformanceMonitor.ts
│   │
│   ├── localization/                 # i18n
│   │   ├── i18n.ts
│   │   ├── translations/
│   │   │   ├── en.json
│   │   │   ├── hi.json
│   │   │   └── index.ts
│   │   └── useTranslation.ts
│   │
│   └── types/                        # Global types
│       ├── global.d.ts
│       ├── api.types.ts
│       └── common.types.ts
│
├── __tests__/                        # Tests
│   ├── unit/
│   │   ├── components/
│   │   ├── hooks/
│   │   └── services/
│   ├── integration/
│   │   └── flows/
│   └── e2e/
│       └── scenarios/
│
├── scripts/                          # Build & utility scripts
│   ├── codegen.sh                    # Generate types from API
│   ├── clean.sh                      # Clean build artifacts
│   └── bump-version.sh               # Version management
│
├── fastlane/                         # CI/CD automation
│   ├── Fastfile
│   ├── Appfile
│   └── Matchfile
│
├── .husky/                           # Git hooks
│   ├── pre-commit
│   └── pre-push
│
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── release.yml
│
├── docs/                             # Documentation
│   ├── ARCHITECTURE.md
│   ├── API.md
│   ├── CONTRIBUTING.md
│   └── DEPLOYMENT.md
│
├── .eslintrc.js                      # ESLint config
├── .prettierrc.js                    # Prettier config
├── tsconfig.json                     # TypeScript config
├── babel.config.js                   # Babel config
├── metro.config.js                   # Metro bundler config
├── package.json
├── yarn.lock
├── .gitignore
├── .env.example
├── app.json                          # App configuration
└── README.md
```

## 📋 Key Organizational Principles

### 1. Feature-Based Structure
Each feature is self-contained with its own:
- Components (UI)
- Screens (Containers)
- Hooks (Business logic)
- Stores (State)
- Services (Data access)
- Types (TypeScript definitions)

### 2. Separation of Concerns
- **Core**: Infrastructure, configuration, utilities
- **Features**: Business features
- **Shared**: Reusable components
- **Design System**: UI tokens and theme

### 3. Clear Dependency Flow
```
Features → Shared → Design System → Core
     ↓
  Services ← Native Modules
     ↓
    API / Database
```

### 4. Scalability Benefits
- Easy to add new features
- Clear ownership boundaries
- Reduced merge conflicts
- Parallel development possible
- Easy to test in isolation

### 5. Native Code Organization
- **Android**: Standard Kotlin/Java structure
- **iOS**: Standard Swift structure
- **Bridges**: TypeScript wrappers in `core/native-modules`

This structure supports a team of 10-50 engineers working in parallel while maintaining code quality and consistency.
