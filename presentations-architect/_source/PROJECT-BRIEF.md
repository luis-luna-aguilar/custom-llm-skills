# Presentation Architect Skill — Project Brief

## What we're building

A custom Claude Skill called **presentation-architect** that acts as a co-thinker during the ghost deck / wireframing stage of presentation development. It helps analysts and consultants plan, structure, and wireframe board-level presentations that communicate complex analytical findings and recommendations.

This skill operates at the **architecture layer** — before any slide design happens. It is not a slide builder. It is a thinking partner for the planning phase.

## Who this is for

- **Skill user:** An analyst or consultant building presentations for executive audiences
- **Presentation audience:** Board members, C-suite, senior leadership, steering committees
- **Presentation content:** Complex process analysis results and recommendations for action

## What the skill does

### Core capabilities

1. **Narrative structure brainstorming** — Help choose and apply storytelling frameworks (Pyramid Principle, SCR, SCQA, etc.) based on the content type, audience, and goal
2. **Data visualization selection** — Given a data type and a message, recommend the right chart/visual type with decision logic (IF parts-of-whole AND >5 categories → treemap, not pie chart)
3. **Ghost deck wireframing** — Produce slide-by-slide wireframe plans with annotated zones showing what goes where and why
4. **Visual wireframe rendering** — Render inline SVG wireframes of slide layouts showing content zones, rough chart sketches, and placement rationale (see "Visual tools" section below)
5. **Critique and review mode** — Review a user's existing slide plan and identify weaknesses, missing elements, narrative gaps, or poor visualization choices
6. **Simplification coaching** — Help translate complex/technical analytical outputs into clear content for non-technical executive audiences
7. **Lessons learned generation** — At the end of a session, automatically identify new patterns, techniques, or insights discovered during the work and present them as pre-drafted lesson cards for the user to approve

### What the skill does NOT do

- Produce production-ready slides or .pptx files (that's the pptx skill's job)
- Handle slide visual design (colors, fonts, branding, templates)
- Coach on presentation delivery (speaking, body language)
- Build live dashboards or BI tool configurations
- Create infographics or marketing visuals

## Visual tools available

The skill should leverage these rendering capabilities during brainstorming conversations:

### SVG wireframes (primary tool)
- Slide layout wireframes with dashed zones showing content placement
- Color-coded annotations explaining the rationale for each zone
- Rough chart shape sketches (bar outlines, line paths, flow arrows) to indicate visualization type without building the actual chart
- These are schematic, not pixel-perfect — they're planning artifacts

### Mermaid.js
- Process flows and decision trees
- Sequence diagrams
- Useful when the slide content itself is a process or flow diagram

### Chart.js
- Sample charts to demonstrate what a visualization type looks like with rough data
- Useful when comparing "should this be a waterfall or a stacked bar?" — render both and discuss

### HTML widgets
- Side-by-side layout comparisons
- Interactive elements when exploring options

### Key design principle for wireframes
Wireframes should look like wireframes — dashed borders, zone labels, annotation legends. They communicate structure and rationale, not aesthetics. Approximate aspect ratios are fine. The goal is to make the planning conversation tangible and visual.

## Lessons learned mechanism

### How it works
1. At the end of a presentation planning session, the skill automatically reviews what was discussed
2. It identifies any new patterns, novel visualization choices, narrative techniques, or critique insights that emerged — things that go beyond the skill's baseline knowledge
3. It drafts "lesson cards" in a structured format (see below) and presents them to the user
4. The user reviews, approves (or edits), and copies approved cards into the `lessons-learned.md` file in the skill folder
5. Next session, the skill reads `lessons-learned.md` and incorporates past discoveries into its recommendations

### Critical: the user does NOT describe the lessons
The skill does all the work of identifying and articulating what's new. The user only approves or rejects. Zero cognitive load on the user.

### Lesson card format
```markdown
## [Short descriptive title]
- **Date:** [session date]
- **Context:** [what kind of presentation/data/audience prompted this]
- **Discovery:** [what we learned or invented]
- **When to apply:** [conditions under which this lesson is relevant]
- **Example:** [brief concrete example if applicable]
```

## Skill folder structure

```
presentation-architect/
├── SKILL.md                        # Main skill instructions (<500 lines)
├── references/
│   ├── chart-selection.md          # Visualization decision framework
│   │                                 (data type → chart type mapping,
│   │                                  IF/THEN rules, anti-patterns)
│   ├── narrative-frameworks.md     # Storytelling structures
│   │                                 (Pyramid Principle, SCR, SCQA, etc.
│   │                                  when to use each, how to apply)
│   ├── slide-archetypes.md         # Slide layout patterns
│   │                                 (assertion-evidence, billboard,
│   │                                  comparison, dashboard, build slides)
│   ├── simplification.md           # Translation techniques
│   │                                 (complexity → clarity methods,
│   │                                  executive audience adaptation)
│   ├── critique-rubric.md          # QA checklists and red flags
│   │                                 (ghost deck review criteria,
│   │                                  common failure modes)
│   └── sources.md                  # Key authorities and references
│                                     (books, frameworks, named methods)
├── lessons-learned.md              # User-curated compounding knowledge
│                                     (starts empty, grows over time)
└── CHANGELOG.md                    # Version history
```

### File sizing guidance
- SKILL.md should be under 500 lines (Claude.ai limit) — it references the files in `references/` and tells Claude when to load each one
- Each reference file should be self-contained and focused
- The `chart-selection.md` file will be the largest and most detailed — this is the core decision engine
- `lessons-learned.md` starts as an empty template and grows through use

## Workflow the skill enables

A typical session looks like this:

1. **User provides context** — "I need to present the results of a process efficiency audit to the steering committee. We found 3 major bottlenecks, quantified the cost impact, and have 5 recommendations."
2. **Skill helps choose narrative structure** — Recommends a framework (e.g., SCR) and proposes a high-level flow (situation → key findings → impact → recommendations → next steps)
3. **Slide-by-slide planning** — For each slide, the skill recommends: what data goes here, what visualization type, what the action title should say, how to balance text and visuals
4. **Visual wireframing** — Renders inline SVG wireframes showing the proposed layout for key slides, with annotations
5. **Critique loop** — User pushes back, suggests changes, skill iterates. Or user presents their own plan and skill critiques it.
6. **Ghost deck output** — The final plan is a structured document or markdown describing each slide's purpose, content, visualization type, layout, and headline
7. **Lessons capture** — Skill identifies novel discoveries from the session and presents lesson cards for approval

## Research input

A comprehensive research request has been sent out covering seven areas:

1. **Narrative & storytelling frameworks** for executive presentations
2. **Ghost deck / wireframing methodology** — established processes and best practices
3. **Data visualization selection science** — chart chooser frameworks, decision logic, anti-patterns (HIGHEST PRIORITY — this is the core engine)
4. **Slide-level design principles** — layout archetypes, information density, headline best practices
5. **Simplification & translation techniques** — making complex data accessible to non-technical boards
6. **Critique & QA frameworks** — checklists, rubrics, red flags for presentation review
7. **Key sources & authorities** — books, frameworks, named methodologies with attribution

The research output document should be in this project folder when it arrives. It will be the primary input for populating the `references/` files.

## Distribution plan

- **GitHub repository** — version controlled, public or private as preferred
- **Installation:** Users download/clone the repo, zip the `presentation-architect/` folder, upload via Claude Settings > Customize > Skills
- **Updates:** Push to GitHub, users re-download and re-upload the zip
- **Team/Enterprise:** Admins can provision organization-wide through org settings
- **The skill follows the Agent Skills open standard** — portable across Claude surfaces (claude.ai, Claude Code, API)

## Key design decisions already made

| Decision | Rationale |
|----------|-----------|
| Architecture layer only, no slide production | Keeps the skill focused; pptx skill handles production |
| Inline SVG wireframes as primary visual tool | Available in the Visualizer, renders in conversation, schematic fidelity is appropriate for planning |
| Lessons learned are auto-generated, user only approves | Zero cognitive load — the skill does the thinking, user does the curation |
| Chart selection is the deepest reference file | This is where most presentation decisions are won or lost |
| IF/THEN decision logic over abstract theory | The skill needs to be prescriptive, not philosophical |
| Named sources and attribution throughout | Credibility matters; "use a bar chart" is weak, "Abela's chart chooser recommends..." is strong |

## Next steps

1. **Research comes back** → Drop the research output document into this folder
2. **Populate reference files** → Extract and organize research into the six reference files
3. **Write SKILL.md** → The main instruction file that orchestrates everything
4. **Test with a real scenario** → Run a presentation planning session end-to-end
5. **Iterate** → Refine based on what works and what doesn't
6. **Package and distribute** → Zip, upload, share via GitHub
