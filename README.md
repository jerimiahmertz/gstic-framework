## GSTIC Strategic Planning Framework
A structured framework for developing comprehensive business and product strategies, designed to run interactively via Claude Code.

# What is GSTIC?
GSTIC is a five-phase strategic planning methodology:

Phase	Focus	Key Question
Goals	Objectives & KPIs	What does success look like?
Strategy	Audience & positioning	Who are we targeting and why will they choose us?
Tactics	Marketing & product mix	What levers do we pull?
Implementation	Roadmap & execution	How and when do we deliver?
Control	Measurement & iteration	How do we know it's working?
Quick Start
# Clone the repo
git clone https://github.com/YOUR_USERNAME/gstic-framework.git

# Navigate into the repo
cd gstic-framework

# Launch Claude Code
claude

# Then say:
# "Run GSTIC for [your project name]"
Claude Code reads CLAUDE.md automatically and orchestrates the five-phase workflow.

Repo Structure
gstic-framework/
├── CLAUDE.md                      # Claude Code orchestration instructions
├── README.md                      # This file
├── agents/
│   ├── strategist.md              # Goals & Strategy phase persona
│   ├── tactician.md               # Tactics & Implementation phase persona
│   └── analyst.md                 # Control & measurement phase persona
├── templates/
│   ├── gstic-brief.md             # Full GSTIC planning template (all phases)
│   ├── goals-worksheet.md         # Phase 1: Goals definition
│   ├── strategy-canvas.md         # Phase 2: Strategy development
│   ├── tactics-plan.md            # Phase 3: Tactics specification
│   ├── implementation-roadmap.md  # Phase 4: Execution planning
│   └── control-dashboard.md       # Phase 5: Measurement design
├── prompts/
│   ├── kickoff.md                 # Entry orchestration prompt
│   └── phase-transitions.md       # Inter-phase transition logic
└── examples/
    └── warm-leads-gstic.md        # Example: Enterprise lead gen initiative
Usage Modes
Full Run
Say: "Run GSTIC for [project]" — walks through all five phases sequentially.

Single Phase
Say: "Run the Strategy phase for [project]" — jumps to a specific phase.

Iteration
Say: "Revise the Tactics for [project]" — re-enters a completed phase to refine.

Customization
Add agents in agents/ for domain-specific personas (e.g., a growth-engineer.md for PLG motions)
Add templates in templates/ for recurring deliverable formats
Modify CLAUDE.md to change orchestration behavior, output preferences, or framework integrations
Framework Integrations
GSTIC phases can be enriched with complementary frameworks:

Goals → OKRs, Balanced Scorecard
Strategy → Hamilton Helmer's 7 Powers, Jobs-to-Be-Done, AI Canvas
Tactics → Chernev Marketing Mix, Growth Loops
Implementation → RICE Scoring, Agile/SAFe
Control → North Star Metric, HEART Framework
License
MIT — use freely, adapt to your needs.
