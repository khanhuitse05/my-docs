# Flutter Development Roadmap

🎯 **Target Audience:** JavaScript developers with experience in ReactJS, React Native, or NodeJS.

🧠 **Overall Goal:** Get familiar with Flutter fundamentals and state management using Flutter Bloc, ready to contribute to a Flutter project or ship a real mobile app.

✅ **Training Goals**
- Learn Flutter/Dart basics (with JS/React mental model)
- Learn state management with Flutter Bloc
- Build confidence through hands-on projects

---

## 0. Mindset Shift (IMPORTANT)

_Understand key differences between React and Flutter_

### React vs Flutter

| Concept   | React / RN       | Flutter                 |
| --------- | ---------------- | ----------------------- |
| UI        | JSX              | Widget tree             |
| Styling   | CSS / StyleSheet | Widget-based styling    |
| State     | useState / Redux | State (Riverpod / Bloc) |
| Lifecycle | useEffect        | initState / dispose     |
| Rendering | Virtual DOM      | Direct rendering (Skia) |

👉 **Key takeaway:**
- Everything is a **Widget**
- UI = Function(state)

### Dart for JS/TS Developers
- [Dart for JS Developers](https://dart.dev/resources/coming-from/js-to-dart)
- [Flutter for web developers](https://docs.flutter.dev/get-started/flutter-for/web-devs)
- [Flutter for React Native developers](https://docs.flutter.dev/get-started/flutter-for/react-native-devs)
- [Introduction to Flutter & Dart](https://docs.flutter.dev/get-started/flutter-for)
- [A tour of the Dart language](https://dart.dev/guides/language/language-tour)
- [Sound null safety](https://dart.dev/null-safety)
- [Effective Dart](https://dart.dev/guides/language/effective-dart)

---

## 1. Setup & Environment

### Install Flutter
- [Get started - install Flutter](https://docs.flutter.dev/get-started/install)
- [Successfully created a Flutter project and built for iOS and Android](https://docs.flutter.dev/get-started/codelab)
- [Set up an editor](https://docs.flutter.dev/get-started/editor) — recommend Visual Studio Code

### VSCode Extensions (recommended)
- Flutter
- Dart
- GitLens
- Awesome Flutter Snippets
- Built Value Snippets
- Code Spell Checker
- Dart Data Class Generator

### Folder Structure

```
lib/
├── app/          # App-level config (routes, themes, DI, etc.)
├── features/
│   ├── auth/
│   │   ├── widget/
│   │   ├── bloc/
│   │   └── presentation/
│   └── home/
├── domain/       # Reusable api, model
├── shared/       # Reusable widgets, utils, themes, constants
├── core/         # Base classes, network layer, exceptions
```

---

## 2. Write Your First Flutter App

**Goal:** Understand basic Flutter app structure and how to build UI.

### Resources
- [Review & Setup Flutter](https://flutter.dev/docs/get-started/codelab)
- [Your first Flutter app](https://codelabs.developers.google.com/codelabs/flutter-codelab-first#8)
- [Get Started with Flutter UI](https://docs.flutter.dev/ui) — Flutter team tutorial (project structure, UI, layout)

### Flutter Layout Principles
- Layouts in Flutter are built with **widgets**
- Widgets are classes used to build UIs
- Widgets are also used to build UI elements
- Compose simple widgets to build complex widgets

---

## 3. State Management (Flutter Bloc)

**Goal:** Learn production-ready state management patterns.

### Bloc Concepts
- [Why Bloc?](https://bloclibrary.dev/#/whybloc)
- [Bloc concepts](https://bloclibrary.dev/#/coreconcepts)
- [Bloc Architecture](https://bloclibrary.dev/#/architecture)

### Practice
- [Write a Flutter app using Flutter Bloc](https://bloclibrary.dev/#/fluttercountertutorial)
- [Flutter Login](https://bloclibrary.dev/#/flutterlogintutorial) — full example with auth flow

---

## 4. Build a Real App

**Goal:** Ship a real mobile app using a design-to-code workflow.

### Steps

1. **Choose a design**
   - Go to [Figma Community](https://www.figma.com/community/search?resource_type=mixed&sort_by=relevancy&query=mobile%20app) and pick a mobile app UI (login, dashboard, e-commerce, etc.).

2. **Start from a production-ready template** (recommended)
   - [mobile-flutter-template](https://github.com/GoldenOwlAsia/mobile-flutter-template) — GoldenOwl boilerplate with Bloc, routing, Firebase, Sentry, flavors (staging/production).
   - Clone → customize with `customizer.sh` → plug in your Firebase config.

3. **Use AI to build faster**
   - Use Cursor / AI agents to generate screens and widgets from Figma designs.
   - Copy design specs (layout, colors, typography) → prompt AI → iterate.

4. **Implement & iterate**
   - Implement one screen at a time.
   - Follow the template's structure (`lib/src/feature/`) and naming (e.g. `MUser`, `XButton`).
   - Test on device, fix layout issues, then move to the next screen.

---

## Suggested Learning Path

| Phase | Focus |
| ----- | ----- |
| **Day 1** | Mindset shift, Dart basics, Setup, Folder structure |
| **Day 2** | Write first Flutter app, UI & layout principles |
| **Day 3** | State management with Flutter Bloc |
| **Day 4+** | Build a real app from Figma design |
