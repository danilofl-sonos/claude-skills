# Design Critique Framework

Use this structure whenever performing a design critique. Adapt the depth to the scope of the request — a quick gut-check needs less formality than a full review.

---

## 1. Context Check (Before Critiquing)

Confirm you understand:
- **Who** is the target user? (role, expertise, context of use)
- **What** is the user trying to accomplish on this screen/flow?
- **Where** does this fit in the broader product? (entry point, mid-flow, terminal screen)
- **What platform/device** is this designed for?

If any of these are unclear, ask before proceeding.

---

## 2. First Impressions (5-Second Test)

Before detailed analysis, state:
- What is the **primary message or action** a user would notice first?
- Does the visual hierarchy **direct attention** to the right thing?
- What is your **immediate emotional response** to the design? (calm, overwhelming, trustworthy, confusing, etc.)

---

## 3. What's Working

Lead with genuine positives — be specific, not generic.

❌ "The layout looks clean."
✅ "The two-column layout creates a clear separation between form input and contextual help, which reduces cognitive load for first-time users."

---

## 4. Issues & Severity Ratings

Categorize every issue by user impact:

| Severity | Label | Criteria |
|----------|-------|----------|
| 🔴 | Critical | Blocks task completion or causes user error |
| 🟡 | Important | Creates friction, confusion, or reduces trust |
| 🟢 | Nice-to-have | Polish or minor improvement with low impact |

For each issue:
1. **Describe the problem** — what a user would experience
2. **Explain why it's a problem** — root cause (hierarchy, affordance, labeling, etc.)
3. **Suggest a concrete fix** — not "improve the button" but "change CTA label from 'Submit' to 'Save & Continue' to set clearer expectations"

Limit to the **top 5–7 issues**. More than that signals a redesign, not a critique.

---

## 5. Accessibility Flags

Always check proactively:
- **Contrast:** Does text meet WCAG AA (4.5:1 for body, 3:1 for large text)?
- **Touch targets:** Are interactive elements at least 44×44px on mobile?
- **Focus states:** Are keyboard/tab focus indicators visible?
- **Labels:** Do form inputs have visible labels (not just placeholder text)?
- **Error states:** Are errors communicated beyond color alone?

---

## 6. Top Recommendations

Close with a ranked list of the 3 changes that would have the highest impact:

1. [Highest impact change]
2. [Second highest]
3. [Third highest]

Keep these actionable and scoped — the user should be able to act on them immediately.

---

## 7. Open Questions (Optional)

If there are design decisions you can't evaluate without more context, list them:
- "Is there a reason the primary CTA is below the fold on mobile? If not, this should move up."
- "Who manages the empty state — is there a seeding strategy, or do new users start with a blank canvas?"
