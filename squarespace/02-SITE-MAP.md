# Site map and section blueprint

Five pages plus the shared header and footer. Each row lists the Squarespace section type, the blocks inside,
the section theme, and where the content comes from.

Section types are the ones in Squarespace 7.1's **Add section** panel. "Blank" means a blank section you fill
with blocks yourself (Fluid Engine). Ivory = Lightest 1, Vellum = Lightest 2, Pine = Darkest 1.

## Navigation

Survey (`/#survey`) · Services · Field notes · Contact · [Button] Book a survey. The overlay menu on mobile lists all seven sections.

## Home (`/`)

Default theme Lightest 1 (ivory). "Vellum" = Lightest 2. "Pine" = Darkest 1.

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank, 2 columns | Ivory | Left: **Code Block** hero. Right: **Code Block** celestial chart | `code-blocks/hero-headline.html` + `code-blocks/celestial-chart.html` |
| 2 | Blank, padding none | Vellum | **Code Block** legend strip | `code-blocks/marquee.html` |
| 3 | Blank | Ivory | Text (manifesto paragraph in Fraunces) + Text (small note on the name) | `copy/home.md` §Manifesto |
| 4 | Blank | Ivory | **Code Block** chapter head (02 Terrain), **Code Block** ledger | `copy/home.md` §Terrain + `code-blocks/symptoms-ledger.html` |
| 5 | Blank | Vellum | **Code Block** chapter head (03 Routes), **Code Block** services list | `copy/home.md` §Routes + `code-blocks/services-list.html` |
| 6 | Blank | Ivory | **Code Block** chapter head (04 The survey), **Code Block** process stack | `copy/home.md` §The survey + `code-blocks/process-stack.html` |
| 7 | Blank | Ivory | **Code Block** chapter head (05 Field notes), **Code Block** proof | `copy/home.md` §Field notes + `code-blocks/proof-numbers.html` |
| 8 | Blank | Ivory | **Code Block** chapter head (06 Charted), **Code Block** clients grid, Text (note) + Button | `copy/home.md` §Charted + `code-blocks/clients-grid.html` |
| 9 | Blank, then 2 columns | Vellum | **Code Block** chapter head (07 The free survey); below it, left: Text (lede) + Button, right: **Code Block** survey sheet | `copy/home.md` §The free survey + `code-blocks/survey-sheet.html` |
| 10 | Blank, then 2 columns | Ivory | **Code Block** chapter head (08 The map-maker); below it, left: Text (serif paragraph) + **Code Block** rose entry, right: **Code Block** principles | `copy/home.md` §The map-maker + `code-blocks/rose-entry.html` + `code-blocks/principles.html` |
| 11 | Blank, then 2 columns | **Pine** | **Code Block** chapter head `pine` (09 Coordinates); below it, left: Text (email link, contact lines), right: **Form block** | `copy/home.md` §Coordinates |

Every chapter header is the same block (`code-blocks/chapter-head.html`) with a different sheet number, label and
heading: a hairline with survey ticks, the number and label at left, the heading at right.

## Services (`/services`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank | Lightest 1 | Text (eyebrow, H1, lede) | `copy/services.md` §Intro |
| 2 | Blank | Vellum | **Code Block** services list | `code-blocks/services-list.html` |
| 3 | Blank | Lightest 1 | Six Text blocks, one per service (H3 + paragraph + bullets + "Best for") | `copy/services.md` §Service detail |
| 4 | Blank | Lightest 1 | Accordion block: "Questions before you book" | `copy/services.md` §FAQ |
| 5 | Blank | **Pine** | Text (H2) + Button | `copy/services.md` §CTA |

## Field notes (`/field-notes`)

The Findings page: numbers and case sheets, plus room for written notes later.

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank | Ivory | **Code Block** chapter head (Field notes) | `copy/home.md` §Field notes |
| 2 | Blank | Ivory | **Code Block** proof | `code-blocks/proof-numbers.html` |
| 3 | Blank | Ivory | Blog or Summary block for written notes when you have them | |
| 4 | Blank | **Pine** | Text (H2) + Button | *Book a survey* → `/contact` |

## How we work (`/how-we-work`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank | Lightest 1 | Text (eyebrow, H1, lede) | `copy/how-we-work.md` §Intro |
| 2 | Blank | Ivory | **Code Block** process stack | `code-blocks/process-stack.html` |
| 3 | Blank | Lightest 1 | Five Text blocks, one per stage (H3, what happens, what you get) | `copy/how-we-work.md` §Stage detail |
| 4 | Blank | Lightest 1 | Text (H2 "What we won't do") + bullets | `copy/how-we-work.md` §Principles |
| 5 | Blank | **Darkest 1** | Text (H2) + Button | `copy/how-we-work.md` §CTA |

## Clouds (`/clouds`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank | Lightest 1 | Text (eyebrow, H1, lede) | `copy/clouds.md` §Intro |
| 2 | Blank | Ivory | **Code Block** clouds list | `code-blocks/clouds-list.html` |
| 3 | Blank | **Darkest 1** | Text (H2) + Button | `copy/clouds.md` §CTA |

## About (`/about`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank, 2 columns | Ivory | Left: Text (coordinates, H1, lede) + **Code Block** rose entry. Right: Image block (founder photo) | `copy/about.md` §Intro + `code-blocks/rose-entry.html` |
| 2 | Blank | Ivory | **Code Block** principles | `code-blocks/principles.html` |
| 2b | Blank | Ivory | **Code Block** chapter head (Charted) + **Code Block** clients grid | `code-blocks/clients-grid.html` |
| 3 | Blank | Lightest 1 | Text (H2 "Certifications") + bullets or badge images | `copy/about.md` §Certifications |
| 4 | Blank | **Darkest 1** | Text (H2) + Button | `copy/about.md` §CTA |

## Contact (`/contact`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank, 2 columns | Lightest 1 | Left: Text (eyebrow, H1, lede, contact lines). Right: Form block | `copy/contact.md` |
| 2 | Blank | Lightest 1 | Text (H2 "What happens after you send this") + numbered list | `copy/contact.md` §After |

## Footer (all pages)

Pine. A row of links, then the rose and the giant italic wordmark (`code-blocks/footer-wordmark.html`) and the legal lines. Content in `copy/home.md` §Footer.

## Not-found page

Pages → Not linked → System pages → 404. Heading: *This page has been retired.* Body: *Like a Process Builder,
it was replaced by something better. Try the menu above.* Button: Home.
