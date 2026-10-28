# GSTIC Framework — Claude Code Instructions

## What This Is

This repo contains the **GSTIC Strategic Planning Framework** — a structured methodology for developing comprehensive business and product strategies, originally developed by Alexander Chernev (Kellogg School of Management). GSTIC stands for:

- **G**oals — Define what success looks like (business objectives, KPIs, benchmarks)
- **S**trategy — Identify the path to achieve goals (target audience, value proposition, positioning)
- **T**actics — Specify the marketing mix and product levers (product, price, incentives, communication, distribution)
- **I**mplementation — Build the execution plan (roadmap, resources, timelines, dependencies)
- **C**ontrol — Establish measurement and feedback loops (metrics, dashboards, review cadence, iteration triggers)

## How to Use This Framework

When a user asks to "run GSTIC", "start a GSTIC plan", or run a specific phase for a project:

1. **Read the kickoff prompt** at `prompts/kickoff.md` — this is your orchestration guide
2. **Gather context once** (kickoff Step 0) before the first phase, whatever the entry point
3. **Activate agents** — each phase has a dedicated agent persona in `agents/`
4. **Use templates** from `templates/` to structure outputs at each phase
5. **Follow phase transitions** defined in `prompts/phase-transitions.md`
6. **Save each deliverable** to `output/<project-slug>/` once the user confirms it

## Agent Activation Rules

| Phase | Agent File | Role |
|-------|-----------|------|
| Goals | `agents/strategist.md` | Defines objectives, KPIs, and success criteria |
| Strategy | `agents/strategist.md` | Identifies target segments, value prop, positioning |
| Tactics | `agents/tactician.md` | Develops the marketing/product mix |
| Implementation | `agents/tactician.md` | Builds roadmap, assigns resources, sets timelines |
| Control | `agents/analyst.md` | Designs measurement framework and feedback loops |

## Commands

| Command | Action |
|---------|--------|
| "Run GSTIC for [project]" | Full five-phase run, starting with Goals |
| "Run [phase] for [project]" | Single phase — warns about missing earlier phases and states assumptions |
| "Revise [phase]" | Re-open a saved phase, update its file, and flag later phases that may need changes |
| "Show status" | List which phase files exist in `output/<project-slug>/` and name the next phase |
| "Compile brief" | Assemble the saved phases into `output/<project-slug>/gstic-brief.md` |

## Orchestration Behavior

- **Start with Goals by default.** A full run goes Goals → Strategy → Tactics → Implementation → Control, with a brief confirmation between phases.
- **A named phase can run out of order.** If the user asks for a specific phase (e.g., "just do Tactics"), run it — but first warn which earlier phases are missing and state the assumptions you're making in their place.
- **Each phase must produce a deliverable** before transitioning to the next phase.
- **Ask clarifying questions** at the start of each phase — but never re-ask what Step 0 or an earlier phase already answered.
- **Reference prior phase outputs** when working on subsequent phases — read them from `output/<project-slug>/`.
- **Offer to iterate** at the end of each phase before moving on.

## Saving Deliverables

| Phase | File |
|-------|------|
| Goals | `output/<project-slug>/1-goals.md` |
| Strategy | `output/<project-slug>/2-strategy.md` |
| Tactics | `output/<project-slug>/3-tactics.md` |
| Implementation | `output/<project-slug>/4-implementation.md` |
| Control | `output/<project-slug>/5-control.md` |
| Compiled brief | `output/<project-slug>/gstic-brief.md` |

- `<project-slug>` is the project name in lowercase kebab-case (e.g., "Self-Serve Trial" → `self-serve-trial`).
- Save a phase only after the user confirms it. When a phase is revised, overwrite its file.
- If `output/` holds more than one project, ask which one the user means.
- `output/` is git-ignored, so deliverables stay on the user's machine.

## Output Preferences

- Use Markdown for all deliverables
- Include tables for KPIs, timelines, and comparison matrices
- Keep language direct and actionable — no filler
- Tailor depth and vocabulary to the context gathered in Step 0 (B2B or B2C, new or existing initiative, organizational scale)
- When applicable, reference frameworks like Hamilton Helmer's 7 Powers, Jobs-to-Be-Done, or AI Canvas

## Terminology

- **Phase** — one of the five GSTIC phases (1 Goals through 5 Control)
- **Stage** — a step in the Implementation roadmap (Stage 0 Discovery through Stage 3 Optimize)
- **Priority** — tactics are rated High / Med / Low
