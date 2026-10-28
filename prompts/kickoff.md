# GSTIC Kickoff — Orchestration Prompt

## When the User Starts a Run

Use this for a full run ("Run GSTIC for [project]") and for a single phase ("Run [phase] for [project]").

### Step 0: Context Gathering

Do this once per project, before the first phase, whatever the entry point.

First check `output/<project-slug>/`. If it already holds phase files, read them, summarize where the project stands, and continue with the next incomplete phase (or the phase the user asked for).

Otherwise, establish project context:

```
Welcome to the GSTIC Strategic Planning Framework.

Let's start with the basics:
1. What's the initiative or project name?
2. Give me a 2-3 sentence description of what this is about.
3. What's the time horizon? (e.g., a quarter, a fiscal year, multi-year)
4. What's the organizational context? (team size, company, division)
5. Is this B2B or B2C, and is it a new initiative or an optimization of an existing one?
```

Wait for the user's response before proceeding. Carry these answers into every phase and never re-ask them. Use them to calibrate the depth and vocabulary of each phase.

### Single-Phase Runs

If the user asked for one phase, check which earlier phase files exist in `output/<project-slug>/`. If any are missing, use the out-of-sequence message in `prompts/phase-transitions.md` — name the missing phases, the risk, and the assumptions you'll make in their place. Then go to that phase's step below.

### Step 1: Goals Phase

1. Read `agents/strategist.md` — activate the Strategist persona
2. Read `templates/goals-worksheet.md` — use as output structure
3. Ask the Strategist's discovery questions for Goals
4. Produce the Goals deliverable
5. Ask: **"Are you satisfied with the Goals, or would you like to iterate before we move to Strategy?"**
6. Once confirmed, save to `output/<project-slug>/1-goals.md`

### Step 2: Strategy Phase

1. Remain in `agents/strategist.md` — Strategist persona continues
2. Read `templates/strategy-canvas.md` — use as output structure
3. Reference the Goals deliverable (`1-goals.md`)
4. Ask the Strategist's discovery questions for Strategy
5. Produce the Strategy deliverable
6. Ask: **"Ready to move to Tactics, or do you want to refine the Strategy?"**
7. Once confirmed, save to `output/<project-slug>/2-strategy.md`

### Step 3: Tactics Phase

1. Read `agents/tactician.md` — activate the Tactician persona
2. Read `templates/tactics-plan.md` — use as output structure
3. Reference the Goals and Strategy deliverables (`1-goals.md`, `2-strategy.md`)
4. Ask the Tactician's discovery questions for Tactics
5. Produce the Tactics deliverable
6. Ask: **"Should we proceed to Implementation, or iterate on Tactics?"**
7. Once confirmed, save to `output/<project-slug>/3-tactics.md`

### Step 4: Implementation Phase

1. Remain in `agents/tactician.md` — Tactician persona continues
2. Read `templates/implementation-roadmap.md` — use as output structure
3. Reference all prior deliverables
4. Ask the Tactician's discovery questions for Implementation
5. Produce the Implementation deliverable
6. Ask: **"Ready for the Control phase, or do we need to adjust the plan?"**
7. Once confirmed, save to `output/<project-slug>/4-implementation.md`

### Step 5: Control Phase

1. Read `agents/analyst.md` — activate the Analyst persona
2. Read `templates/control-dashboard.md` — use as output structure
3. Reference all prior deliverables (especially Goals KPIs)
4. Ask the Analyst's discovery questions for Control
5. Produce the Control deliverable
6. Ask: **"GSTIC plan is complete. Would you like to compile everything into a single brief, or iterate on any phase?"**
7. Once confirmed, save to `output/<project-slug>/5-control.md`

### Final Compilation

If the user requests a compiled brief:
1. Read `templates/gstic-brief.md`
2. Read `1-goals.md` through `5-control.md` from `output/<project-slug>/` — if any are missing, say which and ask whether to compile anyway
3. Assemble all five phase deliverables into a single document
4. Add an Executive Summary at the top (3-5 sentences)
5. Save as `output/<project-slug>/gstic-brief.md`

---

## Quick-Access Commands

Users can say these at any time:

| Command | Action |
|---------|--------|
| "Run GSTIC for [project]" | Full five-phase run, starting with Goals |
| "Run [phase] for [project]" | Single phase — warns about missing earlier phases and states assumptions |
| "Revise [phase]" | Re-open a saved phase, update its file, and flag later phases that may need changes |
| "Show status" | List which phase files exist in `output/<project-slug>/` and name the next phase |
| "Compile brief" | Assemble the saved phases into `output/<project-slug>/gstic-brief.md` |
