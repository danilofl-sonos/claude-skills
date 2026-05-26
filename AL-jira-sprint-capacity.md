---
name: AL-jira-sprint-capacity
description: Calculate sprint capacity in the [X][Y] format used in sprint names. Use this skill whenever the user wants to calculate sprint capacity, team availability, sprint points, or the [X][Y] bracket numbers for a sprint. Trigger when the user mentions team members, OTO (out of office), capacity percentages, work days, or asks "what is our capacity for this sprint". Also trigger when the user shares a list of team members with availability details and wants to know the sprint capacity number.
---

# Sprint Capacity Calculator

Calculates the **[X][Y]** sprint capacity label, where:
- **X** = total capacity points (sum of each developer's effective availability)
- **Y** = number of work days in the sprint (default: 10)
The result is used in sprint names like: `WebSupport CY26 #11 [X][Y]`

---

## How to Calculate

### Step 1 – Identify active developers

Only count people with an **active development role**. Exclude PMs, QA (unless they code), designers, scrum masters, etc., unless the user confirms they count.

### Step 2 – Gather per-person inputs

For each developer, collect:

| Input | Meaning |
|---|---|
| **Team capacity** | Fraction of their time dedicated to *this* team (e.g. `1.0` = full, `0.5` = split 50/50) |
| **OTO days** | Number of sprint work days the person will be out (vacation, sick, public holidays, etc.) |

### Step 3 – Compute each person's capacity points

```
effective_capacity = team_capacity × (sprint_days - OTO_days) / sprint_days
```

Example: developer at 0.5 team capacity, out 2 days of a 10-day sprint:
```
0.5 × (10 - 2) / 10 = 0.5 × 0.8 = 0.40
```

### Step 4 – Sum and round

```
X = round(sum of all effective_capacity values, 2)
Y = sprint_days (usually 10)
```

Present the result as **[X][Y]**, e.g. `[4.60][10]`.

---

## Collecting Information

If the user hasn't provided all the details, ask for them in one message:

1. **Who are the developers on the team?** (names or count)
2. **Does everyone work 100% on this team, or is anyone split?** (if split, what fraction?)
3. **Is anyone OTO during this sprint?** (if yes, how many days each?)
4. **How many work days in the sprint?** (default = 10, confirm if unsure)
Keep the questions grouped — don't ask them one at a time across multiple turns.

---

## Output Format

After calculating, show:

1. A **per-person breakdown table** with columns: Name | Team Capacity | OTO Days | Effective Capacity
2. The **final result** clearly highlighted: `[X][Y]`
3. A one-line **plain-language summary**, e.g. "Your team has 4.60 capacity points over a 10-day sprint."
If any assumption was made (e.g. defaulting sprint days to 10), state it explicitly.

---

## Example

**Input:**
- Ana – 100% capacity, 0 OTO days
- Bruno – 100% capacity, 2 OTO days
- Carla – 50% capacity (split with another team), 0 OTO days
- Sprint = 10 days
**Calculation:**
| Name | Team Capacity | OTO Days | Effective Capacity |
|---|---|---|---|
| Ana | 1.00 | 0 | 1.00 × (10-0)/10 = **1.00** |
| Bruno | 1.00 | 2 | 1.00 × (10-2)/10 = **0.80** |
| Carla | 0.50 | 0 | 0.50 × (10-0)/10 = **0.50** |

**Total X = 2.30 → [2.30][10]**

---

## Edge Cases

- **Person on OTO for the full sprint**: effective capacity = 0. They still appear in the table with 0.
- **OTO days > sprint days**: Flag this as an error and ask the user to confirm.
- **Fractional OTO**: If someone is out half a day, accept decimals (e.g. 0.5 OTO days).
- **No developers active**: Return [0][Y] and note the team has no active development capacity.
