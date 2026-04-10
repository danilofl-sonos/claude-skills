---
name: jira-story-writer
description: Generate Jira-ready Agile artifacts (User Stories, Spikes, Epics, Bugs) with INVEST-compliant structure, BDD acceptance criteria, and Fibonacci story point estimation. Use this skill whenever the user asks to write, create, generate, or refine any of the following: user stories, Jira tickets, Jira tasks, acceptance criteria, story points, sprint items, backlog items, spikes, epics, or bug reports. Also trigger when the user describes a business requirement, feature request, or defect and wants it structured for a development team. Do NOT wait for the user to say "use the skill" — if the request involves creating structured development work items, use this skill immediately.
---

# Jira Story Writer

Generate high-quality, Jira-ready Agile artifacts for development teams. This skill enforces INVEST principles, BDD acceptance criteria, and Fibonacci estimation on every output.

## Core Behavior Rules

Before generating anything, ask 1–2 pointed clarifying questions to define scope. Never generate stories based on vague input. Examples:
- "Which user persona is this for (e.g., Tier 1 Agent, Admin, End User)?"
- "Is this about creation, update, or resolution of the entity?"
- "Does this touch an external API, integration, or third-party service?"

Challenge incorrect assumptions directly. If the user's framing is wrong or there's a faster approach, say so before generating.

Decide how many artifacts to generate based on the scope of the requirement. A focused, atomic requirement may need only 1 story. A broader feature may need several. Use judgment — the goal is correct decomposition, not a fixed count. If a requirement is large enough to warrant an Epic, say so and offer to decompose it.

End every response with a direct, guiding question to keep the workflow moving (e.g., "Which of these stories best captures the immediate need, or should we refine the acceptance criteria on Story 2?").

---

## Estimation Rules (Fibonacci — Mandatory on Every Artifact)

Use this scale strictly. Always include a written rationale referencing these definitions:

| Points | Label | Examples |
|--------|-------|---------|
| 1 | Trivial | Update a picklist value, add a field to a layout, CSS tweak |
| 2 | Small | Simple Flow, new stateless component, basic API fetch |
| 3 | Medium | Complex Flow with branches, Apex Trigger with unit tests, new CRUD form |
| 5 | Large | 3rd-party integration, complex LWC, complex state management |
| 8 | Extra Large | Multi-component LWC + Apex controllers, significant module refactor |
| 13 | 🚩 Red Flag | Trigger the Discovery Split Rule (see below) |
| Epic | Unstoppable | Beyond 13 — offer to decompose into 5–8 stories |

### Discovery Split Rule (13 Points)

If a task scores 13, do NOT simply assign 13. Instead:
1. State: "This story is too large and carries too much uncertainty to execute safely."
2. Identify the specific technical unknowns.
3. List required sub-tasks (e.g., Analysis, Data Mapping, Testing, Execution).
4. Propose how to split into smaller 3-point and 5-point stories.

### Epic Handling

If scope exceeds 13 points, label it an Epic and automatically offer to generate 5–8 child User Stories from it.

---

## Output Templates

### User Story Template

Use this exact structure. Do not skip any section.

```
## User Story: [Concise Story Title]

### ESTIMATION & COMPLEXITY
- **Story Points:** [1 / 2 / 3 / 5 / 8 / 13 / Epic]
- **Rationale:** [Explain using the scale above. Reference specific complexity drivers.]

---

### USER STATEMENT
**As a** [actor]
**I want** [action]
**So that** [expected outcome — must state clear business value]

**Business Objective:** [Why is this story needed?]
**Business Overview:** [What problem does it solve?]

---

### OUT-OF-SCOPE
Items NOT delivered with this story (even if part of the broader flow):
- [Item 1] — Team responsible: [Team Name]
- [Item 2] — Related Story ID: [ID if known]

---

### ACCEPTANCE CRITERIA
BDD format. Create as many criteria as needed — do not limit to 3.

| # | Given | When | Then |
|---|-------|------|------|
| 1 | [Initial state/context] | [User action] | [Expected system result] |
| 2 | [Initial state/context] | [User action] | [Expected system result] |
| 3 | [Initial state/context] | [User action] | [Expected system result] |

---

### TECHNICAL NOTES
- [ ] Are there configuration changes? (Fields, Layouts, Permissions)
- [ ] Is there custom logic? (Flow, Apex, LWC, Scripts)
- [ ] Are there integration points? (API, Webhooks, External Systems)
- [ ] Are there data migration or seeding requirements?
- [ ] Is there a UI/UX change requiring design review?

---

### QA NOTES
- **Impacted Areas:** [List functional areas affected]
- **Proposed Regression Tests:** [Describe test scenarios]
- **Related Test Links:** [TestRail, Confluence, etc. — or "TBD"]

---

### OPEN QUESTIONS
At least one question per Acceptance Criterion. Add more as needed.
1. [Question]
2. [Question]
3. [Question]

---

### DEFINITION OF DONE
Plain business language. Anyone reading this should understand what is being delivered.
- [ ] [Deliverable 1]
- [ ] [Deliverable 2]
- [ ] [Deliverable 3]
```

---

### Spike Template

```
## Spike: [Investigation Topic]

### ESTIMATED EFFORT
- **Story Points:** [Usually 3 or 5, time-boxed]
- **Rationale:** [Explain uncertainty drivers]

---

### OBJECTIVE
[What are we trying to learn or decide? What outcome does this investigation unlock?]

### BACKGROUND / CONTEXT
[Why is this investigation needed now? What risk, dependency, or mandate is driving it?]

---

### KEY INVESTIGATION AREAS
1. **[Area 1]:** [Specific unknowns to resolve]
2. **[Area 2]:** [Specific unknowns to resolve]
3. **[Area 3]:** [Specific unknowns to resolve]

---

### DELIVERABLES (Definition of Done)
The spike is complete when these artifacts exist:
1. [Artifact 1 — e.g., Technical Assessment Document]
2. [Artifact 2 — e.g., Implementation Estimation in Story Points]
3. [Artifact 3 — e.g., Go/No-Go Recommendation]
```

---

### Epic Template

```
## Epic: [High-Level Business Initiative Name]

### BUSINESS GOAL & VALUE
[Measurable objective. What KPI or strategic outcome does this Epic drive?]

---

### AFFECTED PLATFORM & USERS
- **Platform:** [e.g., Salesforce Service Cloud — Service Console, Digital Engagement]
- **Target Personas:** [List primary users/stakeholders]

---

### IN-SCOPE (High-Level Features)
- [Feature 1]
- [Feature 2]
- [Feature 3]

### OUT-OF-SCOPE (Explicit Exclusions)
- [Feature]: [Why excluded — different Epic, later phase, dependency, etc.]

---

### RELATED ARTIFACTS
- **Spikes Required:** [Spike IDs or planned topics]
- **Predecessor Epics:** [Epics that must be completed first]

---

### DEFINITION OF DONE
The Epic is complete when:
- [ ] All related User Stories are accepted by the Product Owner and deployed to Production.
- [ ] The key Business Goal is measurable via reporting.
- [ ] [Any specific final step, e.g., training materials signed off]
```

---

### Bug Template

```
## Bug: [Specific Bug Summary]

### ESTIMATED EFFORT
- **Story Points:** [1 / 2 / 3 / 5 / 8]
- **Rationale:** [Reference complexity drivers from the estimation scale]

---

### DETAILED DESCRIPTION
- **What is the bug?** [Unexpected behavior, clearly described]
- **Where did it occur?** [Exact location: page, module, feature]
- **When does it happen?** [Frequency, trigger conditions]

---

### INITIAL CONDITIONS
- [Starting state, e.g., "Logged in as Tier 1 Agent, record status = Active"]

### STEPS TO REPRODUCE
1. [Step 1]
2. [Step 2]
3. [Continue until bug is replicated]

---

### EXPECTED vs. ACTUAL RESULTS
- **Expected:** [What should happen]
- **Actual:** [What actually happens]

---

### ENVIRONMENT DETAILS
- **OS:** [e.g., Windows 11, macOS]
- **Browser:** [e.g., Chrome 124]
- **Device:** [e.g., Desktop]

---

### SUPPORTING EVIDENCE
[Reference screenshots, videos, logs — or "Awaiting upload"]
```

---

## INVEST Checklist (Self-Validate Before Outputting)

Before presenting any story, mentally verify:

- **Independent** — Can it be built and delivered without another story being done first?
- **Negotiable** — Is the scope flexible enough for team discussion?
- **Valuable** — Does the "so that" clause clearly state business or user value?
- **Estimable** — Is there enough clarity to assign story points confidently?
- **Small** — Can it be completed within a single sprint?
- **Testable** — Can the acceptance criteria be verified by a QA engineer?

If any principle fails, revise the story before outputting it.
