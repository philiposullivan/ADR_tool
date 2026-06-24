# ADR_tool — Action Design Research Quality Assessment Framework

An interactive, browser-based tool for evaluating the **operationalization of Action Design Research (ADR)**, with a focus on **Researcher–Practitioner Collaboration (RPC)**. It helps researchers and reviewers assess how rigorously an ADR project was conducted and reported, based on established ADR principles and empirical findings from the literature.

A self-contained `index.html` — no server, no build step, no dependencies. Open it in a browser and start assessing.

## What it does

The tool scores an ADR study against a structured set of quality criteria organized into three levels of depth. For each criterion the reviewer rates the evidence as **Not Evidenced**, **Partially Evidenced**, or **Fully Evidenced**, and the tool immediately:

- Highlights the guideline description or improvement steps that correspond to the chosen rating.
- Optionally reveals **Guidance & Examples** drawn from published ADR papers (e.g. Sein et al. 2011, Cronholm et al. 2024, Mettler 2018).
- Updates a running **score panel** with a summary assessment and interpretation once all criteria at the chosen level have been rated.

The assessment is grounded in ADR's core ideas — reciprocal shaping of artifact and design principles, co-creation between researchers and practitioners, reflective abstraction, formalization of learning, and generalization.

## Assessment levels

| Level | Name | Cells | Focus |
| --- | --- | --- | --- |
| Level 1 | Parsimonious | 1 (Cell 10) | The single core discriminator — **Mutual Dependency Management** between artifact and principles. Quick check. |
| Level 2 | Mid-Tier | 5 (Cells 10, 5, 6, 12, 18) | Essential quality indicators — context co-creation, reflection, formalization, generalization. Balanced. |
| Level 3 | Comprehensive | 10 (Cells 10, 5, 6, 12, 18, 1, 2, 8, 11, 17) | Complete evaluation across all identified quality criteria for rigorous ADR. |

Use Level 1 for a fast sanity-check, Level 2 for a balanced review, or Level 3 for a deep, in-depth analysis.

## How to use

1. Open `index.html` in any modern browser.
2. Start on the **Overview** tab or jump straight to Level 1 / 2 / 3.
3. For each criterion row, read the description and help text.
4. Click a rating button — **Not**, **Partially**, or **Fully Evidenced**.
5. (Optional) Click **Show Guidance & Examples** for practical tips and illustrations from published ADR papers.
6. Check the **score panel** at the bottom of each level for an aggregate score and interpretation.

## Project structure

```
index.html    # The entire app: markup, CSS (in <style>), and JS logic (in <script>)
README.md
```

## Project structure (detail)

Everything lives in one file on purpose, so the tool is trivially shareable and runs offline:

- **Markup** — header, intro panel, tabbed navigation, level cards, criteria tables, guidance sections, score panels.
- **CSS (embedded)** — design system via CSS variables (colors, shadows, radii), responsive grid layout, tab transitions, card hover effects.
- **JavaScript (embedded)** — tab switching, guideline visibility rules, per-cell scoring (`getCellScore`), level-average calculation (`calculateAverageScore`), aggregate score + interpretation rendering (`updateScores`, `updateScoreDisplay`).

## Requirements

- Any modern web browser. No installation, server, or internet connection required.

## Notes

This is a research-assessment instrument. The criteria, cells, and examples are derived from the ADR methodology literature; treat the scores as a structured aid to qualitative judgment, not as an automated verdict on research quality.
