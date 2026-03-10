# MedZone PR — Claude Code Guide

## What This Repo Is

This is **The Agency** — a curated collection of 68+ specialized AI agent personalities — forked and extended for **MedZone PR**, a healthcare management consulting agency in Puerto Rico founded by Dr. James Collazo. The repo contains agent definitions that plug directly into Claude Code, Cursor, Aider, and other AI development tools, plus a planned Next.js marketing website.

MedZone PR helps independent physicians in Puerto Rico build cash-pay revenue streams, optimize practice operations, and grow their businesses beyond the ceiling imposed by Medicare Advantage capitation.

---

## Directory Structure

| Directory | Contents |
|-----------|----------|
| `specialized/` | Custom MedZone PR agents + general specialized agents |
| `engineering/` | 11 software engineering agents |
| `design/` | 8 design and UX agents |
| `marketing/` | 11 marketing and content agents |
| `product/` | 4 product management agents |
| `project-management/` | 5 project and studio management agents |
| `testing/` | 8 QA and testing agents |
| `support/` | 6 support, finance, and compliance agents |
| `spatial-computing/` | 6 XR and spatial computing agents |
| `strategy/` | Multi-agent orchestration playbooks and runbooks |
| `examples/` | Multi-agent workflow examples |
| `integrations/` | Converted outputs for each AI tool |
| `scripts/` | Conversion, installation, and lint scripts |
| `website/` | Next.js marketing website for MedZone PR (in progress) |
| `.claude/skills/` | Custom slash-command skills for Claude Code |

---

## MedZone PR Custom Agents

Four agents built specifically for MedZone PR's consulting practice. All live in `specialized/`.

### Healthcare Revenue Strategist
**File**: `specialized/healthcare-revenue-strategist.md`
**Use when**: Analyzing a physician's revenue ceiling, identifying cash-pay service opportunities, building financial models for new service lines.
**Core capability**: Takes a practice's payer mix, patient volume, and specialty → outputs top 3 cash-pay service recommendations with unit economics and 12-month revenue projections.

### Puerto Rico Practice Consultant
**File**: `specialized/puerto-rico-practice-consultant.md`
**Use when**: Advising on IPA relationships, launching a new practice on the island, navigating PR-specific regulations, licensing (COSSMO), or municipal market analysis.
**Core capability**: Understands the 70%+ MA market concentration, IPA dynamics, cultural business norms, and operational realities specific to Puerto Rico.

### Medical Business Writer
**File**: `specialized/medical-business-writer.md`
**Use when**: Generating client-facing proposals, physician case studies, thought leadership content, email sequences, or website copy.
**Core capability**: Writes in a physician-to-physician voice — credible, specific, no buzzwords. Fully bilingual (Spanish/English). Uses real numbers, never vague promises.

### Practice Launch Orchestrator
**File**: `specialized/practice-launch-orchestrator.md`
**Use when**: Coordinating the end-to-end launch of a new physician practice — from initial feasibility through first profitable month.
**Core capability**: Manages the critical path (credentialing starts Week 1), coordinates the other three agents in sequence, and produces weekly status reports with clear decision points.

---

## Agent File Format

All agent files follow this structure:

### YAML Frontmatter (required)
```yaml
---
name: Agent Name
description: One-line specialty summary (appears in tool UIs)
color: "#hexcode" or colorname
tools: ToolA, ToolB  # optional — limits available tools
---
```

### Body Sections (required)

| Section | Emoji | Purpose |
|---------|-------|---------|
| Identity & Memory | 🧠 | Role, personality, experience |
| Core Mission | 🎯 | 2-3 primary responsibilities with specific deliverables |
| Critical Rules | 🚨 | Non-negotiable constraints and approach patterns |
| Deliverables | 📋 | Templates, code samples, frameworks with real examples |
| Workflow Process | 🔄 | Step-by-step execution phases |
| Communication Style | 💭 | Voice, tone, example phrasings |
| Learning & Memory | 🔄 | Patterns to remember and build on |
| Success Metrics | 🎯 | Quantified outcomes that define success |
| Advanced Capabilities | 🚀 | Specialized techniques and mastery areas |

### Naming Convention
```
division/division-agent-slug.md
```
Examples:
- `specialized/healthcare-revenue-strategist.md`
- `engineering/engineering-code-reviewer.md`
- `marketing/marketing-content-creator.md`

---

## Creating a New Agent

1. Choose the appropriate division directory
2. Create the file: `division/division-agent-slug.md`
3. Add YAML frontmatter (`name`, `description`, `color` are required)
4. Fill all required body sections using the structure above
5. Include concrete examples — code, templates, or frameworks (not abstract advice)
6. Add quantified success metrics (specific numbers, not vague outcomes)
7. Run the linter:
   ```bash
   bash scripts/lint-agents.sh
   ```
8. Fix any warnings before committing

---

## Skills (Slash Commands)

Custom skills are in `.claude/skills/`. Use them in Claude Code with `/skill-name`.

### `/revenue-audit`
Runs a structured revenue analysis for a physician practice. Collects practice data and outputs a full audit with revenue ceiling analysis, top 3 cash-pay service recommendations, and 12-month projections.

### `/client-proposal`
Generates a tailored MedZone PR engagement proposal. Takes physician name, specialty, municipality, and pain points → outputs a polished proposal with ROI projections and service recommendations.

### `/new-agent`
Scaffolds a new agent file following repo conventions. Asks for name, division, specialty, and color → creates a properly formatted `.md` file with all sections pre-filled.

---

## Linting & Validation

```bash
bash scripts/lint-agents.sh
```

Checks:
- YAML frontmatter has `name`, `description`, `color`
- Body has required sections (Identity, Mission, Rules)
- File has sufficient content (50+ words)

Run before every commit that adds or modifies an agent.

---

## Multi-Tool Conversion

```bash
bash scripts/convert.sh
```

Converts all agent `.md` files into tool-specific formats:
- **Claude Code**: `.md` files (already compatible)
- **Cursor**: `.mdc` rule files → `integrations/cursor/`
- **Aider**: Single `CONVENTIONS.md` → `integrations/aider/`
- **Windsurf**: Single `.windsurfrules` → `integrations/windsurf/`
- **Antigravity (Gemini)**: `SKILL.md` files → `integrations/antigravity/`

Run after adding new agents to regenerate integration outputs.

---

## Installation

```bash
bash scripts/install.sh
```

Interactive installer that detects which AI tools are present and copies agents to the correct locations (e.g., `~/.claude/agents/` for Claude Code).

---

## Website (MedZone PR Next.js Site)

**Directory**: `website/`
**Status**: Planned — awaiting design direction from Dr. Collazo

**Tech stack**:
- Next.js (App Router, TypeScript)
- `next-intl` for Spanish/English i18n (Spanish-first)
- Tailwind CSS for styling
- Nodemailer for contact form email delivery
- Professional security baseline: CSRF, rate limiting, CSP headers, input validation

**Local development** (once scaffolded):
```bash
cd website
npm install
npm run dev
# → http://localhost:3000
```

**Hostinger deployment**: See `website/README.md` for step-by-step deployment to Hostinger Node.js VPS.

---

## Agent Design Principles

Agents in this repo must follow these principles (from the Agency's founding philosophy):

1. **Strong personality, not generic** — Every agent has a distinct voice and character
2. **Concrete deliverables** — Real templates, code, frameworks. Never vague guidance.
3. **Quantified success metrics** — Specific numbers, not "improves outcomes"
4. **Domain expertise** — Deep specialization, not shallow coverage
5. **Proven workflows** — Battle-tested processes, not theoretical advice
6. **PR market specificity** — MedZone PR agents must account for Puerto Rico's unique market dynamics

---

## Contribution Workflow

```
1. git checkout -b your-feature-branch
2. Create or edit agent in appropriate division
3. bash scripts/lint-agents.sh   # must pass
4. git add <file>
5. git commit -m "feat: add [Agent Name] to [division]"
6. git push -u origin your-feature-branch
7. Open PR against main
```

**Branch naming**: Feature branches should describe what's being added, e.g., `feat/add-dental-specialist-agent`.

---

## Key Files Reference

| File | Purpose |
|------|---------|
| `scripts/lint-agents.sh` | Validate agent files |
| `scripts/convert.sh` | Convert agents for all tools |
| `scripts/install.sh` | Install agents to tool directories |
| `strategy/nexus-strategy.md` | Multi-agent coordination vision |
| `examples/workflow-landing-page.md` | Example 4-agent landing page workflow |
| `examples/workflow-startup-mvp.md` | Example MVP development workflow |
| `CONTRIBUTING.md` | Detailed contribution guidelines |
