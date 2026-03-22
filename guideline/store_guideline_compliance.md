# 📱 Mobile App Store Guideline Compliance

**Version:** 1.0  
**Owner:** Jimmy
**Applies to:** iOS (App Store) & Android (Google Play)

---

## 1. 🎯 Purpose

This document defines the standards and processes required to ensure our mobile apps comply with App Store and Google Play policies, reducing the risk of rejection, removal, or account penalties.

---

## 2. 📦 Scope

Applies to:

- All mobile apps (new + existing)
- All releases (major, minor, hotfix)
- Production builds for store submission

---

## 3. 🚨 Core Principles

1. User Safety First
2. Transparency in Data Usage
3. No Misleading Behavior
4. Respect Platform Rules
5. Review Before Submit

---

## 4. 🧩 Key Compliance Areas

### 4.1 Account & Authentication

**Requirements**

- Clear login flows
- No forced account creation unless necessary
- Account deletion supported

**Checklist**

- [ ] Login works
- [ ] Logout works
- [ ] Account deletion available
- [ ] No hidden auth flows

---

### 4.2 Data Privacy & Permissions

**Rules**

- Request only necessary permissions
- Explain usage before requesting
- Match store declaration

**Checklist**

- [ ] Permission explanation shown
- [ ] Privacy policy valid
- [ ] Data usage matches declaration
- [ ] No unnecessary background access

---

### 4.3 Payments & Subscriptions

**Rules**

- iOS: Use in-app purchase
- Android: Use Google Play Billing

**Checklist**

- [ ] No external payment links (iOS)
- [ ] Subscription terms clear
- [ ] Restore purchase implemented
- [ ] Pricing consistent

---

### 4.4 Content & UX

**Checklist**

- [ ] No fake UI or misleading elements
- [ ] No dead buttons
- [ ] No debug UI
- [ ] All links functional

---

### 4.5 Performance & Stability

**Checklist**

- [ ] No crash on launch
- [ ] Core flows work
- [ ] Works on latest OS
- [ ] Handles offline state

---

### 4.6 Metadata Compliance

**Checklist**

- [ ] Screenshots match UI
- [ ] No fake claims
- [ ] Correct age rating
- [ ] Accurate description

---

### 4.7 Background Behavior

**Checklist**

- [ ] No unnecessary background tasks
- [ ] No hidden tracking
- [ ] Battery usage reasonable

---

### 4.8 Third-party SDKs

**Checklist**

- [ ] SDK reviewed
- [ ] Declared in privacy
- [ ] No deprecated SDKs

---

### 4.9 Backward Compatibility

**Rules**

- Support minimum OS versions declared in store listing
- Handle data migration on upgrade without data loss
- Avoid breaking changes for users updating from older versions

**Checklist**

- [ ] Works on oldest supported OS
- [ ] Upgrade path tested
- [ ] No breaking API changes for in-use features

---

## 5. 🔄 Release Compliance Process

### Step 1 — Developer

- Self-check compliance

### Step 2 — QA

- Validate flows and permissions

### Step 3 — Tech Lead

- Final review

### Step 4 — Submission

- [ ] Version updated
- [ ] Release notes added
- [ ] Privacy form completed

---

## 6. ↩️ Rollback / Hotfix Readiness

**Rules**

- Keep previous build artifacts and signing credentials available
- Document rollback steps per platform
- Define escalation path for critical store issues

**Checklist**

- [ ] Previous version build available
- [ ] Hotfix branch strategy defined
- [ ] Store listing changes reversible

---

## 7. ❌ Common Rejection Reasons

- Crash on launch
- Broken login
- Missing account deletion
- Misleading UI
- Invalid privacy policy
- External payment (iOS)

---

## 8. 🔐 Ownership

| Role      | Responsibility     |
| --------- | ------------------ |
| Developer | Feature compliance |
| QA        | Validation         |
| Tech Lead | Approval           |
| PM        | Metadata           |

---

## 9. 🧪 Testing

- Fresh install
- Upgrade
- Logged in/out
- Offline
- Permission denied

---

## 10. 📌 Best Practices

- Test on real devices
- Avoid demo logic in production
- Keep store content updated
- Monitor feedback

---

## 11. 📣 Final Rule

> If unsure → escalate before submitting
