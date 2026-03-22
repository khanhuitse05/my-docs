# Flutter Development Roadmap (For React Native / ReactJS Developers)

---

## 0. Mindset Shift (IMPORTANT)

_Understand key differences between React and Flutter_

## React vs Flutter

| Concept   | React / RN       | Flutter                 |
| --------- | ---------------- | ----------------------- |
| UI        | JSX              | Widget tree             |
| Styling   | CSS / StyleSheet | Widget-based styling    |
| State     | useState / Redux | State (Riverpod / Bloc) |
| Lifecycle | useEffect        | initState / dispose     |
| Rendering | Virtual DOM      | Direct rendering (Skia) |

👉 Key takeaway:

- Everything is a **Widget**
- UI = Function(state)

---

- [Dart for JS Developers](https://dart.dev/resources/coming-from/js-to-dart)

## Flutter - Tutorial

### Write your first app

Goal:

- Install Flutter
- How to write a flutter app (Basic structure)

Documents:

- [Review & Setup Flutter](https://flutter.dev/docs/get-started/codelab)
- [Your first Flutter app](https://codelabs.developers.google.com/codelabs/flutter-codelab-first#8)

### Start build a real app

Goal: Ship a real mobile app using a design-to-code workflow.

**Steps:**

1. **Choose a design**
   - Go to [Figma Community](https://www.figma.com/community/search?resource_type=mixed&sort_by=relevancy&query=mobile%20app) and pick a mobile app UI you like (login, dashboard, e-commerce, etc.).

2. **Start from a production-ready template** (recommended)
   - [mobile-flutter-template](https://github.com/GoldenOwlAsia/mobile-flutter-template) — GoldenOwl boilerplate with Bloc, routing, Firebase, Sentry, flavors (staging/production).
   - Clone → customize with `customizer.sh` → plug in your Firebase config.

3. **Use AI to build faster**
   - Use Cursor / AI agents to generate screens and widgets from Figma designs.
   - Copy design specs (layout, colors, typography) → prompt AI → iterate.

4. **Implement & iterate**
   - Implement one screen at a time.
   - Follow the template’s structure (`lib/src/feature/`) and naming (e.g. `MUser`, `XButton`).
   - Test on device, fix layout issues, then move to the next screen.
