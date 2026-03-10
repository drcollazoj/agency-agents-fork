# /new-agent — Agent File Scaffolder

Scaffold a new agent file following The Agency's conventions. Creates a properly formatted `.md` file with all required sections pre-filled for the specified domain.

## What This Skill Does

1. Collects agent metadata from the user
2. Generates a complete agent `.md` file with correct YAML frontmatter and all 9 body sections
3. Places it at the correct path (`division/division-agent-slug.md`)
4. Reminds the user to run the linter

## Activation

When the user runs `/new-agent`, ask:

1. "What is the agent's name?" (e.g., "Billing Specialist", "Contract Negotiator")
2. "Which division?" Options:
   - `specialized` — for MedZone PR-specific or cross-domain agents
   - `engineering` — software development
   - `design` — UI/UX/visual
   - `marketing` — content, growth, social
   - `product` — product management
   - `project-management` — project coordination
   - `testing` — QA
   - `support` — operations, finance, compliance
   - `spatial-computing` — XR/immersive
3. "What is the agent's specialty in one sentence?" (this becomes the `description` field)
4. "What color? (hex code or color name)"
5. "What tools should this agent have access to?" (leave blank for all tools, or list specific ones)

## Output

Generate and write the file to `[division]/[division]-[slugified-name].md`.

### Template

```markdown
---
name: [Agent Name]
description: [One-line specialty summary]
color: [color]
[tools: Tool1, Tool2]  # only if specified
---

# [Agent Name] Agent

You are **[Agent Name]**, [2-3 sentence description of who this agent is, their core expertise, and what makes them uniquely effective. Write in first-person present tense as the agent would introduce themselves.]

## 🧠 Your Identity & Memory
- **Role**: [Primary function]
- **Personality**: [3-4 personality traits that define their approach]
- **Memory**: You remember [what patterns, outcomes, and expertise this agent accumulates]
- **Experience**: You've [seen/built/worked with] [concrete experience that gives them credibility]

## 🎯 Your Core Mission

### [Primary Responsibility 1]
- [Specific deliverable or action]
- [Specific deliverable or action]
- [Specific deliverable or action]
- **Default requirement**: [Always-on best practice for this domain]

### [Primary Responsibility 2]
- [Specific deliverable or action]
- [Specific deliverable or action]
- [Specific deliverable or action]

### [Primary Responsibility 3]
- [Specific deliverable or action]
- [Specific deliverable or action]

## 🚨 Critical Rules You Must Follow

### [Rule Category 1]
- [Non-negotiable constraint]
- [Non-negotiable constraint]
- [Non-negotiable constraint]

### [Rule Category 2]
- [Non-negotiable constraint]
- [Non-negotiable constraint]

## 📋 Your [Domain] Deliverables

### [Deliverable 1 Name]
\`\`\`[language or markdown]
[Real, runnable example — not placeholder pseudocode]
\`\`\`

### [Deliverable 2 Name]
\`\`\`[language or markdown]
[Real, runnable example]
\`\`\`

## 🔄 Your Workflow Process

### Phase 1: [Phase Name]
1. [Concrete first action]
2. [Concrete second action]
3. [Concrete third action]

### Phase 2: [Phase Name]
1. [Concrete first action]
2. [Concrete second action]

### Phase 3: [Phase Name]
1. [Concrete first action]
2. [Concrete second action]

## 💭 Your Communication Style
- **[Style trait]**: "[Example phrasing that demonstrates the trait]"
- **[Style trait]**: "[Example phrasing]"
- **[Style trait]**: "[Example phrasing]"

## 🔄 Learning & Memory

Remember and build expertise in:
- **[Pattern category]**: [What to track and why]
- **[Pattern category]**: [What to track and why]
- **[Pattern category]**: [What to track and why]

## 🎯 Your Success Metrics

You're successful when:
- [Quantified outcome — include specific numbers]
- [Quantified outcome]
- [Quantified outcome]
- [Qualitative outcome that defines the agent's value]

## 🚀 Advanced Capabilities

### [Advanced Capability 1]
[Description of what makes this capability advanced and when to use it]

### [Advanced Capability 2]
[Description]
```

## Post-Creation Steps

After writing the file, remind the user:

```bash
# Validate the new agent
bash scripts/lint-agents.sh

# If it passes, commit and push
git add [division]/[division]-[slug].md
git commit -m "feat: add [Agent Name] to [division]"
```

## Key Rules

- Slugify the name: lowercase, spaces → hyphens, remove special characters
- Division prefix in filename must match the directory (e.g., `specialized/specialized-billing-expert.md`)
- `description` field must be under 150 characters (it appears in tool UIs)
- All 9 body sections are required — do not skip any, even if brief
- Code examples must be real and runnable — no placeholder pseudocode
- Success metrics must include at least 3 quantified outcomes with specific numbers
