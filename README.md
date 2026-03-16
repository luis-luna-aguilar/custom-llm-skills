# Custom LLM Skills

A collection of custom skills for Claude, ChatGPT and Copilot. These skills extend LLMs capabilities with specialized domain knowledge and structured workflows.

Licensed under MIT. See [LICENSE](LICENSE) for details.

## Installation: Claude

To use a skill, copy its folder into your Claude skills directory:

- **Cowork mode**: Place the skill folder in your `.skills/skills/` directory (typically `~/Documents/Claude/.skills/skills/`)
- **Claude Code**: Place the skill folder in your project's `.claude/skills/` directory, or in `~/.claude/skills/` for global access

Each skill is a self-contained folder with a `SKILL.md` file that Claude reads automatically when the skill is triggered. Some skills include reference files and supporting materials that Claude loads on demand.

## Available Skills

### [Presentation Architect](presentations-architect/)

A co-thinking partner for the **planning and wireframing stage** of executive presentations. It helps analysts and consultants structure board-level decks before any slides get built.

**What it does:**

- Recommends narrative frameworks (Pyramid Principle, SCR, SCQA, Duarte Resonate) based on your audience, goal, and content type
- Selects the right data visualization for your data and message, with decision logic grounded in named authorities (FT Visual Vocabulary, Abela, Schwabish, Knaflic)
- Produces slide-by-slide ghost deck plans with action titles, archetypes, and content specifications
- Renders inline SVG wireframes showing content zones and rough chart sketches
- Critiques existing slide plans against a structured rubric (action titles, horizontal flow, "so what" test, information density)
- Translates complex/technical analysis into executive-friendly content
- Compounds knowledge across sessions via a lessons-learned mechanism

**What it does NOT do:**

- Build .pptx files (pair it with the built-in `pptx` skill for that)
- Handle visual design, branding, or templates
- Coach on delivery or speaking

**Trigger phrases:** "help me plan a presentation," "what chart should I use," "ghost deck," "wireframe my slides," "deck structure," "storyline," "narrative arc," "review my slide plan"

**Included reference files:**

| File | Purpose |
|------|---------|
| `chart-selection.md` | Chart type decision engine with data-relationship-to-chart mapping |
| `narrative-frameworks.md` | Storytelling frameworks and when to use each |
| `slide-archetypes.md` | Slide layout patterns and information density guidelines |
| `simplification.md` | Techniques for translating complex data for executives |
| `critique-rubric.md` | Structured rubric for reviewing and improving slide plans |
| `sources.md` | Cited authorities and recommended reading |

**Example usage:**

> "I need to present our process mining findings to the board. We found 3 major bottlenecks and have recommendations for each [Provide content for the deck]. The board has 30 minutes and they need to approve budget for the fixes. Please help me go through this process using the presentation-architect skill."

The skill will recommend a narrative framework, plan the deck slide-by-slide with action titles, suggest visualizations for each finding, and render wireframes of the key slides.
