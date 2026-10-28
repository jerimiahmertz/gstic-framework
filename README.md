# GSTIC Strategic Planning Framework

A structured, AI-driven strategic planning framework designed to run interactively via [Claude Code](https://code.claude.com/docs). GSTIC walks you through five sequential phases to develop comprehensive business and product strategies — from defining objectives through measurement design.

GSTIC (Goals, Strategy, Tactics, Implementation, Control) was developed by Alexander Chernev at the Kellogg School of Management. This repo turns it into a guided, conversational workflow.

> **Need market discovery first?** [MAGSTIC](https://github.com/jerimiahmertz/magstic-framework) is the extended version. It adds a Phase 0 (market attractiveness, opportunity sizing, customer discovery, positioning, business model) before these five phases. This repo stays the lighter, GSTIC-only version.

## What is GSTIC?

| Phase | Focus | Key Question |
|-------|-------|-------------|
| **G** — Goals | Objectives & KPIs | What does success look like? |
| **S** — Strategy | Audience & positioning | Who are we targeting and why will they choose us? |
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

Claude Code loads `CLAUDE.md` when it starts in this folder. `CLAUDE.md` points it to the kickoff prompt, which runs the five phases in order.

## How It Works

`CLAUDE.md` and the kickoff prompt tell Claude which of these files to read at each phase:

**Agents** (`agents/`) — Persona definitions that shape how Claude thinks during each phase. The Strategist pushes for specificity in goals and positioning. The Tactician builds executable plans. The Analyst designs measurement systems that drive decisions. They are plain Markdown files that Claude adopts in the main conversation, so every phase stays a back-and-forth with you.

**Templates** (`templates/`) — Structured output formats for each phase. These ensure deliverables are consistent, complete, and traceable across phases.

**Prompts** (`prompts/`) — Orchestration logic that controls phase sequencing, exit criteria, and context handoffs.

**Saved deliverables** (`output/`) — Each phase is saved to `output/<project>/` once you confirm it (`1-goals.md` through `5-control.md`). You can stop, come back in a new session, revise a phase, or compile the brief later. `output/` is git-ignored, so your plans stay on your machine.

## Repo Structure

```
gstic-framework/
├── CLAUDE.md                      # Orchestration instructions (Claude Code loads this)
├── README.md
├── LICENSE
├── agents/
│   ├── strategist.md              # Goals & Strategy phases
│   ├── tactician.md               # Tactics & Implementation phases
│   └── analyst.md                 # Control phase
├── templates/
│   ├── goals-worksheet.md         # Phase 1 output
│   ├── strategy-canvas.md         # Phase 2 output
│   ├── tactics-plan.md            # Phase 3 output
│   ├── implementation-roadmap.md  # Phase 4 output
│   ├── control-dashboard.md       # Phase 5 output
│   └── gstic-brief.md             # Compiled brief (all phases)
├── prompts/
│   ├── kickoff.md                 # Entry orchestration
│   └── phase-transitions.md       # Exit criteria and phase handoffs
├── examples/
│   └── tidewell-self-serve-gstic.md  # Worked example (fictional company)
└── output/                        # Your saved deliverables (created on first run, git-ignored)
```

## Usage Modes

| Command | What It Does |
|---------|-------------|
| `Run GSTIC for [project]` | Full five-phase run, starting with Goals |
| `Run [phase] for [project]` | Single phase — warns about missing earlier phases and states its assumptions |
| `Revise [phase]` | Re-open a saved phase, update it, and flag later phases that may need changes |
| `Show status` | List which phases are saved for the project and name the next one |
| `Compile brief` | Assemble the saved phases into one document |

## Tactics: Five Levers

Chernev's GSTIC defines seven tactics: product, service, brand, price, incentives, communication, and distribution. This framework uses five — **Product, Price, Incentives, Communication, Distribution** — to keep the Tactics phase manageable. Service decisions sit under Product, and brand decisions under Communication. To use all seven, add Service and Brand sections to `templates/tactics-plan.md` and `agents/tactician.md`, and update the Tactics exit criteria in `prompts/phase-transitions.md`.

## Integrated Frameworks

GSTIC phases can pull in complementary frameworks depending on context:

- **Goals** — OKRs, Balanced Scorecard
- **Strategy** — Hamilton Helmer's 7 Powers, Jobs-to-Be-Done, Value Proposition Canvas, AI Canvas
- **Tactics** — Growth Loops, RICE / ICE / MoSCoW prioritization
- **Implementation** — Stage-gated rollout, RACI, Agile/SAFe
- **Control** — North Star Metric, HEART Framework

## Customization

Add new agent personas in `agents/` for domain-specific roles (e.g., `growth-engineer.md` for PLG motions) and list them in the agent table in `CLAUDE.md`. Add templates in `templates/` for recurring deliverable formats. Modify `CLAUDE.md` to change orchestration behavior, output preferences, or framework integrations.

## License

[MIT](LICENSE)
