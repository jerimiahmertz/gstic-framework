# GSTIC Kickoff — Orchestration Prompt

## When the User Says "Run GSTIC"

Follow this sequence exactly:

### Step 0: Context Gathering

Before entering any phase, establish project context:

```
Welcome to the GSTIC Strategic Planning Framework.

Let's start with the basics:
1. What's the initiative or project name?
2. Give me a 2-3 sentence description of what this is about.
3. What's the time horizon? (e.g., Q1 2026, FY2026, multi-year)
4. What's the organizational context? (team size, company, division)
```

Wait for the user's response before proceeding.

### Step 1: Goals Phase

1. Read `agents/strategist.md` — activate the Strategist persona
2. Read `templates/goals-worksheet.md` — use as output structure
3. Ask the Strategist's discovery questions for Goals
4. Produce the Goals deliverable
5. Ask: **"Are you satisfied with the Goals, or would you like to iterate before we move to Strategy?"**

### Step 2: Strategy Phase

1. Remain in `agents/strategist.md` — Strategist persona continues
2. Read `templates/strategy-canvas.md` — use as output structure
3. Reference the Goals deliverable from Step 1
4. Ask the Strategist's discovery questions for Strategy
5. Produce the Strategy deliverable
6. Ask: **"Ready to move to Tactics, or do you want to refine the Strategy?"**

### Step 3: Tactics Phase

1. Read `agents/tactician.md` — activate the Tactician persona
2. Read `templates/tactics-plan.md` — use as output structure
3. Reference Goals and Strategy deliverables
4. Ask the Tactician's discovery questions for Tactics
5. Produce the Tactics deliverable
6. Ask: **"Should we proceed to Implementation, or iterate on Tactics?"**

### Step 4: Implementation Phase

1. Remain in `agents/tactician.md` — Tactician persona continues
2. Read `templates/implementation-roadmap.md` — use as output structure
3. Reference all prior deliverables
4. Ask the Tactician's discovery questions for Implementation
5. Produce the Implementation deliverable
6. Ask: **"Ready for the Control phase, or do we need to adjust the plan?"**

### Step 5: Control Phase

1. Read `agents/analyst.md` — activate the Analyst persona
2. Read `templates/control-dashboard.md` — use as output structure
3. Reference all prior deliverables (especially Goals KPIs)
4. Ask the Analyst's discovery questions for Control
5. Produce the Control deliverable
6. Ask: **"GSTIC plan is complete. Would you like to compile everything into a single brief, or iterate on any phase?"**

### Final Compilation

If the user requests a compiled brief:
1. Read `templates/gstic-brief.md`
2. Assemble all five phase deliverables into a single document
3. Add an Executive Summary at the top (3-5 sentences)
4. Save as `output/[project-name]-gstic-brief.md`

---

## Quick-Access Commands

Users can say these at any time:

| Command | Action |
|---------|--------|
| "Run GSTIC for [project]" | Full five-phase run |
| "Run [phase] for [project]" | Single phase execution |
| "Revise [phase]" | Re-enter a completed phase |
| "Show status" | Display which phases are complete and current phase |
| "Compile brief" | Generate the full GSTIC document |
| "Skip to [phase]" | Jump ahead (with dependency warning) |
