# 📱 Mobile Estimation Guidelines

## Overview

For mobile development, we avoid estimating work in **exact hours**.  
Instead, we use **Story Points (SP)** based on the Fibonacci sequence:

> 1, 2, 3, 5, 8, 13…

Story points represent the **overall effort**, combining:

- Complexity
- Uncertainty
- Risk
- Scope (UI + Logic + Integration)

This helps the team estimate more reliably, especially when dealing with:

- Platform differences (iOS vs Android)
- Device fragmentation
- SDK / OS constraints
- API dependencies

---

## Core Principles

### 1. Estimate effort, not time

Avoid “this takes 6 hours”.  
Instead: “this is a 3-point story”.

### 2. Consider full mobile scope

Each estimation should include:

- UI implementation (SwiftUI / UIKit / Flutter / Compose)
- State management
- API integration
- Error handling
- Edge cases (offline, permissions, lifecycle)

### 3. Account for platform differences

- Flutter: mostly shared UI, but watch platform channels
- Native: duplicated effort across iOS & Android
- SDK behavior differences (camera, biometrics, push notifications)

### 4. Break down large stories

If a story > 13 points → **must be split**

---

## Story Point Guidelines

### 🟢 1 Point — Tiny Changes

**Characteristics**

- Very clear, no ambiguity
- No backend dependency OR minimal
- No architecture impact

**Effort**

- ~1–2 hours

**Examples**

- Change text, color, spacing
- Adjust UI alignment (no layout restructure)
- Minor config change
- Simple sorting/filter (local only)

---

### 🟢 2 Points — Small Changes

**Characteristics**

- Mostly UI or mostly logic
- Slight modification to existing logic

**Effort**

- ~0.5 – 1 day

**Examples**

- Add small UI feature across multiple screens
- Update existing API field mapping
- Add simple calculation (e.g., totals, counters)
- Minor validation logic

---

### 🟡 3 Points — Medium Changes

**Characteristics**

- Modify existing logic or flow
- Requires understanding current implementation

**Effort**

- ~1 day

**Examples**

- Update business logic in a feature
- Refactor part of ViewModel / Bloc / Presenter
- Add new local data handling
- Adjust navigation flow

---

### 🟡 5 Points — Feature-Level Work

**Characteristics**

- New functionality with limited scope
- Simple backend integration

**Effort**

- ~2–3 days

**Examples**

- Add a new screen with API integration
- Create one new endpoint integration
- Basic form + validation + submission
- Minor state management changes

---

### 🟠 8 Points — Complex Feature

**Characteristics**

- Multi-screen feature
- Requires research or spike
- Involves multiple layers (UI + API + state)

**Effort**

- ~4–5 days (half sprint)

**Examples**

- New feature with multiple screens & flows
- Offline handling + sync logic
- Integration with device features (camera, location, biometrics)
- Data migration (local DB changes)

---

### 🔴 13 Points — High Uncertainty / Risk

**Characteristics**

- Unknown feasibility
- Requires POC or experimentation
- Architecture or major design impact

**Effort**

- Not strictly time-bound  
  → Should be **split if possible**

**Examples**

- Implement new architecture (e.g., migrate to MVVM / Clean Architecture)
- Introduce new SDK (payments, video streaming, WebRTC)
- Complex performance optimization
- Cross-platform deep integration

---

## Risk & Uncertainty Dimensions

When estimating, consider:

### 🔹 Complexity

- UI complexity (animations, responsive layout)
- Logic complexity (state, concurrency)

### 🔹 Uncertainty

- Requirements clarity
- API readiness
- Unknown SDK behavior

### 🔹 Risk

- Impact on existing features
- Data migration
- Platform-specific bugs

---

## Mobile-Specific Considerations

### 📲 Device & OS Fragmentation

- Android versions & device variations
- iOS backward compatibility

### 🔌 API Dependency

- Backend readiness
- API stability

### ⚙️ Performance

- Rendering performance
- Memory usage
- Battery impact

### 🌐 Network Conditions

- Offline mode
- Retry & error handling

### 🔐 Permissions & Security

- Camera / Location / Notifications
- Authentication flow (biometric, OAuth)

---

## Best Practices

- ✅ Always discuss estimates as a team (FE + BE + QA)
- ✅ Use relative comparison (this task vs another)
- ✅ Re-estimate when scope changes
- ✅ Split large/unclear tasks early
- ❌ Don’t convert story points to hours
- ❌ Don’t estimate alone for complex tasks

---

## Summary

Story points help mobile teams:

- Handle uncertainty better
- Align across platforms
- Avoid misleading time commitments

> Focus on **effort + complexity**, not **hours**.
