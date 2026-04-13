# Nielsen's 10 Usability Heuristics

Reference for usability audits. For each heuristic, check compliance and flag violations.

---

## 1. Visibility of System Status

The system should always keep users informed about what is going on.

✅ Loading indicators, progress bars, success/error states
❌ Silent failures, no confirmation after actions, unclear loading states

---

## 2. Match Between System and the Real World

Use words, phrases, and concepts familiar to the user.

✅ Plain language, familiar metaphors, logical ordering
❌ Technical jargon, internal naming, counter-intuitive groupings

---

## 3. User Control and Freedom

Users often make mistakes. Provide clear "emergency exits."

✅ Undo, cancel, back navigation, confirm before destructive actions
❌ No way to cancel, irreversible actions without warning, trapping users in flows

---

## 4. Consistency and Standards

Follow platform conventions. Don't make users guess.

✅ Consistent patterns across the product, adherence to platform norms
❌ Same action labeled differently, inconsistent button placement, novel patterns for standard tasks

---

## 5. Error Prevention

Design to prevent problems from occurring in the first place.

✅ Inline validation, disabled states for unavailable actions, confirmation dialogs
❌ No guardrails on destructive actions, accepting invalid input silently

---

## 6. Recognition Rather Than Recall

Minimize cognitive load. Users shouldn't have to remember things.

✅ Visible options, contextual help, breadcrumbs, recent items
❌ Requiring users to memorize codes, no context about where they are, hidden features

---

## 7. Flexibility and Efficiency of Use

Support both novice and expert users.

✅ Keyboard shortcuts, bulk actions, customizable workflows
❌ One-size-fits-all interface, no power user features, forcing step-by-step for experts

---

## 8. Aesthetic and Minimalist Design

Don't show information that isn't needed right now.

✅ Clean layouts, progressive disclosure, relevant content only
❌ Cluttered dashboards, too many options, visual noise drowning key actions

---

## 9. Help Users Recognize, Diagnose, and Recover from Errors

Error messages should be plain language, explain the problem, and suggest a solution.

✅ "Your password must be at least 8 characters" + show what's missing
❌ "Error 403", "Something went wrong", generic red borders with no explanation

---

## 10. Help and Documentation

Even if the system doesn't need docs, help should be easy to find.

✅ Contextual help, tooltips, searchable docs, onboarding guidance
❌ No help available, docs buried in footer, unhelpful FAQs

---

## Audit Output Format

For each heuristic violated:

```
[Heuristic #N – Name]
Severity: 🔴 / 🟡 / 🟢
Finding: [What's wrong]
Location: [Where in the UI]
Recommendation: [Specific fix]
```
