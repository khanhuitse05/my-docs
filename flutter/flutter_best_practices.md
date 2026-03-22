# Flutter Best Practices

This document outlines best practices and conventions for developing Flutter applications to ensure code quality, maintainability, performance, and scalability.
Template: <https://github.com/GoldenOwlAsia/mobile-flutter-template>

## 1. Project Structure

A well-organized project structure improves code navigation and maintainability.

### Recommended Structure

```text
lib/
├── core/
│   ├── constants/           # App-wide constants (e.g., colors, strings)
│   ├── models/              # Data models
│   ├── services/            # API, storage, or other services
│   └── utils/               # Utility functions and helpers
├── features/
│   ├── feature_name/
│   │   ├── bloc/            # Business logic (bloc, use cases, entities)
│   │   ├── widgets/         # Common UI widget for this feature
│   │   └── screen.dart     # Feature entry point
├── navigation/              # Routing and navigation logic
├── widgets/                 # Reusable widgets
├── domain/                  # Data layer (API calls, repositories, models)
└── main.dart                # App entry point
```

### Project Structure Tips

- Group files by feature (e.g., auth, profile) rather than type to keep related code together.
- Use `core` for shared resources across features.
- Keep `main.dart` minimal, delegating initialization to appropriate classes.

## 2. Naming Conventions

Consistent naming improves readability and maintainability.

### Files and Directories

- Use `snake_case` for file and directory names (e.g., `user_profile.dart`, `auth_service`).
- Name files based on their content (e.g., `login_screen.dart` for a login UI).

### Classes and Widgets

- Use `PascalCase` for class names (e.g., `UserProfile`, `LoginScreen`).
- Prefix private members with `_` (e.g., `_userData`).

### Variables and Functions

- Use `camelCase` for variables and functions (e.g., `fetchUserData`, `userName`).
- Make function names descriptive (e.g., `getUserById` instead of `getUser`).

### Constants

- Use `kCamelCase` for constants (e.g., `kPrimaryColor`, `kDefaultPadding`).

## 3. Coding Best Practices

Follow these guidelines to write clean and efficient Flutter code.

### Keep Widgets Small and Focused

- Break down large widgets into smaller, reusable ones.
- Each widget should have a single responsibility (e.g., `UserAvatar` for displaying a profile picture).

### Use Const Constructors

- Apply `const` to widgets and values where possible to improve performance (e.g., `const Text('Hello')`).

### Avoid Deep Widget Trees

- Use `Builder`, `LayoutBuilder`, or custom widgets to reduce nesting.
- Extract complex logic into separate methods or classes.

### Leverage Type Safety

- Use strong typing for variables, parameters, and return types.
- Avoid `dynamic` unless absolutely necessary.

### Handle Null Safety

- Embrace Dart's null safety features.
- Use `late` variables cautiously and prefer initializing variables where possible.

### Use Linting

- Adopt `flutter_lints` or `very_good_analysis` for consistent code quality.

## 4. Performance Optimization

Optimize your app for speed and responsiveness.

### Minimize Rebuilds

- Use `const` widgets to prevent unnecessary rebuilds.
- Leverage `ValueKey` or `UniqueKey` to control widget identity.
- Use `Consumer` (Provider) or `BlocBuilder` (Bloc) to rebuild only specific parts of the UI.

### Optimize Images

- Use compressed image formats (e.g., WebP).
- Leverage `Image.asset` with appropriate resolution (@2x, @3x).
- Cache network images with `cached_network_image`.

### Lazy Loading

- Load data or widgets only when needed (e.g., use `ListView.builder` for long lists).
- Implement pagination for API calls.

### Profile and Test

- Use Flutter's DevTools to identify performance bottlenecks.
- Test on low-end devices to ensure smooth performance.

## 5. Navigation

Handle navigation cleanly and efficiently.

### Use Named Routes

Define routes in a centralized file (e.g., `navigation/routes.dart`).

**Example:**

```dart
const String loginRoute = '/login';
const String homeRoute = '/home';
```

### Leverage Navigation Packages

- Use `go_router` or `auto_route` for type-safe navigation and deep linking.
- Avoid manual `Navigator.push` for complex apps.

### Navigation Tips

- Pass minimal data through navigation arguments (e.g., IDs instead of full objects).
- Handle back navigation and edge cases (e.g., unauthorized access).

## 6. State Management

### Recommended Approaches

- **Bloc**: Ideal for large apps with complex state and business logic.

### State Management Tips

- Keep business logic out of widgets; use services or blocs for logic.
- Use immutable state where possible (e.g., with `freezed` for Bloc).
- Leverage dependency injection for services and state management objects.
- Document state transitions for complex apps (e.g., using state diagrams).

## 7. Internationalization (i18n)

Support multiple languages for global reach.

### i18n Tips

- Use `intl` package for localization.
- Store translations in `.arb` files (e.g., `app_en.arb`, `app_es.arb`).
- Avoid hardcoding strings; use `AppLocalizations.of(context)`.

**Example:**

```dart
Text(S.of(context).welcomeMessage)
```

## 8. Dependency Management

Manage dependencies efficiently.

### Dependency Tips

- Pin specific versions in `pubspec.yaml` to avoid breaking changes (e.g., `http: ^0.13.5`).
- Regularly update dependencies with `flutter pub upgrade`.
- Avoid unnecessary dependencies to reduce app size.
