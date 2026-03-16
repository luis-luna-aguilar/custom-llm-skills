# Chart Selection Decision Framework

This is the core decision engine for choosing visualizations. Use the FT Visual Vocabulary's 9-category system as the primary framework. Cross-reference with Abela for quick checks and Evergreen for plain-language communication goals. Use Berinato's 2×2 to determine whether a visualization is even needed versus a conceptual diagram or exploratory analysis.

## Table of contents

1. [Major chart selection frameworks](#major-chart-selection-frameworks)
2. [Recommendations by data relationship type](#recommendations-by-data-relationship-type)
3. [When NOT to use a chart](#when-not-to-use-a-chart)
4. [Evidence-based design principles](#evidence-based-design-principles)
5. [Labeling, annotation, and the "so what"](#labeling-annotation-and-the-so-what)
6. [Chart crimes and misleading patterns](#chart-crimes-and-misleading-patterns)
7. [Color usage](#color-usage)
8. [Visualization types for process analysis](#visualization-types-for-process-analysis)

---

## Major chart selection frameworks

Nine established frameworks exist. The AI should draw on multiple simultaneously.

**Andrew Abela's Chart Chooser** (2006, Extreme Presentation): The original single-page decision tree from Gene Zelazny's *Saying It With Charts*. Asks "What would you like to show?" then branches: Comparison, Composition, Distribution, Relationship. Simple and fast. Limitation: omits ranking, deviation, flow, geospatial, hierarchical, and network relationships.

**FT Visual Vocabulary** (~2016–2018, FT Visual Journalism Team: Alan Smith, Chris Campbell, Ian Bott): **72 chart types in 9 categories**: Deviation, Correlation, Ranking, Distribution, Change over Time, Part-to-Whole, Magnitude, Spatial, Flow. The most widely adopted professional standard. Available as poster, interactive tool, and Tableau edition. **This is the primary reference.**

**Stephanie Evergreen's Chart Choosers** (Quantitative v4.1, 2019; Qualitative 3.0, 2017 with Jennifer Lyons): Unique for plain-language entry points ("When a single number is important") and the only framework addressing non-numeric data (timelines, concept maps, quote callouts). Best for evaluation, social science, non-technical users.

**The Graphic Continuum** (2014, Jon Schwabish & Severino Ribecca): ~90 chart types across 6 categories showing cross-category connections. An inspiration tool, not a step-by-step guide.

**The Data Visualisation Catalogue** (2012–2013, Severino Ribecca, datavizcatalogue.com): Online library, ~16 functional categories. Broadest functional categorization.

**From Data to Viz** (~2018, Yan Holtz & Conor Healy): Starts from input data format rather than communication goal. ~50 chart types across ~20 dataset formats. Includes Caveat Gallery of ~40 pitfalls.

**Scott Berinato's 2×2 Typology** (2016, *Good Charts*, HBR Press): Meta-framework asking "conceptual or data-driven?" × "declaring or exploring?" → four quadrants: Idea Illustration, Idea Generation, Everyday Dataviz, Visual Discovery. Use to decide *whether and why* to visualize.

**Juice Analytics Chart Chooser** (2007, Zach Gemignani with Andrew Abela): Filterable web app with downloadable templates. Adds Trend and Table to Abela's 4 categories.

Additional: **Ferdio's Data Viz Project**, **Chart.guide**, **Steve Franconeri's "Which Visualization?"** (Northwestern, perception-science-based), **Venngage ICCOR Method**.

---

## Recommendations by data relationship type

For each of the 15 types below, the primary recommendation appears first, followed by alternatives and decision rules.

### 1. Comparison across categories
*e.g., sales by region*

- **Primary: Horizontal bar chart** — handles many categories, long labels, natural ranking
- Alternative: column chart (≤7 categories, short labels); grouped bar (sub-categories); dot plot (zero baseline irrelevant); lollipop (>15 categories)
- IF >3 sub-groups → small multiples instead of clustered bar
- IF exact values needed → table
- **NOT**: pie charts, 3D bars, area charts without time axis

### 2. Comparison across time
*e.g., revenue by quarter*

- **Primary: Line chart** — continuous trends, acceleration, deceleration
- Alternative: column (discrete periods, individual values); slope chart (exactly 2 time points); area chart (magnitude emphasis)
- IF few periods (<5) → column may outperform line
- IF >5 lines → small multiples or highlight + gray
- IF showing rank change → bump chart
- **NOT**: pie charts, scatter without time connection

### 3. Composition — static
*parts of whole at one point*

- **Primary: 100% stacked bar** — comparing composition across categories
- Alternative: pie (≤5 slices with one dominant); donut (center annotation); treemap (hierarchical/many); waffle (percentages); Marimekko (category size varies)
- IF >5 parts → avoid pie, use treemap or stacked bar
- IF parts nearly equal → avoid pie, use bar
- IF hierarchical → treemap or sunburst

### 4. Composition over time
*how parts change*

- **Primary: Stacked area chart** — cumulative total + individual contributions
- Alternative: 100% stacked area (relative proportions); stacked bar (discrete periods); streamgraph (many categories, editorial)
- IF need to compare individual series → small multiples
- IF absolute totals matter → regular stacked
- **NOT**: multiple pie charts over time, unstacked overlapping areas

### 5. Distribution — single variable

- **Primary: Histogram** — continuous data default
- Alternative: density plot (smoother); box plot (quartiles/outliers); strip/jitter (<30 points)
- IF comparing groups → box plot or violin
- IF showing shape → density or histogram
- **NOT**: bar charts showing means only (hides distribution)

### 6. Distribution — two variables

- **Primary: Scatter plot** — bivariate distribution, clusters, outliers
- Alternative: 2D density/contour (>5,000 points); hexbin (large datasets); heatmap (co-occurrence)
- IF <500 points → standard scatter
- IF >5,000 → hexbin or 2D density
- **NOT**: dual-axis line charts to imply correlation

### 7. Distribution — multiple variables

- **Primary: Ridgeline plot** — comparing distributions across many groups
- Alternative: violin (distribution shapes); multiple box plots (summary stats); small multiples of histograms; parallel coordinates (many continuous variables)
- IF >10 groups → ridgeline
- IF need statistical summary → multiple box plots
- **NOT**: overlapping histograms beyond 2–3 groups

### 8. Relationship / Correlation

- **Primary: Scatter plot with trend line**
- Alternative: bubble chart (+third variable via size); connected scatter (two variables over time); correlogram (pairwise among many)
- IF 2 variables → scatter
- IF 3 variables → bubble
- IF many variables → correlogram
- **Always annotate**: correlation ≠ causation
- **NOT**: dual-axis charts, bar charts for correlation

### 9. Flow / Process / Sequence

- **Primary: Sankey diagram** — flow quantities with volume proportionality
- Alternative: funnel (linear conversion); waterfall (sequential additive/subtractive); alluvial (categorical membership changes); chord (bidirectional)
- IF linear pipeline → funnel
- IF financial bridge → waterfall
- IF complex branching → Sankey
- IF bidirectional → chord
- **NOT**: standard bar/line; Sankey with >15 nodes

### 10. Geospatial / Location-based

- **Primary: Choropleth map** — values by region (rates/ratios)
- Alternative: proportional symbol (absolute magnitudes); dot density (distribution); cartogram (large-area bias); flow map (movement)
- IF showing rates → choropleth (normalize data!)
- IF showing counts → proportional symbol
- IF large-area bias → cartogram or hexbin
- **NOT**: choropleth for absolute counts, 3D maps

### 11. Ranking / Ordering

- **Primary: Sorted horizontal bar chart** — largest to smallest
- Alternative: lollipop (many items); bump chart (rank change over time); slope chart (2 time points)
- IF static ranking → sorted bar
- IF rank change over time → bump chart
- **NOT**: pie charts, unsorted bar charts

### 12. Deviation from baseline/target

- **Primary: Diverging bar chart** — positive/negative from reference
- Alternative: diverging stacked bar (Likert data); surplus/deficit filled line (time-series); bullet chart (single metric vs target)
- IF survey data → diverging stacked bar
- IF time-series deviation → surplus/deficit line
- IF single KPI vs target → bullet chart

### 13. Change over time (trends, cycles, volatility)

- **Primary: Line chart** — continuous trends
- Alternative: area (magnitude); column (discrete); fan chart (uncertainty/forecasts); sparklines (inline context); calendar heatmap (day/week patterns); candlestick (financial OHLC)
- IF continuous → line
- IF uncertainty → fan chart or confidence bands
- IF seasonal pattern → calendar heatmap

### 14. Hierarchical / Nested data

- **Primary: Treemap** — hierarchical proportions
- Alternative: sunburst (multi-level drill-down); dendrogram (tree structure); circular packing; nested bar
- IF showing proportions → treemap
- IF showing structure → dendrogram
- IF multiple levels → sunburst
- IF audience unfamiliar with treemaps → nested bars

### 15. Network / Connections

- **Primary: Node-link diagram**
- Alternative: chord (mutual relationships); adjacency matrix (dense networks); Sankey (directed flow with volume); hierarchical edge bundling
- IF <50 nodes → force-directed graph
- IF >100 nodes → adjacency matrix or edge bundling
- **NOT**: non-relational chart types; force-directed for very dense networks

---

## When NOT to use a chart

The decision not to visualize is as important as choosing the right chart.

**Big number display**: Single KPI, status at a glance. Pair with: comparison (vs plan/prior), directional indicator (↑/↓), conditional color (green/red). Round aggressively — "$518M" beats "$517,893,412." Answers: "Is this good or bad, and is it getting better or worse?"

**Table**: Audience needs exact values for lookup/verification; multiple dimensions or mixed types; analytical audience cross-referencing; <20 data points where a chart adds no value. Per Few: "Tables interact with our verbal system."

**Chart**: Message lives in the shape — trends, patterns, distributions, outliers; audience needs to compare relative magnitudes. Per Few: "Graphs interact with our visual system."

**Text callout**: 1–2 numbers statable in a sentence; recommendation is the primary message; narrative context matters more than pattern recognition.

**Master rule** (Knaflic): "When debating table vs. graph, ask how the data will be used and consider your audience. For busy executives, a simple chart is best. For analytical audiences who verify conclusions, include tables of raw data."

---

## Evidence-based design principles

**Tufte's data-ink ratio** (1983/2001): Data-ink ÷ total ink → maximize toward 1.0. Apply the erasure test: if removing an element doesn't hurt the data, remove it. The Lie Factor (size of effect in graphic ÷ size of effect in data) should equal ~1.0. Caveat: moderate decoration can increase memorability (Inbar et al., 2007; Bateman et al., 2010).

**Cognitive load** (Stephen Few, *Show Me the Numbers*): Working memory holds ~3–4 items. Reduce load by: direct labels instead of legends, ≤5 distinct visual encodings, consistent formatting, removing non-data elements, strategic color (gray + one highlight).

**Pre-attentive attributes** (Healey & Enns, 2012; Knaflic; Few): Processed in <250ms. Form (orientation, length, width, size, shape, enclosure), Color (hue, intensity), Position (x,y), Motion. Use one strategically; overuse creates clutter. **Position and length are the most accurate encoding channels** (Cleveland & McGill, 1984).

**Gestalt principles**: Proximity (group related items), Similarity (consistent color for same series), Enclosure (shading to group), Connection (lines), Continuity (sort bars, time flows), Closure (remove unnecessary axes). Hierarchy: Connection > Enclosure > Proximity > Similarity.

**Executive audiences**: 3–15 seconds per visual. Seek "Are we on track? What needs attention?" Prefer simple charts (bar, line, big number). Want 5–7 hero metrics. Design every executive chart for the 3-second glance test.

---

## Labeling, annotation, and the "so what"

**Direct labeling over legends — always.** Legends force back-and-forth eye movement. Place labels directly on/next to lines and bars. Legends acceptable only when direct labeling creates clutter (>5 overlapping series).

**Action titles, not descriptive titles.** "Revenue Overview" fails. "West Region sales grew 2.5x, driving 60% of Q3 growth" succeeds. The title states the insight. Knaflic: "Never assume it's apparent what's being shown."

**Annotations are the most underused tool.** Annotate: sudden spikes/dips (explain cause), threshold crossings, anomalies needing context. Techniques: reference lines (targets, averages), shaded regions, callout boxes with arrows, selective data labels (not all points).

**The power pairing: Color + Words** (Knaflic). Gray out non-essential data, highlight the key story. Ann K. Emery's four signals: descriptive title, descriptive subtitle, annotations, dark/light contrast.

**Executive slide structure**: Headline = the "so what" insight. Chart = visual evidence. Annotation = context for key data points. Footer = methodology, assumptions, data source.

---

## Chart crimes and misleading patterns

Alberto Cairo (*How Charts Lie*, 2019) identifies five ways charts lie: poorly designed, dubious data, insufficient data, concealing uncertainty, suggesting misleading patterns.

| Crime | Problem | Fix |
|---|---|---|
| **Truncated baseline** | Non-zero Y on bar charts exaggerates differences | Always start bar Y-axes at zero; line charts have flexibility but annotate |
| **Dual-axis misuse** | Two manipulable Y-axes manufacture false correlations | Small multiples, index to common baseline, or connected scatterplots |
| **3D effects** | Perspective distortion, zero information added | Always use 2D |
| **Pie chart overuse** | Poor angle comparison; fail with >5 categories | Bar charts for comparison; limit pies to 2–3 categories |
| **Cherry-picked time ranges** | Selective dates support narrative | Show complete context or note the selection |
| **Rainbow color scales** | Perceptually non-uniform | Use Viridis, Magma, Inferno |
| **Spaghetti charts** | >5–7 overlapping lines unreadable | Small multiples or highlight + gray |
| **Misleading area** | Bubbles scaled by diameter not area | Scale by area |
| **Inverted axes** | Zero at top violates convention | Zero at bottom always |
| **Cumulative hiding decline** | Cumulative always increases | Show both cumulative and per-period |

---

## Color usage

**Three palette types**: Sequential (low→high: Blues, Viridis, Magma), Diverging (center deviation: Blue-Red, Purple-Green), Categorical (distinct groups: Okabe-Ito, Tableau 10).

**Accessible palettes**: Okabe-Ito (8 colors, colorblind gold standard, Nature journals), Viridis family (perceptually uniform, colorblind-safe, grayscale-friendly), ColorBrewer (classic reference, colorbrewer2.org), Paul Tol's schemes.

**Rules**: Max 5–7 distinct colors for categorical data. **Gray + highlight technique** (Knaflic, Wilke): gray out non-essential, ONE bold accent for the key story. ~8% of men, ~0.5% of women have color vision deficiency. Never rely on color alone — pair with shape, pattern, position, or labels. Avoid red-green; use orange-blue. WCAG: 3:1 for large elements, 4.5:1 for small.

**Encoding channel hierarchy** (Cleveland & McGill, 1984): Position on common scale → Length → Angle/Slope → Area → Color saturation → Color hue.

---

## Visualization types for process analysis

| Visualization | Best for | Decision rule |
|---|---|---|
| **Process map / Flowchart** | Sequential steps, decision logic | IF sequence/logic > volume → process map |
| **Sankey diagram** | Flow quantities, multi-path branching | IF complex branching with magnitude → Sankey |
| **Funnel chart** | Linear conversion/attrition | IF strictly sequential pipeline → funnel |
| **Waterfall chart** | Cumulative +/- contributions | IF financial bridge → waterfall |
| **Control chart** | Process stability over time | IF monitoring for special-cause variation → control chart |
| **Pareto chart** | 80/20 analysis, top contributors | IF identifying vital few causes → Pareto |
| **Swimlane diagram** | Cross-functional process, handoffs | IF 4–12 actors/departments → swimlane |
| **Value stream map** | End-to-end lean process with metrics | IF lean/Six Sigma with cycle time → VSM |
| **Gantt chart** | Timeline/scheduling, dependencies | IF parallel tasks with dependencies → Gantt |

**Key comparisons**: Funnel = simple, linear, single-path. Sankey = complex, multi-path, branching with proportional magnitude. If users can skip stages → Sankey. If strictly linear → funnel. For "How did we get from starting revenue to ending profit?" → waterfall. For "Where does our budget go?" → Sankey.
