# Flutter Roadmap

## 🚀 Introduction

This Flutter Roadmap is a living document that outlines the architecture, tools, conventions, and workflows adopted for Flutter development across our projects. It’s intended to align the team on a unified development strategy, boost productivity, and ensure code quality and maintainability over time.

## 🎯 Purpose

- Provide a consistent structure and guidelines for all Flutter projects.
- Streamline onboarding for new developers.

## 🧭 How to Use This Roadmap

- Read from top to bottom if you’re onboarding or starting a new project.
- Jump to specific sections for quick references.
- This doc will evolve — feedback and contributions are encouraged.

---

## 📦 Setup Flutter

### Get started

1. Install Flutter
2. Successfully create a Flutter project and build for iOS and Android

### 🧰 Set up an editor (recommend Visual Studio Code)

**VSCode extensions:**

- GitLens
- Awesome Flutter Snippets
- Built Value Snippets
- Code Spell Checker
- Dart Data Class Generator

---

## 🗂️ Folder Structure

```
lib/
├── app/              # App-level config (routes, themes, DI, etc.)
├── features/
│   ├── auth/
│   │   ├── widget/
│   │   ├── bloc/
│   │   └── presentation/
│   └── home/
├── domain/           # Reusable api, model
├── shared/           # Reusable widgets, utils, themes, constants
├── core/             # Base classes, network layer, exceptions
```

---

## 🧱 Core Architecture

### 🔁 State Management

**Flutter Bloc** (recommended)

- Each feature has its own Bloc/Cubit.
- Events trigger state changes.
- States are immutable and represent UI snapshots.

### 🔧 Environment Config

- Use `.env` files via `flutter_dotenv`
- Define environment-specific variables for API endpoints, Firebase configs, feature toggles, etc.

### 🧪 Dependency Injection

- Use `get_it` for simple DI with less boilerplate.

### 🧭 Navigation

**Recommended options:**

- `go_router` (preferred for simplicity + deep linking)
- `auto_route` (if you need more control/custom transitions)

### 📤 Repository Pattern

All data flow (API, DB, cache) is abstracted via repositories in the domain layer.

```dart
abstract class AuthRepository {
  Future<User> login(String email, String password);
}
```

---

## 🧪 Testing Strategy

We follow a layered testing approach to ensure correctness, stability, and confidence during refactors or releases.

### 📦 Testing Libraries

| Package            | Description                                                                                              |
| ------------------ | -------------------------------------------------------------------------------------------------------- |
| `flutter_test`     | The default Flutter testing library that includes tools for writing unit, widget, and integration tests. |
| `mockito`          | Used to create mocks of objects for unit testing.                                                        |
| `bloc_test`        | Helps test BLoCs and Cubits.                                                                             |
| `integration_test` | Flutter's official library for running integration tests.                                                |

### ✅ 1. Unit Testing

Tests small, isolated logic like use cases, Cubits/Blocs, and pure functions.

- **Located in:** `test/feature_name/unit/`
- **Tools:** `flutter_test`, `mocktail` or `mockito`

### 🧱 2. Widget Testing

Tests UI widgets in isolation with fake data and dependencies.

- **Located in:** `test/feature_name/widgets/`

### 📱 3. Integration Testing

Tests full user flows across screens.

- **Located in:** `integration_test/`
- Use `flutter_test` + `integration_test` packages.

### 🛠️ CI Integration

- Run all tests on each PR using GitHub Actions, Bitrise, or GitLab CI.
- Optionally: Add test coverage with `lcov` + `coveralls`.

---

## 📦 Dependency Management

### 📚 Pubspec.yaml

Your `pubspec.yaml` file is where all external dependencies are listed.

```yaml
dependencies:
  flutter:
    sdk: flutter
  flutter_bloc: ^8.0.0
  riverpod: ^2.0.0
  http: ^0.13.3

dev_dependencies:
  flutter_test:
    sdk: flutter
  mockito: ^5.0.0
```

### 🚦 Managing Package Versions

Managing versions is important for avoiding breaking changes. You can use:

- **Caret syntax (`^`):** Ensures backward compatibility with a major version.

  ```yaml
  dependencies:
    flutter_bloc: ^8.0.0
  ```

- **Exact versions:** Avoid breaking changes by pinning a version.

  ```yaml
  dependencies:
    flutter_bloc: 8.0.0
  ```

- **Dependency Overrides:** Used to force a specific version (use carefully).

  ```yaml
  dependency_overrides:
    flutter_bloc: ^8.0.0
  ```

## 📦 Common Packages

Here’s a breakdown of some of the most common and useful packages in Flutter development:

### Networking

- **http:** A simple and widely used package for making HTTP requests. It works with APIs and JSON responses.
- **dio:** A powerful HTTP client that supports additional features like interceptors, request cancellation, and file downloading.

### Navigation

- **auto_route:** Provides a declarative approach to navigation, helping you manage route definitions and routing logic cleanly.
- **go_router** (preferred for simplicity + deep linking)

### UI and Design

- **flutter_svg:** A package for rendering SVG images in Flutter. It’s essential when working with vector graphics.

- **cached_network_image:** This package allows for caching images from the web, improving app performance by storing images locally.

- **modal_bottom_sheet:** Popular package for creating custom modal bottom sheets in Flutter.

- **bot_toast:** A package used to display toast notifications in Flutter. It offers a more customizable and lightweight alternative to traditional toast messages.

- **shimmer:** A package for adding shimmer effects to your Flutter UI.

- **auto_size_text:** A package for creating text widgets that automatically adjust their size to fit within the available space.

- **lottie:** A Flutter package that allows you to display Lottie animations, which are lightweight JSON-based animations.

### Authentication and Firebase (Analytics & Monitoring)

- **firebase_analytics:** Provides integration with Firebase Analytics to track user interactions and behavior in your app.

- **sentry_flutter:** A Flutter plugin for integrating Sentry error tracking, which helps you capture and track errors, crashes, and performance issues.

- **firebase_auth:** Firebase Authentication package for Flutter. It helps you implement user authentication features, including Google sign-in, Facebook login, email/password authentication, etc.

- **google_sign_in**, **sign_in_with_apple**

- **firebase_messaging:** Integrates Firebase Cloud Messaging (FCM) with your Flutter app, enabling push notifications.

- **onesignal_flutter:** Integrates OneSignal’s push notification service for delivering notifications to your app users.

- **flutter_local_notifications:** A package that provides the ability to display local notifications within the app.

### Other Utility Packages

- **intl:** A package for internationalization and localization, helping you format dates, numbers, and messages in different languages and locales.
- **device_info_plus:** A plugin to retrieve detailed information about the device on which the app is running.
- **share_plus:** Provides the ability to share content (text, images, etc.) from your app to other apps.

---

## 🛠️ Dart Language

- [A tour of the Dart language](https://dart.dev/guides/language/language-tour)
- [Sound null safety](https://dart.dev/null-safety)
- [Effective Dart](https://dart.dev/guides/language/effective-dart)
- **From another platform:**
  - Flutter for React Native developers
  - Flutter for Android developers
  - Flutter for web developers

---

## 🛠️ Write your first Flutter app

In this phase, you'll bring everything together by building a complete app from scratch. You'll apply key concepts such as design patterns, networking, state management, Firebase integration, and deployment.

### Goals after completing these projects

| Area                     | Tasks                                                                                                                               |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| **Basic Widgets**        | Learn Material Design widgets, Explore Cupertino (iOS-style) widgets                                                                |
| **Design Patterns**      | Apply common patterns like Observer, Factory, Builder, Dependency Injection, and Skeleton                                           |
| **Networking**           | Work with JSON data, Connect to RESTful APIs                                                                                        |
| **Firebase Integration** | Use Firestore for the database, Implement push notifications, Handle file uploads with Firebase Storage, Set up user authentication |
| **Deployment**           | Build and deploy for both iOS and Android                                                                                           |
| **Assets**               | Add images and custom fonts, Customize app icon and splash screen                                                                   |
| **State Management**     | Use a state management solution (e.g., Flutter Bloc)                                                                                |
| **Packages**             | Get familiar with using third-party packages                                                                                        |
| **Navigation**           | Implement stack-based navigation using `go_router`                                                                                  |

### Demo

- **Get Started with Flutter UI** — A tutorial from the Flutter team. It is very suitable for you to start coding Flutter. You will be familiar with the Flutter Project structure, UI, and Layout used.

- **Flutter Firebase Login (using Bloc)** — In this tutorial, we're going to build a Firebase Login Flow in Flutter using the Bloc library.
- **Flutter Gallery Widget** — You will try all the basic widgets commonly used. Use the widget configurations, and see the changes of each configuration.
