# GSTIC Framework — Claude Code Instructions

## What This Is

This repo contains the **GSTIC Strategic Planning Framework** — a structured methodology for developing comprehensive business and product strategies. GSTIC stands for:

- **G**oals — Define what success looks like (business objectives, KPIs, benchmarks)
- **S**trategy — Identify the path to achieve goals (target audience, value proposition, positioning)
- **T**actics — Specify the marketing mix and product levers (product, price, incentives, communication, distribution)
- **I**mplementation — Build the execution plan (roadmap, resources, timelines, dependencies)
- **C**ontrol — Establish measurement and feedback loops (metrics, dashboards, review cadence, iteration triggers)

## How to Use This Framework

When a user enters this repo and asks to "run GSTIC" or "start a GSTIC plan" for a project:

1. **Read the kickoff prompt** at `prompts/kickoff.md` — this is your orchestration guide
2. **Activate agents sequentially** — each phase has a dedicated agent persona in `agents/`
3. **Use templates** from `templates/` to structure outputs at each phase
4. **Follow phase transitions** defined in `prompts/phase-transitions.md`

## Agent Activation Rules

| Phase | Agent File | Role |
|-------|-----------|------|
| Goals | `agents/strategist.md` | Defines objectives, KPIs, and success criteria |
| Strategy | `agents/strategist.md` | Identifies target segments, value prop, positioning |
| Tactics | `agents/tactician.md` | Develops the marketing/product mix |
| Implementation | `agents/tactician.md` | Builds roadmap, assigns resources, sets timelines |
| Control | `agents/analyst.md` | Designs measurement framework and feedback loops |

## Orchestration Behavior

- **Always start with Goals.** Never skip ahead.
- **Each phase must produce a deliverable** before transitioning to the next phase.
- **Ask clarifying questions** at the start of each phase — don't assume context.
- **Reference prior phase outputs** when working on subsequent phases.
- **Offer to iterate** at the end of each phase before moving on.
- If the user says "full GSTIC" or "run all phases," proceed through all five sequentially with brief confirmation between each.
- If the user names a specific phase (e.g., "just do Tactics"), jump directly to that phase but warn if prerequisite phases haven't been completed.

## Output Preferences

- Use Markdown for all deliverables
- Include tables for KPIs, timelines, and comparison matrices
- Keep language direct and actionable — no filler
- Tailor depth to the user's context (enterprise product management, B2B, platform strategy)
- When applicable, reference frameworks like Hamilton Helmer's 7 Powers, Jobs-to-Be-Done, or AI Canvas

## Project Context Detection

If the user mentions a specific project, try to understand:
- Is this B2B or B2C?
- Is this a new initiative or optimization of an existing one?
- What's the organizational scale (startup, mid-market, enterprise)?
- Are there existing metrics or baselines?

Use these signals to calibrate the depth and vocabulary of each phase.
