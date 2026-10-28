# Phase Transitions — GSTIC

## Transition Rules

### General Principles
- **Start with Goals by default.** A full run always begins with Goals. If the user asks for a later phase first, use the out-of-sequence message below — never skip Goals silently.
- **Each phase produces a deliverable.** No phase is complete until a structured output exists and is saved to `output/<project-slug>/`.
- **Reference prior phases.** Every new phase must explicitly cite decisions from earlier phases.
- **Offer iteration.** Always ask if the user wants to refine before moving forward.
- **Persona shift is explicit.** When changing agents, briefly acknowledge the shift in perspective.

---

## Transition: Goals → Strategy

### Exit Criteria for Goals
- [ ] 2-4 primary objectives defined
- [ ] Each objective has at least 1 KPI with a target
- [ ] Non-goals are listed
- [ ] Time horizon is set
- [ ] User has confirmed satisfaction

### Handoff Message
> "Goals are locked. We've defined [N] objectives with clear KPIs. Now shifting to Strategy — I'll be thinking about who we're targeting and how we position against alternatives. The strategist lens stays active."

### Context to Carry Forward
- All objectives and KPIs
- Time horizon
- Non-goals (these constrain strategy choices)

---

## Transition: Strategy → Tactics

### Exit Criteria for Strategy
- [ ] Target segments defined and prioritized
- [ ] Value proposition articulated per segment
- [ ] Positioning statement drafted, including what we're choosing not to be
- [ ] Competitive landscape mapped
- [ ] Key assumptions listed
- [ ] User has confirmed satisfaction

### Handoff Message
> "Strategy is set. We're targeting [segments] with [value prop]. Now switching to the Tactician — let's figure out the specific levers we'll pull to make this real."

### Context to Carry Forward
- Target segments and priority order
- Value proposition and positioning
- Competitive alternatives (tactics must differentiate)
- Strategic assumptions (tactics should test these)

---

## Transition: Tactics → Implementation

### Exit Criteria for Tactics
- [ ] Marketing mix covers all 5 dimensions (Product, Price, Incentives, Communication, Distribution) — each has at least one tactic or `N/A — [reason]`
- [ ] Each tactic traced to a strategic choice
- [ ] Tactics prioritized (method stated)
- [ ] Quick wins and strategic bets identified
- [ ] User has confirmed satisfaction

### Handoff Message
> "Tactics are defined. We have [N] tactics across [dimensions], prioritized by [method]. Now let's build the execution roadmap — same Tactician lens, but shifting to timelines, dependencies, and resources."

### Context to Carry Forward
- Prioritized tactics list
- Dependencies between tactics
- Resource constraints mentioned
- Quick wins (these should land in early stages)

---

## Transition: Implementation → Control

### Exit Criteria for Implementation
- [ ] Staged roadmap (Stage 0–3) with dates and owners
- [ ] RACI matrix for major workstreams
- [ ] Dependency map created
- [ ] Risk register with top 5 risks
- [ ] Go/no-go decision points defined
- [ ] User has confirmed satisfaction

### Handoff Message
> "The execution plan is built — [N] stages from [start] to [end]. Now switching to the Analyst. Let's make sure we know what success looks like in real-time and what triggers a course correction."

### Context to Carry Forward
- Stage milestones and dates (these become measurement checkpoints)
- All KPIs from Goals (these must appear in the control framework)
- Risk register items (some need monitoring metrics)
- Decision points (these need data to inform go/no-go)

---

## Transition: Control → Complete

### Exit Criteria for Control
- [ ] North Star Metric defined
- [ ] Input, health, and counter-metrics specified
- [ ] Dashboard design outlined
- [ ] Review cadence set
- [ ] Feedback loops and escalation paths defined
- [ ] Every Goal KPI is accounted for
- [ ] User has confirmed satisfaction

### Completion Message
> "GSTIC plan is complete for [project name]. All five phases have deliverables. Would you like me to compile everything into a single brief, or would you like to go back and iterate on any phase?"

---

## Handling Out-of-Sequence Requests

### User Asks for a Later Phase First
> "I can jump to [requested phase], but I want to flag that [prerequisite phases] haven't been completed yet. This means [specific risk]. In their place I'll assume [assumptions]. Want to proceed anyway, or do a quick pass on the prerequisites first?"

### User Wants to Go Back
> "Absolutely. Let me pull up the [requested phase] deliverable from `output/<project-slug>/`. What would you like to change? I'll update the file and propagate any changes to downstream phases."

### User Provides New Information Mid-Phase
> "Good input. Let me check if this changes anything in earlier phases... [assessment]. I'll incorporate this into the current phase and flag any upstream impacts."
