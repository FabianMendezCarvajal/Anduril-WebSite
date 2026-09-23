# Code blocks

Each file is a self-contained HTML + CSS component. In Squarespace: **Add block → Code**, set *Type* to
**HTML**, untick *Display source*, paste the whole file. None of them require JavaScript, so they work on every
plan. With `code-injection/footer.html` installed (Core plan or higher) they gain motion: reveals, counters,
bar animation, the hero glow and the custom cursor.

| File | Where | Section theme |
|---|---|---|
| `chapter-head.html` | Top of every numbered section (edit number, label, heading) | Dark or light |
| `hero-headline.html` | Home, section 1 (alone in its section) | Dark |
| `marquee.html` | Home, section 2 | Dark |
| `symptoms-ledger.html` | Home, section 3 | Dark |
| `services-list.html` | Home section 5, Services page | Light (paper) |
| `process-stack.html` | Home section 6, How we work page | Dark |
| `proof-numbers.html` | Home section 7 | Dark |
| `clients-grid.html` | Home section 8 (chapter 05), About page | Dark |
| `org-health-card.html` | Home section 9 right column, Contact page | Light |
| `principles.html` | Home section 10 right column, About page | Light |
| `clouds-list.html` | Clouds page | Dark |
| `footer-wordmark.html` | Footer, last section | Dark |

Edit the text directly inside the block. Class names are prefixed `and-` so they never collide with Squarespace's own styles.
