# Code blocks (Proposal B, the West)

Each file is a self-contained HTML + CSS component. In Squarespace: **Add block → Code**, set *Type* to
**HTML**, untick *Display source*, paste the whole file. All but one work without JavaScript on every plan; the
celestial chart carries its own script and needs the Core plan or higher.
With `code-injection/footer.html` installed (Core plan or higher) they gain the motion layer: the sheet frame,
contours, reveals, counters, bar animation and the cursor.

| File | Where | Section theme |
|---|---|---|
| `chapter-head.html` | Top of every numbered sheet (edit number, label, heading) | Ivory, vellum or pine |
| `hero-headline.html` | Home, section 1, left column | Ivory |
| `celestial-chart.html` | Home, section 1, under the hero block: the working sky wheel rising from the bottom edge, drawn as an atlas plate, its controls behind a dial at the right (needs JavaScript, Core plan or higher) | Ivory |
| `marquee.html` | Home, section 2, the legend strip | Vellum |
| `symptoms-ledger.html` | Home sheet 02, Terrain | Ivory |
| `services-list.html` | Home sheet 03 Routes, Services page | Vellum |
| `process-stack.html` | Home sheet 04 The survey, How we work page | Ivory |
| `proof-numbers.html` | Home sheet 05 Field notes | Ivory |
| `clients-grid.html` | Home sheet 06 Charted, About page | Ivory |
| `survey-sheet.html` | Home sheet 07 right column, Contact page | Vellum |
| `rose-entry.html` | Home sheet 08 under the paragraph, About page | Ivory |
| `principles.html` | Home sheet 08 right column, About page | Ivory |
| `clouds-list.html` | Clouds page | Ivory |
| `footer-wordmark.html` | Footer, last section | Pine |

Edit the text directly inside the block. Class names are prefixed `and-` so they never collide with Squarespace's own styles.
