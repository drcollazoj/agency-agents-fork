# /revenue-audit — Practice Revenue Audit

Run a full revenue analysis for a physician practice using the Healthcare Revenue Strategist framework.

## What This Skill Does

Collects practice data from the user, then produces:
1. **Revenue ceiling analysis** — what's the maximum this practice can earn under its current insurance-dependent model
2. **Top 3 cash-pay service recommendations** — matched to specialty, location, and infrastructure with unit economics
3. **12-month projection** — conservative revenue model showing the impact of adding cash-pay services

## Activation

When the user runs `/revenue-audit`, ask these questions one at a time (don't overwhelm with a form):

1. "What is the physician's specialty?" (e.g., Family Medicine, Internal Medicine, Cardiology)
2. "Which municipality in Puerto Rico?" (e.g., San Juan, Bayamón, Caguas, Ponce)
3. "How many patients per day on average?"
4. "What's the approximate payer mix? (% MA, % commercial, % Medicaid, % self-pay)"
5. "Current monthly gross revenue (approximate)?"
6. "Staff count and rough monthly payroll?"
7. "Any existing cash-pay services? If yes, which ones?"
8. "Any equipment or space currently underutilized?"

## Output Format

Use the Revenue Audit template from `specialized/healthcare-revenue-strategist.md`:

```markdown
# Practice Revenue Audit — [Specialty], [Municipality]

## Current State
[Fill with provided data]

## Revenue Ceiling Analysis
[Calculate max insurance-dependent revenue based on panel size, cap rates, and payer mix]
[Explain why the ceiling exists and what's driving it in this municipality]

## Cash-Pay Service Opportunities

### Service 1: [Name]
[Unit economics: startup cost, monthly cost, price, volume, revenue, profit, breakeven]
[Fit score 1-10 with rationale]

### Service 2: [Name]
[Same structure]

### Service 3: [Name]
[Same structure]

## Recommended Service Stack
[Primary + secondary with combined monthly impact]

## 12-Month Revenue Projection
| Month | Insurance Revenue | Cash-Pay Revenue | Total | Notes |
[Conservative scenario]

## Implementation Priority
[3 steps in order with rationale]
```

## Key Rules

- Use conservative estimates — never inflate projections
- Reference PR-specific market dynamics (MA penetration, IPA structures) where relevant
- If a service doesn't fit the practice profile, say so and explain why
- Include startup costs and ramp-up time in every projection
- If payer mix is 70%+ MA, explicitly calculate the revenue ceiling before recommending cash-pay services
