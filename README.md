# GSTIC Strategic Planning Framework

A structured, AI-driven strategic planning framework designed to run interactively via [Claude Code](https://docs.anthropic.com/en/docs/claude-code). GSTIC walks you through five sequential phases to develop comprehensive business and product strategies — from defining objectives through measurement design.

## What is GSTIC?

| Phase | Focus | Key Question |
|-------|-------|-------------|
| **G** — Goals | Objectives & KPIs | What does success look like? |
| **S** — Strategy | Audience & positioning | Who are we targeting and why us? |
| **T** — Tactics | Marketing & product mix | What levers do we pull? |
| **I** — Implementation | Roadmap & execution | How and when do we deliver? |
| **C** — Control | Measurement & iteration | How do we know it's working? |

Each phase produces a structured deliverable. Each deliverable traces back to the ones before it — tactics link to strategy, strategy links to goals, control covers every KPI.

## Quick Start

```bash
git clone https://github.com/jerimiahmertz/gstic-framework.git
cd gstic-framework
claude
```

Then say:

```
Run GSTIC for [your project name]
```

Claude Code reads `CLAUDE.md` on entry and orchestrates the full five-phase workflow automatically.

## How It Works

The framework uses three components that Claude Code picks up from the repo:

**Agents** (`agents/`) — Persona definitions that shape how Claude thinks during each phase. The Strategist pushes for specificity in goals and positioning. The Tactician builds executable plans. The Analyst designs measurement systems that drive decisions.

**Templates** (`templates/`) — Structured output formats for each phase. These ensure deliverables are consistent, complete, and traceable across phases.

**Prompts** (`prompts/`) — Orchestration logic that controls phase sequencing, transition criteria, and context handoffs.

## Repo Structure

```
gstic-framework/
├── CLAUDE.md                      # Orchestration instructions (Claude Code reads this)
├── README.md
├── agents/
│   ├── strategist.md              # Goals & Strategy phases
│   ├── tactician.md               # Tactics & Implementation phases
│   └── analyst.md                 # Control phase
├── templates/
│   ├── gstic-brief.md             # Full compiled brief (all phases)
│   ├── goals-worksheet.md         # Phase 1 output
│   ├── strategy-canvas.md         # Phase 2 output
│   ├── tactics-plan.md            # Phase 3 output
│   ├── implementation-roadmap.md  # Phase 4 output
│   └── control-dashboard.md       # Phase 5 output
├── prompts/
│   ├── kickoff.md                 # Entry orchestration
│   └── phase-transitions.md       # Phase handoff logic
└── examples/
    └── warm-leads-gstic.md        # Worked example
```

## Usage Modes

| Command | What It Does |
|---------|-------------|
| `Run GSTIC for [project]` | Full five-phase sequential run |
| `Run the Strategy phase for [project]` | Single phase (warns if prerequisites incomplete) |
| `Revise the Tactics` | Re-enter a completed phase to refine |
| `Show status` | See which phases are done |
| `Compile brief` | Assemble all phases into one document |
| `Skip to [phase]` | Jump ahead with dependency warning |

## Integrated Frameworks

GSTIC phases can pull in complementary frameworks depending on context:

- **Goals** — OKRs, Balanced Scorecard
- **Strategy** — Hamilton Helmer's 7 Powers, Jobs-to-Be-Done, AI Canvas
- **Tactics** — Chernev Marketing Mix, Growth Loops
- **Implementation** — RICE Scoring, Agile/SAFe phasing
- **Control** — North Star Metric, HEART Framework

## Customization

Add new agent personas in `agents/` for domain-specific roles (e.g., `growth-engineer.md` for PLG motions). Add templates in `templates/` for recurring deliverable formats. Modify `CLAUDE.md` to change orchestration behavior, output preferences, or framework integrations.

## License

MIT
