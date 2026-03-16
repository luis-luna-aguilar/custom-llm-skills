# Presentation architecture and data storytelling: a complete reference for AI-assisted deck planning

**This reference document provides the complete knowledge base for an AI skill that acts as a co-thinker during the ghost deck and wireframing stage of presentation development.** It covers seven interconnected domains—from choosing the right chart type to structuring narrative arcs to critiquing slide plans—synthesized from the field's most authoritative frameworks, practitioners, and research. Every section is designed to be directly actionable as system instructions: each provides named frameworks with attribution, IF/THEN decision rules, and documented anti-patterns. The target output is always a strong presentation blueprint for executive audiences (boards, C-suite, steering committees) before any visual design work begins.

---

## 2.3 Data visualization selection science

This is the most critical capability for the co-thinker skill. Choosing the wrong chart type is the single most common failure in analytical presentations—it forces the audience to decode the visual rather than absorb the message.

### The major chart selection frameworks

Nine established, named frameworks exist for systematic chart selection. Each approaches the problem from a different angle, and the AI should draw on multiple frameworks simultaneously.

**Andrew Abela's Chart Chooser** (2006, Extreme Presentation) is the original single-page decision tree, inspired by Gene Zelazny's *Saying It With Charts*. It asks one question—"What would you like to show?"—then branches across four data relationships: Comparison, Composition, Distribution, and Relationship. Each branch forks on secondary questions (time variable present? how many periods? how many variables?) to arrive at ~15 chart types. Its strength is simplicity and speed. Its limitation is coverage: it omits ranking, deviation, flow, geospatial, hierarchical, and network relationships entirely.

**The Financial Times Visual Vocabulary** (~2016–2018, FT Visual Journalism Team: Alan Smith, Chris Campbell, Ian Bott, and others) organizes **72 chart types into 9 categories**: Deviation, Correlation, Ranking, Distribution, Change over Time, Part-to-Whole, Magnitude, Spatial, and Flow. This is the most widely adopted professional standard as of 2025. Available as a poster (English, Japanese, Chinese), an interactive web tool, and a Tableau edition by Andy Kriebel. The 9-category system addresses most of Abela's gaps and is the recommended primary reference for the AI skill.

**Stephanie Evergreen's Chart Choosers** (Quantitative v4.1, 2019; Qualitative 3.0, 2017, with Jennifer Lyons; Chart Chooser Cards, 51-card deck with fassforward) are unique in two ways. First, they use plain-language communication goals as entry points ("When a single number is important," "How 2+ numbers are alike or not," "Hey, things changed over time"). Second, the Qualitative Chart Chooser is the only framework addressing non-numeric data (timelines, concept maps, quote callouts, word clouds). Best for evaluation, social science, and non-technical users.

**The Graphic Continuum** (2014, Jon Schwabish and Severino Ribecca; Bronze at Kantar Information is Beautiful Awards) is a 24"×36" poster plotting **~90 chart types across 6 categories**: Distribution, Time, Comparing Categories, Geospatial, Part-to-Whole, and Relationships. Unlike decision trees, it shows connections between chart types across categories—a bar chart links to both "Comparing Categories" and "Distribution." Best for expanding beyond the familiar bar-line-pie defaults. Not a step-by-step guide but an inspiration and reference tool.

**The Data Visualisation Catalogue** (2012–2013, Severino Ribecca, datavizcatalogue.com) is an online library browsable by ~16 functional categories or alphabetically. Each entry includes description, anatomy, use cases, similar charts, and tools. The broadest functional categorization of any framework.

**From Data to Viz** (~2018, Yan Holtz and Conor Healy; won Information is Beautiful Award) is an interactive decision tree unique in starting from **input data format** rather than communication goal. Users identify data type (Numeric, Categoric, Maps, Network, Time Series), then branch by variable count and observation count. Covers ~50 chart types across ~20 dataset formats. Includes a Caveat Gallery of ~40 dataviz pitfalls and links to R/Python code.

**Scott Berinato's 2×2 Typology** (2016, *Good Charts*, Harvard Business Review Press) is a meta-framework asking two questions: "Is the information conceptual or data-driven?" and "Am I declaring something or exploring something?" This produces four quadrants: **Idea Illustration** (conceptual + declarative), **Idea Generation** (conceptual + exploratory), **Everyday Dataviz** (data-driven + declarative), and **Visual Discovery** (data-driven + exploratory). Best for strategic decisions about *whether and why* to visualize, not *which chart type*.

**Juice Analytics Chart Chooser** (2007, Zach Gemignani with Andrew Abela) converted Abela's tree into a filterable web application with downloadable Excel/PowerPoint templates in Tufte-compliant styling. Adds "Trend" and "Table" to Abela's original 4 categories.

Additional frameworks include **Ferdio's Data Viz Project** (searchable by function, shape, and input data), **Chart.guide** (poster format), **Steve Franconeri's "Which Visualization?"** (Northwestern, perception-science-based), and the **Venngage ICCOR Method** (Inform, Compare, Change, Organize, Relationship).

**Decision rule for the AI**: Use the FT Visual Vocabulary's 9-category system as the primary framework. Cross-reference with Abela for quick checks and Evergreen for plain-language communication goals. Use Berinato's 2×2 to determine whether a visualization is even needed versus a conceptual diagram or exploratory analysis.

### Visualization recommendations by data relationship type

For each of the 15 data relationship types below, the primary recommendation appears first, followed by alternatives and decision rules.

**1. Comparison across categories** (e.g., sales by region). Primary: **horizontal bar chart** (best default—handles many categories, long labels, and natural ranking). Alternative: column chart (vertical bar) for ≤7 categories with short labels; grouped/clustered bar for sub-categories across groups; dot plot when zero baseline is irrelevant; lollipop chart for >15 categories to reduce clutter. IF >3 sub-groups → use small multiples instead of clustered bar. IF exact values needed → consider a table. What NOT to use: pie charts (poor at comparing non-adjacent slices), 3D bars, area charts without time axis.

**2. Comparison across time** (e.g., revenue by quarter). Primary: **line chart** (best for continuous trends, acceleration, deceleration). Alternative: column chart for discrete time periods emphasizing individual values; slope chart for exactly 2 time points; area chart for emphasizing magnitude. IF few periods (<5) → column may outperform line. IF >5 lines → use small multiples or highlight one line while graying others. IF showing change in rank → bump chart. What NOT to use: pie charts, scatter plots without time connection.

**3. Composition—static** (parts of whole at one point). Primary: **100% stacked bar** (best for comparing composition across categories). Alternative: pie chart for ≤5 slices with one dominant slice to highlight; donut chart (same as pie but allows center annotation); treemap for hierarchical/many categories; waffle chart for percentages (more accurate than pie); Marimekko chart when category size also varies. IF >5 parts → avoid pie, use treemap or stacked bar. IF parts are nearly equal → avoid pie (hard to distinguish), use bar. IF hierarchical → treemap or sunburst.

**4. Composition over time** (how parts change). Primary: **stacked area chart** (shows cumulative total and individual contributions). Alternative: 100% stacked area when relative proportions matter more than absolutes; stacked bar for discrete periods; streamgraph for many categories in editorial contexts. IF need to compare individual series accurately → small multiples (stacked obscures middle layers). IF absolute totals matter → regular stacked. What NOT to use: multiple pie charts over time, unstacked overlapping areas.

**5. Distribution—single variable**. Primary: **histogram** (best default for continuous data). Alternative: density plot for smoother view; box plot for summarizing with quartiles/outliers; strip/jitter plot for <30 data points. IF comparing groups → box plot or violin. IF showing shape → density or histogram. IF many outliers → box plot reveals them clearly. What NOT to use: bar charts showing means only (hides distribution shape).

**6. Distribution—two variables**. Primary: **scatter plot** (best for bivariate distribution, clusters, outliers). Alternative: 2D density/contour plot for >5,000 points; hexbin for large datasets; heatmap for co-occurrence frequency. IF <500 points → standard scatter. IF >5,000 → hexbin or 2D density. What NOT to use: dual-axis line charts to imply correlation.

**7. Distribution—multiple variables**. Primary: **ridgeline plot** (best for comparing distributions across many groups). Alternative: violin plot for distribution shapes across groups; multiple box plots for quick summary statistics; small multiples of histograms; parallel coordinates for many continuous variables. IF >10 groups → ridgeline. IF need statistical summary → multiple box plots. What NOT to use: overlapping histograms beyond 2–3 groups.

**8. Relationship/Correlation**. Primary: **scatter plot** with trend line (best default). Alternative: bubble chart (adds third variable via size); connected scatter (two variables over time); heatmap/correlogram (pairwise correlations among many variables). IF 2 variables → scatter. IF 3 variables → bubble. IF many variables → correlogram. **Always annotate**: correlation ≠ causation. What NOT to use: dual-axis charts without justification, bar charts for correlation.

**9. Flow/Process/Sequence**. Primary: **Sankey diagram** (best for flow quantities between stages with volume proportionality). Alternative: funnel chart for linear conversion/attrition; waterfall for sequential additive/subtractive changes; alluvial diagram for categorical membership changes across stages; chord diagram for bidirectional flows. IF linear pipeline → funnel. IF financial bridge → waterfall. IF complex branching → Sankey. IF bidirectional → chord. What NOT to use: standard bar/line charts; Sankey with >15 nodes (becomes unreadable).

**10. Geospatial/Location-based**. Primary: **choropleth map** (best for values by region, showing rates/ratios). Alternative: proportional symbol map for absolute magnitudes at locations; dot density for distribution/concentration; cartogram when large-area bias is problematic; flow map for movement between locations. IF showing rates → choropleth (normalize data!). IF showing counts → proportional symbol. IF large-area bias → cartogram or hexbin. What NOT to use: choropleth for absolute counts (large areas dominate misleadingly), 3D maps.

**11. Ranking/Ordering**. Primary: **sorted horizontal bar chart** (best default—sort largest to smallest). Alternative: lollipop for many items; bump chart for rank changes over time; slope chart for comparing 2 time points. IF static ranking → sorted bar. IF rank change over time → bump chart. What NOT to use: pie charts, unsorted bar charts (defeats ranking purpose).

**12. Deviation from baseline/target**. Primary: **diverging bar chart** (best for positive/negative from a reference). Alternative: diverging stacked bar for Likert scale data; surplus/deficit filled line for time-series deviation; bullet chart for single metric vs. target. IF survey data → diverging stacked bar. IF time-series deviation → surplus/deficit line. IF single KPI vs. target → bullet chart. What NOT to use: standard bar charts that cannot show negative direction.

**13. Change over time** (trends, cycles, volatility). Primary: **line chart** (best for continuous trends). Alternative: area chart for magnitude emphasis; column for discrete intervals; fan chart for uncertainty/forecasts; sparklines for inline trend context; calendar heatmap for day/week patterns; candlestick for financial OHLC. IF continuous → line. IF uncertainty → fan chart or confidence bands. IF seasonal pattern → calendar heatmap. What NOT to use: pie charts, scatter without time connection.

**14. Hierarchical/Nested data**. Primary: **treemap** (best for hierarchical proportions). Alternative: sunburst for multi-level drill-down; dendrogram for tree structure and clustering; circular packing as aesthetic alternative; nested bar for familiar chart type. IF showing proportions → treemap. IF showing structure → dendrogram. IF multiple levels → sunburst. IF audience unfamiliar with treemaps → nested bars. What NOT to use: flat bar charts (lose hierarchy), pie charts (cannot show nesting).

**15. Network/Connections**. Primary: **node-link diagram** (best default for showing connections). Alternative: chord diagram for mutual relationships in circular layout; adjacency matrix for dense networks; Sankey for directed flow with volume; hierarchical edge bundling for hierarchical + connection data. IF <50 nodes → force-directed network graph. IF >100 nodes → adjacency matrix or edge bundling. What NOT to use: any non-relational chart type; force-directed layouts for very dense networks (becomes a "hairball").

### When NOT to use a chart

The decision to *not* visualize is as important as choosing the right chart. Four alternatives exist, each with clear selection criteria.

**Use a "big number" display when** you have a single KPI that must communicate status at a glance. Pair big numbers with three elements: a comparison (vs. plan, vs. prior period), a directional indicator (↑/↓ arrow), and conditional color (green/red for above/below target). Round aggressively—"$518M" beats "$517,893,412" because precision adds no value at the KPI level. A KPI card earns its place when it answers "Is this good or bad, and is it getting better or worse?" without the reader having to think.

**Use a table when** the audience needs exact values for lookup or verification (financial reports where each decimal matters), when data contains multiple dimensions or mixed types (numerical + text + categorical), when the audience is analytical and wants to cross-reference, or when you have <20 data points where a chart adds no interpretive value. Per Stephen Few: "Tables interact primarily with our verbal system. We read tables."

**Use a chart when** the message lives in the shape of the values—trends, patterns, distributions, outliers—or when the audience needs to compare relative magnitudes quickly. Per Few: "Graphs interact with our visual system. It's a high-bandwidth information flow."

**Use a text callout when** the "data" is 1–2 numbers statable in a sentence ("Revenue grew 23% YoY"), a recommendation is the primary message, or narrative context matters more than pattern recognition.

**Master decision rule** (Knaflic): "When debating table vs. graph, ask how the data will be used and consider your audience. For busy executives, a simple chart is best. For analytical audiences who verify conclusions, include tables of raw data."

### Evidence-based chart design principles for executives

**Tufte's data-ink ratio** (Edward Tufte, *The Visual Display of Quantitative Information*, 1983/2001): Data-ink ratio = data-ink ÷ total ink. Goal: maximize toward 1.0. Apply the **erasure test**: "Would the data suffer any loss if this element were eliminated? If no, remove it." Eliminate decorations, unnecessary gridlines, ornamental shading, heavy borders, and 3D effects. The **Lie Factor** (size of effect in graphic ÷ size of effect in data) should equal ~1.0. Caveat: some research (Inbar et al., 2007; Bateman et al., 2010) found that moderate decoration increases memorability—so remove obvious clutter but don't strip charts to bare bones when engagement matters.

**Cognitive load** (Stephen Few, *Show Me the Numbers*): Working memory holds ~3–4 items simultaneously. A chart with 5 color-coded series and a separate legend forces the viewer to remember what each color means while interpreting data—cognitive overload. **Reduce load by**: using direct labels instead of legends, limiting distinct visual encodings to ≤5, using consistent formatting across charts, removing gridlines/borders/backgrounds that don't serve data, and using strategic color (gray + one highlight).

**Pre-attentive attributes** (Healey & Enns, 2012; Knaflic, 2015; Few, 2012) are visual properties processed in <250 milliseconds without conscious attention. Four groups: **Form** (orientation, length, width, size, shape, enclosure), **Color** (hue, intensity/saturation), **Position** (x,y coordinates), and **Motion** (flicker, movement). Rules: use one pre-attentive attribute strategically to draw attention; overuse creates clutter. Hue is excellent for categories but poor for quantitative values. **Position and length are the most accurate encoding channels** for quantitative comparison (Cleveland & McGill, 1984).

**Gestalt principles** applied to charts: **Proximity** (close objects perceived as belonging together—group related charts, place titles near their charts), **Similarity** (consistent color for same data series across charts), **Enclosure** (subtle background shading to group related KPIs), **Connection** (lines in line charts), **Continuity** (sort bars largest→smallest; time charts past→future), **Closure** (removing unnecessary axis lines—charts remain recognizable). Hierarchy of strength: Connection > Enclosure > Proximity > Similarity.

**Executive audiences differ fundamentally from analyst audiences.** Executives spend **3–15 seconds per visual**, seek "Are we on track? What needs attention?", prefer simple charts (bar, line, big number), and want **5–7 hero metrics**. Analysts spend minutes to hours, seek root causes, tolerate complex visualizations, and want dozens of metrics with drill-down. Design every executive chart for the 3-second glance test.

### Labeling, annotation, and embedding the "so what"

**Direct labeling over legends—always.** Legends force back-and-forth eye movement between legend and data, increasing cognitive load. Place data series labels directly next to or on the lines/bars they describe. Legends are acceptable only when direct labeling would create clutter (>5 overlapping series).

**Action titles, not descriptive titles.** "Revenue Overview" fails. **"West Region sales grew 2.5x, driving 60% of Q3 growth"** succeeds. The title states the insight so the viewer knows exactly why the chart matters. Knaflic: "Never assume it's apparent what's being shown."

**Annotations are the most underused tool in data storytelling.** Annotate: sudden spikes or dips (explain the cause), threshold crossings, anomalies needing context, and any chart where the "so what" isn't self-evident. Techniques include reference lines (targets, averages, benchmarks), shaded regions (specific time periods), callout boxes with arrows to data points, and selective data labels (not all points—that creates clutter).

**The power pairing is Color + Words** (Knaflic). If time-constrained, these two give the greatest impact. Ann K. Emery's four storytelling signals: descriptive title, descriptive subtitle, annotations, and dark/light contrast (gray out non-essential data, highlight the key story).

**Structure for executive slides**: Headline = the "so what" insight. Chart = the visual evidence. Annotation = context for key data points. Footer = methodology, assumptions, data source.

### Chart crimes and misleading patterns

Alberto Cairo (*How Charts Lie*, 2019) identifies five ways charts lie: poorly designed, displaying dubious data, displaying insufficient data, concealing/confusing uncertainty, and suggesting misleading patterns.

**Truncated/non-zero baseline**: Y-axis not starting at zero on bar charts makes small differences look dramatic. Studies show viewers overestimate differences even when warned. Fix: always start bar chart y-axes at zero. Line charts have more flexibility but annotate clearly if truncated.

**Dual-axis misuse**: Two independently manipulable y-axes can manufacture false correlations. Research (Isenberg et al., 2011): participants found dual-axis charts "very confusing" with poor accuracy. Fix: use small multiples, index both series to a common baseline, or use connected scatterplots.

**3D effects**: Perspective distortion makes bars/slices appear larger or smaller based on viewing angle. The added dimension conveys zero information. Fix: always use 2D.

**Pie chart overuse**: Poor at comparing angles; fail with >5 categories; 3D pies are worst. Fix: use bar charts for comparison; limit pies to 2–3 categories showing dominant proportion vs. whole.

**Cherry-picked time ranges**: Selecting start/end dates to support a narrative. Fix: show complete context or note the selection.

**Rainbow/spectral color scales**: Perceptually non-uniform—equal data differences appear as unequal color differences. Fix: use perceptually uniform scales (Viridis, Magma, Inferno).

**Spaghetti charts**: >5–7 overlapping lines are unreadable. Fix: use small multiples or highlight one series while graying others.

**Misleading area comparisons**: Bubbles scaled by diameter (area grows as the square). Fix: scale by area, not diameter.

**Inverted axes**: Y-axis reversed (zero at top) violates convention. Fix: always follow convention—zero at bottom.

**Cumulative graphs hiding decline**: Cumulative totals always increase even when period-over-period data declines. Fix: show both cumulative and per-period views.

### Color usage in data visualization

Three palette types serve different purposes. **Sequential palettes** (low→high, one direction: Blues, Viridis, Magma) are for data progressing from low to high. **Diverging palettes** (deviating from a center: Blue-Red, Purple-Green) are for data with a meaningful midpoint (profit/loss from zero, above/below average). **Categorical palettes** (distinct groups, no order: Okabe-Ito, Tableau 10) are for unordered categories.

Named accessible palettes: **Okabe-Ito** (8 colors, gold standard for colorblind safety, recommended by Nature journals), **Viridis family** (Viridis, Magma, Inferno, Plasma—perceptually uniform, colorblind-safe, grayscale-friendly), **ColorBrewer** (Cynthia Brewer—classic reference for all three types, with web tool at colorbrewer2.org), **Paul Tol's schemes** (comprehensive, scientist-designed).

**Critical rules**: Maximum **5–7 distinct colors** for categorical data—beyond 7, distinction degrades rapidly. **The gray + highlight technique** (Knaflic, Wilke) is the most powerful tool for executive presentations: gray out all non-essential data, use ONE bold accent color for the key story element. ~8% of men and ~0.5% of women have color vision deficiency (mostly red-green). **Never rely on color alone**—pair with shape, pattern, position, or labels. Avoid red-green pairs; use orange-blue as a culturally neutral alternative. WCAG minimum: 3:1 contrast ratio for large elements, 4.5:1 for smaller elements.

**Encoding channel hierarchy** (Cleveland & McGill, 1984): For quantitative data accuracy, from most to least accurate: Position on common scale → Length → Angle/Slope → Area → Color saturation → Color hue. Use position and length for the most important comparisons; reserve color for categories or emphasis.

### Visualization types for process analysis

| Visualization | Best for | IF/THEN rule |
|---|---|---|
| **Process map/Flowchart** | Sequential steps, decision logic | IF sequence/logic matters more than volume → process map |
| **Sankey diagram** | Flow quantities with branching, multi-path | IF complex branching with magnitude differences → Sankey |
| **Funnel chart** | Linear conversion/attrition | IF strictly sequential pipeline → funnel |
| **Waterfall chart** | Cumulative positive/negative contributions | IF financial bridge (revenue → costs → profit) → waterfall |
| **Control chart** | Process stability over time | IF monitoring for special-cause variation → control chart |
| **Pareto chart** | 80/20 analysis, top contributors | IF identifying the vital few causes → Pareto |
| **Swimlane diagram** | Cross-functional process, handoffs | IF 4–12 actors/departments involved → swimlane |
| **Value stream map** | End-to-end lean process with metrics | IF lean/Six Sigma with cycle time data → VSM |
| **Gantt chart** | Timeline/scheduling, task dependencies | IF project planning with parallel tasks → Gantt |

**Key comparisons**: Funnel = simple, linear, single-path conversion; Sankey = complex, multi-path, branching with proportional magnitude. If users can skip stages or follow multiple paths → Sankey. If strictly linear → funnel. Waterfall = cumulative sequential changes; Sankey = flow distribution across paths. For "How did we get from starting revenue to ending profit?" → waterfall. For "Where does our budget go?" → Sankey.

---

## 2.1 Narrative and storytelling frameworks for executive presentations

### The dominant frameworks

**The Pyramid Principle** (Barbara Minto, first published ~1987, developed at McKinsey in the 1970s) is the gold standard. Structure: the single key message/recommendation at the top, 2–4 supporting arguments at the second level, data and evidence at the third level. Start with the answer, then provide supporting evidence. Uses **vertical logic** (question-answer dialogue traveling down) and **horizontal logic** (inductive or deductive reasoning across same-level points). Incorporates **MECE** (Mutually Exclusive, Collectively Exhaustive). Rule: "You think from the bottom up, but you present from the top down."

**SCQA** (Situation-Complication-Question-Answer, also Minto) frames the introduction specifically. Situation = indisputable current state. Complication = what has changed that creates tension. Question = what the presentation answers. Answer = the recommendation (which becomes the pyramid's top). Best for opening slides and executive summaries.

**SCR** (Situation-Complication-Resolution, McKinsey) collapses the Question into the transition from Complication to Resolution. SCR frames the macro narrative; the Pyramid structures the arguments within the Resolution. The Resolution typically takes **60–70% of content**.

**And/But/Therefore** (Randy Olson, *Houston, We Have A Narrative*, 2015) is the simplest narrative template: "\_\_\_ AND \_\_\_ BUT \_\_\_ THEREFORE \_\_\_." Contrasted with AAA (And, And, And)—a non-narrative list of facts. Best for elevator pitches and quick framing.

**Nancy Duarte's Sparkline** (*Resonate*, 2010) alternates between "What Is" (current painful reality) and "What Could Be" (aspirational future), creating dramatic tension throughout. Ends on "The New Bliss"—a vivid transformed future. Includes S.T.A.R. moments (Something They'll Always Remember). Best for keynotes, vision presentations, and change management—less suitable for data-heavy analytical presentations.

**The Assertion-Evidence Model** (Michael Alley, Penn State) structures every slide as a one-sentence assertion headline supported by visual evidence—no bullet points. Research-validated for deeper audience comprehension. Best for technical and analytical slides.

### When to use which framework

| Goal | Primary framework | Secondary |
|---|---|---|
| Recommend action | Pyramid Principle + SCR | SCQA for intro |
| Get a decision | Pyramid (answer first) | SCR for framing |
| Present analysis findings | SCQA to frame the question | Pyramid for the answer |
| Inspire/motivate | Duarte Resonate | Hero's Journey |
| Quick verbal response | PREP | ABT |
| Elevator pitch | ABT | PREP |

**By audience**: IF C-suite/time-pressed → Pyramid (answer first). IF audience is skeptical or trust is low → build-up approach. IF audience needs inspiration → Resonate. IF mixed/large → SCQA or ABT for clarity.

**The MBB standard combines multiple frameworks**: SCR frames the overall arc, SCQA structures the executive summary, the Pyramid organizes supporting arguments, MECE ensures no gaps or overlaps, and action titles communicate the story at the slide level.

### Governing thought and headline-driven decks

The **governing thought** is the single most important idea—the primary message everything supports. Every presentation has exactly one. It sits at the pyramid's top and should be actionable and specific, not vague.

**Headline-driven (action title) decks** use complete sentence titles on every slide that communicate the key insight. Topic title (wrong): "Market Analysis." Action title (right): "Market is growing but fragmented and competitive." McKinsey calls these "leads" and trains: "A good lead will concisely capture the audience's attention, explain why the page is important, and show how it contributes to the storyline."

**The slide title storyboard technique**: Write the storyline in a document first (dot-dash format—dots are key statements that become slide titles, dashes are supporting data). Then reading ONLY the titles should tell the complete story. The **horizontal flow** is the story told by titles alone. The **vertical flow** is how each slide's body supports its title.

**The newspaper headline test**: Would this title work as a newspaper headline? Does it communicate a complete, self-contained insight? **Maximum 2 lines, ≤15 words.** Use active voice with action verbs. Avoid "and" (signals two ideas that should be two slides).

### Handling controversial recommendations

**Answer-first** (default for most executive presentations): State recommendation in the first 60 seconds, follow with 2–3 key reasons, provide data backup. Use when trust is high and content is non-controversial.

**Build-up** (for sensitive content): Lead with context and evidence, walk through analytical logic, arrive at conclusion with audience having followed the reasoning. Use when trust is low, recommendation is counterintuitive, or audience would reject the conclusion reflexively.

**Decision rule**: IF trust is high AND content is non-controversial → answer first. IF trust is low OR highly controversial → build-up. IF time is very limited → always answer first regardless.

**Techniques for pre-empting objections**: Include "Anticipated Questions" slide; acknowledge 2–3 risks explicitly alongside recommendations; quantify cost of inaction; present alternatives considered and rejected; prepare appendix slides for deep-dive questions ("I have a slide on that" builds enormous credibility); brief a friendly stakeholder beforehand for meeting support.

**Bad news structure** (modified SCR): Situation → Bad news (direct, don't bury it) → Impact (quantified) → Options (2–3 with pros/cons) → Recommendation → Next steps. **Never present bad news without a plan to address it.**

### Executive summary best practices

The executive summary is the one slide taking the most time—written LAST but appearing FIRST. Components follow SCR: Situation (10–15%, 1–2 sentences), Complication (15–20%), Resolution (60–70% including recommendation, key arguments, and quantified impact).

**BCG bold-bullet structure**: Bold sentences = key claims (skimmable as standalone story), bullet points below = supporting evidence. Reference body slide numbers for navigation.

**The 1-slide test**: If a board member reads ONLY the executive summary, they should understand the recommendation, quantified impact, key risks, and required decisions. If comprehension requires flipping to the appendix, the synthesis is incomplete.

Minto: "90% of all the thinking takes place in the introduction. If you have one hour and it takes 45 minutes for the introduction, that is about the right balance of time."

### Non-linear consumption and appendix strategy

Board members often read ahead, flip out of order, scan titles first, and skip to recommendations or appendix. **Design for random access**: each section self-contained with section dividers, navigation aids (slide numbers, progress bars), cross-references ("See Appendix Slide 45"), and consistent slide anatomy.

Nancy Duarte's **Slidedocs** concept addresses the tension between presentation and document. A Slidedoc is a visual document in presentation software intended to be read, not projected—one key message per slide but ~100 words per slide. The **slideument** (trying to make one artifact serve both purposes) fails at both.

**Appendix strategy**: The appendix is NOT a slide graveyard—it contains strategically prepared answers to anticipated questions. Five types: methodology backup, deeper data cuts, scenario alternatives, historical context, and implementation detail. **Test**: if removing a slide from the main deck doesn't break the storyline, it belongs in the appendix. Organize by chapter matching main deck structure or by stakeholder (CFO data, COO operations detail). Quality over quantity: **5–10 well-prepared slides you know inside out beats 30 you cannot navigate.**

---

## 2.5 Simplification and translation techniques

### Simplifying complex data without losing accuracy

**Aggregation strategy**: IF audience is C-suite → roll up to KPIs tied to strategic goals; keep granular detail in appendix. IF audience needs operational action → keep detail at the decision-making level. IF >5 categories → aggregate smaller categories into "Other" and footnote.

**The iceberg approach**: Only 10–20% of information should be visible on the slide; 80–90% is available as backup. Show the summary, have detail available. McKinsey standard: Title → Executive Summary → Body Slides → Appendix.

**Precision rules**: Round to meaningful precision—$21M not $21,000,000. Skip unnecessary decimals. Use them only when numbers are within a few percent of each other. IF the difference matters for the decision → keep precision. IF not → round aggressively.

### Overcoming the curse of knowledge

The curse of knowledge (Chip and Dan Heath, *Made to Stick*; Steven Pinker) is a cognitive bias where experts assume similar understanding in their audience. Miro Kazakoff (MIT Sloan): "We struggle to remember what it was like before we knew what we know now."

It manifests as: jargon blindness, assuming context is obvious, pattern projection (believing others see the same patterns in data—confirmed experimentally by Xiong, van Weelden & Franconeri at Northwestern), skipping the "why it matters," and encoding information at too high a level.

**Practical checklist**: Can someone outside your team understand this in 60 seconds? Have you replaced all jargon/acronyms? Does the slide require verbal explanation? Have you stated WHY this matters? Has a non-expert reviewed this? Are you assuming the audience sees the same pattern you see?

### Analogies, metaphors, and reference points

Numbers in isolation lack meaning. Heath brothers (*Made to Stick*): "Statistics should almost always illustrate a relationship. It's more important for people to remember the relationship than the number." The Beyond War movement dropped a single BB into a metal bucket (Hiroshima) then poured 5,000 BBs (world's nuclear arsenal)—making an abstract concept viscerally tangible.

**Techniques**: Associate data with familiar objects; use concrete physical representations ("enough to fill X football stadiums"); select culturally relevant scales; ensure the analogy covers >50% of the concept before transitioning back. **SUCCESs principles** applied to data: Simple, Unexpected, Concrete, Credible, Emotional, Stories.

### Presenting uncertainty without undermining the message

**Translation rules**: "Confidence interval" → "range of possible values." "95% confidence level" → "very likely" or "high confidence." Lead with the best estimate, then acknowledge the range: "We expect revenue of $50M, with a likely range of $45M–$55M." Limit caveats to 2–3 upfront. Present both risks and opportunities. Don't use 95% confidence intervals by default—think about what the decision-maker needs.

**Visual techniques**: Shaded bands on graphs, error bars on charts, fan charts for forecasts, scenario comparison tables (base/bull/bear) side-by-side. **Warning**: uncertainty often gets lost when communicated upward—"only central numbers persist." Ensure key uncertainty messages survive the drafting process.

### Sensitivity analysis and scenario presentation

**Tornado diagrams** rank variables by impact: widest bars at top (most sensitive), narrowing downward. Best for identifying which 2–3 assumptions drive the most value swing. Limitation: assumes one variable changes at a time.

**Scenario comparison**: Three standard scenarios (base, bull, bear) presented side-by-side. Scenarios must be internally consistent—never mix optimistic and pessimistic assumptions within one case. For boards: side-by-side comparison tables, not 50-cell sensitivity grids.

**Decision rule**: IF board/investment committee → tornado chart (which assumptions matter most) + scenario comparison table. IF operational teams → detailed sensitivity grids with conditional formatting.

### "So what" escalation: data to action

The fundamental chain: **Data** ("What happened?") → **Insight** ("Why did it happen?") → **Implication** ("Why should we care?") → **Recommendation** ("What should we do?"). Brent Dykes (*Effective Data Storytelling*, 2020) identifies three pillars: Data + Narrative + Visuals. His narrative arc: Setting → Hook (inciting incident) → Rising Insights → Climax (Aha Moment) → Action/Recommendation.

**Decision rule**: IF you can't articulate the "so what" → you're not done with analysis. IF the data doesn't lead to a clear action → consider whether a presentation is the right vehicle.

**Anti-pattern**: Presenting observation ("sales peak on Fridays") without insight ("because of weekly promotions") or action ("replicate on Tuesdays"). Never leave the audience to draw their own conclusions.

---

## 2.2 Ghost deck and wireframing methodology

### Process and stages

A **ghost deck** (also skeleton deck, shell deck, straw-man deck) is an early-draft presentation approximately **20% complete**. The standard MBB consulting process:

1. **Brief/Objective Setting**: Define the one-sentence purpose—what do you want the audience to learn, decide, or do?
2. **Dot-Dash Storyline**: Write the storyline in a text document. Main ideas = dots (become slide titles), supporting ideas = dashes. Test logic before opening PowerPoint.
3. **Ghost Deck/Skeleton**: Transfer into PowerPoint with action titles and headlines only. Add rough sketches of exhibits.
4. **Review with Leadership**: Is the storyline right? What content is needed? What exists? What's missing?
5. **Production/Build-out**: Fill in data, create charts, apply formatting.
6. **Polish and Final Review**: Executive summary (written last), formatting, source citations.

**Stage gates**: (1) Storyline approval (dot-dash review), (2) Ghost deck structure approval, (3) Content completeness review, (4) Final polish.

**Cardinal rule**: "You don't open PowerPoint until you're completely satisfied with your storyline" (Slide Science). The dot-dash approach lets you lay out the entire storyline without investing time creating slides. If changes are needed, you find out before wasting effort.

### Fidelity levels

**Level 1—Text-only outline** (dot-dash): Just slide titles and key points in a Word document. Use when storyline is uncertain. Fastest to iterate.

**Level 2—Ghost deck** (skeleton with action titles): Titles + headlines in PowerPoint, mostly blank slides, rough box sketches. ~20% of final effort. Use when storyline is agreed but data collection is ongoing.

**Level 3—Annotated wireframe**: Titles + headlines + placeholder charts with labels ("[Bar chart: Revenue by segment, FY23–FY25]"), sticker notes on data needs. Use when initial data is available.

**Level 4—Near-final draft**: All data populated, charts created, formatting applied. Missing only polish, executive summary, and citations.

**Decision rule**: IF direction uncertain → Level 1. IF storyline agreed but data in progress → Level 2. IF team needs to assign data tasks → Level 3. IF content complete → Level 4.

### Templates and techniques

**Sticky note storyboarding** (Cole Nussbaumer Knaflic): One idea per sticky note → arrange randomly → sequence into Opening → Key Points → Close. Color-code by priority (yellow = essential, pink = nice-to-have). Physical, tactile, prevents premature commitment to slide design.

**Slide sorter view**: Print 9 slides per page ("3×3 grid") to see overall structure at a glance. Quickly identifies gaps, redundancies, and flow problems.

**Capturing visualization decisions**: On ghost slides, annotate intended charts with bracketed descriptions: "[Bar chart: Revenue by segment, FY23–FY25]." For each exhibit, document: what metric is needed, data source, status (available/in progress/not started), owner, and deadline.

### Common failure modes

**Skipping the ghost deck entirely**: Team jumps from analysis to finished slides → massive rework when stakeholders disagree. **Over-investing in design before structure is set**: Beautiful charts on slides with wrong storyline → sunk cost bias prevents restructuring. **Failure to align on narrative**: Different team members build conflicting slides → Frankenstein deck. **Scope creep**: 80-slide deck for a 1-hour meeting. **Not testing early**: First stakeholder review with near-final deck → fundamental direction changes after major investment. McKinsey: consultants who show up after a long period with their "final" version absent any input are never impressive.

---

## 2.4 Slide-level design principles for analytical presentations

### Slide layout archetypes

**Assertion-Evidence** (Michael Alley, Penn State): Full-sentence assertion headline + visual evidence in body. No bullet points. Research-validated for deeper comprehension. Best for analytical and technical slides.

**Billboard**: One big idea—single statistic, quote, or phrase with large visual. Passes the 3-second test instantly. Best for keynote emphasis and "punctuation" slides between analytical sections.

**Build slide** (Progressive disclosure): Single visual revealed in stages. Each click adds one element. IF content has >3 interrelated components → use build. Controls attention, reduces overload.

**Comparison slide**: Side-by-side columns comparing options, scenarios, or time periods. Forces MECE thinking, makes trade-offs explicit.

**Dashboard slide**: Multi-panel layout with several small charts and KPIs. Best for status updates and operational monitoring. **Never use to make an argument**—it shows status, not conclusions.

**Consulting exhibit** (McKinsey/BCG): Action title (insight), subtitle (data source), body (chart/table proving the title), source citation in footer. One message per slide. Functions as standalone document.

**Framework/Matrix**: 2×2 matrix or strategic framework. Best for strategic positioning and prioritization. Don't force data into a 2×2 if dimensions aren't genuinely meaningful.

### Information density per slide

**The core rule**: Each slide communicates exactly ONE assertion. The **"And" test**: does your headline contain "and" connecting two claims? If yes → split. The **glance test** (Duarte, HBR 2012): audience should comprehend the main point in ≤3 seconds. Show to a colleague for 3 seconds—if they can't state the point, simplify.

| Deck type | Words/slide | Font minimum |
|---|---|---|
| Live presentation | 14–50 | 24pt body |
| Presented + leave-behind | ~86 | 18pt body |
| Pre-read / leave-behind | ~170 | 14pt body |
| TED-style keynote | <15 | 40pt body |

**"Slides are cheap" rule**: There is no value in minimizing slide count by packing slides full. An extra slide costs nothing; cognitive overload costs everything.

### Action titles: comprehensive rules

Action titles must be complete sentences with active verbs, ≤15 words, never exceeding 2 lines. They must pass both the "So What?" test (states an insight, not a description) and the "newspaper headline test" (specific and factual). Communicate outcomes, not processes: "Analyzing competitor pricing" → "Competitors undercut us by 15% in three key segments." Avoid "and" in titles. No jargon. The **horizontal flow test**: reading only titles in sequence should produce a coherent story. This is how MBB partners review decks.

### Tables in presentations

Use a table when: audience needs exact values, data has mixed types, precision matters more than pattern recognition, or comparing many specific attributes. **Design rules**: Never use PowerPoint default formatting. Remove heavy gridlines—use alternating row shading or subtle horizontal lines. Highlight important rows/cells with color or bold. Keep tables concise—include only data supporting the action title. Stephen Few: "IF data requires sequential reading of exact values → table. IF data requires pattern recognition → chart."

### Progressive disclosure

Start with the simplest view, add one element per click, maintain spatial consistency (elements appear in final position), use color/opacity to control focus (dim previous elements to 30–50% opacity), and end with a coherent complete picture. IF the deck is a leave-behind → do NOT use animation builds (they become dead slides in PDF). More than 5–6 build steps per slide is excessive—split into multiple slides instead.

---

## 2.6 Critique and quality assurance frameworks

### The consulting QA checklist

**Content quality checks**:

- **Action titles**: Every slide has a sentence title stating the insight (red flag: topic-only titles)
- **Horizontal flow**: Reading only titles tells a coherent story (red flag: story breaks at vague titles)
- **"So What?" test**: Every slide has a clear takeaway (red flag: data displayed without interpretation)
- **Body-title alignment**: Nothing in title not in body; nothing in body irrelevant to title (red flag: orphan data or unsupported claims)
- **Source citations**: Every data point sourced in footer (red flag: unsourced numbers)
- **MECE structure**: Sections don't overlap, nothing missing
- **One message per slide**: No "and" titles

**Formatting quality checks**: Consistent fonts/colors/alignment across all slides, spell-check + manual proofread, hidden metadata cleared (old client names, internal comments), consistent number formatting.

### The elevator test and compression frameworks

**Elevator test**: Can someone flip through the deck in 2–3 minutes, reading only titles, and understand the complete argument? Print/display only action titles in sequence, read aloud as a paragraph. Pass: narrative is coherent, persuasive, and complete. Fail: titles are topics, logical gaps exist, story doesn't build to recommendation.

**3-second glance test** (slide-level, Duarte): Show each slide to a colleague for exactly 3 seconds. Can they state the main point? IF no → simplify.

### Audience alignment testing

Before building: create an audience persona—who are they, what do they care about, what will they resist? Per slide: does this address the audience's needs, or just what the presenter wants to say? The **"So what to THEM?" test**: not just "so what?" but "so what to THIS audience specifically?" Language test: are there acronyms the audience won't understand?

### Red flags predicting presentation failure

| Anti-pattern | Description | Fix |
|---|---|---|
| **Data dump** | Slides crammed with every finding | Apply "so what?" filter |
| **Topic titles** | Descriptions instead of conclusions | Rewrite as insight-bearing sentences |
| **Bottom-up build** | Saving conclusion for the end | Invert: lead with recommendation (Pyramid) |
| **Frankendeck** | Cobbled from old decks, inconsistent | Enforce template, QA for consistency |
| **Orphan visuals** | Charts disconnected from title | Every visual must prove the headline |
| **Wall of text** | Full paragraphs on slides | Bold-bullet format, or split slides |
| **Appendix avoidance** | Supporting data cluttering main flow | Move non-essential detail to appendix |

### Pre-delivery final checklist

1. Horizontal flow test passed (titles alone tell the story)
2. Glance test passed (each slide comprehensible in 3 seconds)
3. Every slide answers "so what?"
4. One message per slide (no "and" titles)
5. All sources cited
6. Consistent formatting
7. No hidden metadata issues
8. Spell-check completed
9. Appendix contains all supporting detail
10. Executive summary works standalone
11. Builds/animations export gracefully to PDF

---

## 2.7 Key sources and authorities

### Essential books by function

**For executive presentation structure**: *The Pyramid Principle* by Barbara Minto (1987/2020)—the gold standard for answer-first, logically structured communication. Foundational to McKinsey, BCG, and all major consulting firms.

**For data storytelling process**: *Storytelling with Data* by Cole Nussbaumer Knaflic (2015)—codifies a 6-step process (understand context → choose visual → eliminate clutter → draw attention → think like designer → tell story). Used at 100+ universities. The most practical entry point for business professionals.

**For narrative design**: *Resonate* by Nancy Duarte (2010)—reverse-engineers great presentations using the Sparkline (alternating "what is" vs. "what could be"). Taught at Stanford GSB. *Slide:ology* (2008) by Duarte covers visual thinking for slides. *DataStory* (2019) bridges data visualization and narrative.

**For data storytelling theory**: *Effective Data Storytelling* by Brent Dykes (2020)—the most comprehensive treatment of Data + Narrative + Visuals as intersecting pillars. Strong on the psychology of why stories work.

**For visualization theory**: *The Visual Display of Quantitative Information* by Edward Tufte (1983/2001)—the foundational work. Data-ink ratio, chartjunk, Lie Factor, small multiples, sparklines. Amazon's top 100 non-fiction of the 20th century.

**For practical chart design**: *Show Me the Numbers* by Stephen Few (2012)—definitive practical guide for tables and graphs. *Good Charts* by Scott Berinato (2016, HBR Press)—the 2×2 typology and "talk, sketch, prototype" process. *Fundamentals of Data Visualization* by Claus Wilke (2019)—systematic reference, also free online.

**For critical visual literacy**: *How Charts Lie* by Alberto Cairo (2019)—five ways charts deceive. *The Truthful Art* (2016)—five qualities of great visualizations: truthful, functional, beautiful, insightful, enlightening.

**For memorable communication**: *Made to Stick* by Chip and Dan Heath (2007)—the SUCCESs framework (Simple, Unexpected, Concrete, Credible, Emotional, Stories). Essential complement to any data visualization book.

### Key frameworks

**FT Visual Vocabulary**: 72 chart types in 9 categories. The most widely adopted professional chart selection reference. Available at ft-interactive.github.io/visual-vocabulary/.

**The Graphic Continuum** (Schwabish & Ribecca): ~90 chart types across 6 categories showing cross-category connections. Best for expanding beyond defaults.

**Abela's Chart Chooser**: The original 4-category decision tree. Simple, fast, widely known.

**Evergreen's Chart Choosers**: Plain-language goal-based selection including the only qualitative data visualization framework.

**From Data to Viz**: Data-format-first interactive decision tree at data-to-viz.com with caveat gallery.

### Key online resources

**Storytelling with Data** (storytellingwithdata.com)—blog, monthly challenges, podcast, community. **PolicyViz** (policyviz.com, Jon Schwabish)—blog, podcast, tools lists, strong on policy/social science. **Datawrapper Blog** (blog.datawrapper.de)—outstanding articles on chart design, color theory, weekly dispatches. **Depict Data Studio** (depictdatastudio.com, Ann K. Emery)—practical training for researchers and nonprofits. **Flowing Data** (flowingdata.com, Nathan Yau)—daily curation since 2007, R tutorials. **Nightingale** (nightingaledvs.com)—journal of the Data Visualization Society. **Visualising Data** (visualisingdata.com, Andy Kirk)—design commentary, podcast, comprehensive tool catalogue.

### Foundational academic research

**Cleveland & McGill (1984)**, "Graphical Perception," *Journal of the American Statistical Association*—the foundational paper ranking perceptual accuracy of visual encodings. Position > Length > Angle > Area > Color saturation > Hue. Underlies virtually all modern chart selection guidance.

**Heer & Bostock (2010)**, "Crowdsourcing Graphical Perception," *CHI*—replicated Cleveland & McGill via Mechanical Turk, validating the perceptual hierarchy and enabling large-scale visualization research. Bostock later created D3.js.

**Bertin (1967/1983)**, *Semiology of Graphics*—original systematic theory of visual variables (position, size, shape, value, color, orientation, texture).

**Mackinlay (1986)**, "Automating the Design of Graphical Presentations"—extended Cleveland & McGill into automated systems, influencing Tableau.

### Key practitioners

**Edward Tufte**: "Galileo of graphics." Yale professor emeritus. Coined data-ink ratio, chartjunk. Four foundational books. **Cole Nussbaumer Knaflic**: Former Google analytics. Five bestselling books. Made data visualization skills accessible at scale. **Nancy Duarte**: CEO of Silicon Valley's largest design firm. Created presentations for Apple and Al Gore. Six books. Cracked the code for story patterns in business. **Barbara Minto**: First female MBA hire at McKinsey. Invented the Pyramid Principle and MECE. Still the global standard. **Stephen Few**: Founder of Perceptual Edge. Six books on evidence-based, perception-grounded data presentation. **Alberto Cairo**: Knight Chair in Visual Journalism, University of Miami. Leading voice on visual literacy and ethics. **Scott Berinato**: HBR Senior Editor. Championed data visualization in business with the 2×2 typology. **Brent Dykes**: Leading authority on data storytelling as distinct from data visualization. DAA "Most Influential" 2016. **Jon Schwabish**: Urban Institute senior fellow. Created the Graphic Continuum and PolicyViz. **Andy Kirk**: UK-based independent expert. Visualisingdata.com since 2010. Clients include Google, CERN, McKinsey. Three editions of *Data Visualisation: A Handbook*.