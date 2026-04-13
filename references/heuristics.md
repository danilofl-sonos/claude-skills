# Nielsen's 10 Usability Heuristics

Reference for usability audits. For each heuristic, check whether the interface satisfies, partially satisfies, or violates it — then rate severity and suggest a fix.

---

## 1. Visibility of System Status

**Principle:** Keep users informed about what is happening through appropriate feedback within a reasonable time.

**What to look for:**
- Loading states (spinners, progress bars, skeleton screens)
- Success/error confirmations after actions
- Active/selected states on navigation and controls
- Upload or save progress indicators

**Common violations:**
- Button does nothing visibly after click
- No feedback after form submission
- No indication of where the user is in a multi-step flow

---

## 2. Match Between System and the Real World

**Principle:** Use language, concepts, and conventions familiar to the user — not system-oriented terminology.

**What to look for:**
- Labels use the user's vocabulary, not technical or internal terms
- Mental models match real-world analogies (e.g., shopping cart, inbox)
- Icons are universally recognizable or labeled

**Common violations:**
- Error codes instead of plain-language messages
- Internal product names surfaced to end users
- Ambiguous icons with no labels

---

## 3. User Control and Freedom

**Principle:** Support undo and redo. Provide a clear "emergency exit" for users who took a wrong action.

**What to look for:**
- Undo/redo for destructive actions
- Cancel buttons on dialogs, forms, and flows
- Back navigation that preserves state
- Ability to dismiss/close modals

**Common violations:**
- Deleting without confirmation or undo
- Modal with no close button
- Browser back breaks the flow

---

## 4. Consistency and Standards

**Principle:** Follow platform conventions. Users should not have to wonder whether different words, situations, or actions mean the same thing.

**What to look for:**
- Consistent button styles, labels, and placement across screens
- Terminology used consistently throughout the product
- Adherence to platform conventions (iOS, Android, web patterns)

**Common violations:**
- "Save" on one screen, "Update" on another for the same action
- Primary button on the left in some dialogs, right in others
- Inconsistent iconography for the same concept

---

## 5. Error Prevention

**Principle:** Design to prevent problems from occurring in the first place.

**What to look for:**
- Inline validation before form submission
- Confirmation dialogs for destructive or irreversible actions
- Constraints that prevent invalid input (e.g., date pickers, input masks)
- Clear affordances that prevent misuse

**Common violations:**
- No confirmation before deleting a record
- Free-text input where a constrained input would suffice
- Ambiguous UI that leads users to take the wrong action

---

## 6. Recognition Rather Than Recall

**Principle:** Minimize the user's memory load. Make objects, actions, and options visible.

**What to look for:**
- Options visible in context (no need to remember a command)
- Recently used items, search history, or smart defaults
- Contextual help and tooltips where relevant
- Labels on all icons and controls

**Common violations:**
- Icon-only toolbars with no labels or tooltips
- Requiring users to remember syntax for a search/filter
- Settings buried in menus with no discoverability

---

## 7. Flexibility and Efficiency of Use

**Principle:** Allow expert users to speed up interactions. Support both novice and expert usage patterns.

**What to look for:**
- Keyboard shortcuts for power users
- Bulk actions for repetitive tasks
- Saved searches, templates, or presets
- Quick access to frequently used features

**Common violations:**
- No keyboard navigation on web apps
- No bulk select/edit for list views
- Every task requires the same number of steps regardless of user expertise

---

## 8. Aesthetic and Minimalist Design

**Principle:** Remove irrelevant or rarely needed information. Every extra element competes with relevant information.

**What to look for:**
- Screens free of visual noise and unnecessary elements
- Only information relevant to the current task is shown
- Progressive disclosure used for complex or advanced options

**Common violations:**
- Dashboard overloaded with widgets and metrics
- Long forms asking for information not needed at this step
- Promotional content mixed into task-oriented screens

---

## 9. Help Users Recognize, Diagnose, and Recover from Errors

**Principle:** Error messages should be plain language, precisely indicate the problem, and constructively suggest a solution.

**What to look for:**
- Error messages explain what went wrong and what to do next
- Errors are shown in context (inline, near the problem)
- Errors don't erase user input
- Distinction between user errors and system errors

**Common violations:**
- "An error occurred. Please try again." with no context
- Validation errors shown only at top of form, not near the field
- Form cleared after a submission error

---

## 10. Help and Documentation

**Principle:** Even though it's better if the system can be used without documentation, sometimes help is necessary.

**What to look for:**
- Contextual help (tooltips, inline guidance) at decision points
- Searchable documentation or knowledge base
- Onboarding for first-time users
- Empty states that guide rather than confuse

**Common violations:**
- Empty states with no guidance ("No items found" — and nothing else)
- Complex features with no tooltip or contextual explanation
- Help documentation not accessible from within the relevant screen

---

## Audit Scoring Template

| # | Heuristic | Status | Severity | Finding | Recommendation |
|---|-----------|--------|----------|---------|----------------|
| 1 | Visibility of System Status | ✅ / ⚠️ / ❌ | 🔴/🟡/🟢 | | |
| 2 | Match: System & Real World | ✅ / ⚠️ / ❌ | 🔴/🟡/🟢 | | |
| 3 | User Control & Freedom | ✅ / ⚠️ / ❌ | 🔴/🟡/🟢 | | |
| 4 | Consistency & Standards | ✅ / ⚠️ / ❌ | 🔴/🟡/🟢 | | |
| 5 | Error Prevention | ✅ / ⚠️ / ❌ | 🔴/🟡/🟢 | | |
| 6 | Recognition vs Recall | ✅ / ⚠️ / ❌ | 🔴/🟡/🟢 | | |
| 7 | Flexibility & Efficiency | ✅ / ⚠️ / ❌ | 🔴/🟡/🟢 | | |
| 8 | Aesthetic & Minimalist | ✅ / ⚠️ / ❌ | 🔴/🟡/🟢 | | |
| 9 | Error Recovery | ✅ / ⚠️ / ❌ | 🔴/🟡/🟢 | | |
| 10 | Help & Documentation | ✅ / ⚠️ / ❌ | 🔴/🟡/🟢 | | |
