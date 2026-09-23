# Site map and section blueprint

Five pages plus the shared header and footer. Each row lists the Squarespace section type, the blocks inside,
the section theme, and where the content comes from.

Section types are the ones in Squarespace 7.1's **Add section** panel. "Blank" means a blank section you fill
with blocks yourself (Fluid Engine). "Auto layout" is the *List* section type (Simple list / Carousel / Banner slideshow).

## Navigation

Services · How we work · Clouds · About · Contact · [Button] Book a free org review

## Home (`/`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank, 2 columns | Lightest 1 | Left: Text (eyebrow, H1, lede), Button ×2, Text (clouds line). Right: **Code Block** | `copy/home.md` §Hero + `code-blocks/org-health-card.html` |
| 2 | Blank | Lightest 1 | Text (eyebrow, H2), **Code Block** | `copy/home.md` §Symptoms + `code-blocks/symptoms-strip.html` |
| 3 | Blank | Lightest 1 | Text (eyebrow, H2, lede), **Code Block** | `copy/home.md` §Services + `code-blocks/services-grid.html` |
| 4 | Blank | **Darkest 1** | Text (eyebrow, H2, lede), **Code Block** | `copy/home.md` §Process + `code-blocks/process-steps.html` |
| 5 | Blank | Lightest 1 | Text (eyebrow, H2), **Code Block** | `copy/home.md` §Clouds + `code-blocks/clouds-list.html` |
| 6 | Blank | Lightest 1 | Text (eyebrow, H2), **Code Block**, Text (note) | `copy/home.md` §Results + `code-blocks/results-tiles.html` |
| 7 | Blank, 2 columns | Lightest 1 | Quote block ×2 | `copy/home.md` §Client voices |
| 8 | Blank, 2 columns | Lightest 1 | Left: Text (eyebrow, H2, lede). Right: Text (four short headings + paragraphs) | `copy/home.md` §About |
| 9 | Blank, 2 columns | Lightest 1 | Left: Text (eyebrow, H2, lede, contact lines). Right: **Form block** | `copy/home.md` §Contact |

The home page is a long single page that mirrors the preview. The four inner pages repeat their section with
more depth so the navigation has proper destinations for SEO.

## Services (`/services`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank | Lightest 1 | Text (eyebrow, H1, lede) | `copy/services.md` §Intro |
| 2 | Blank | Lightest 1 | **Code Block** services grid | `code-blocks/services-grid.html` |
| 3 | Blank | Lightest 1 | Six Text blocks, one per service (H3 + paragraph + bullets + "Best for") | `copy/services.md` §Service detail |
| 4 | Blank | Lightest 1 | Accordion block: "Questions before you book" | `copy/services.md` §FAQ |
| 5 | Blank | **Darkest 1** | Text (H2) + Button | `copy/services.md` §CTA |

## How we work (`/how-we-work`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank | Lightest 1 | Text (eyebrow, H1, lede) | `copy/how-we-work.md` §Intro |
| 2 | Blank | **Darkest 1** | **Code Block** process steps | `code-blocks/process-steps.html` |
| 3 | Blank | Lightest 1 | Five Text blocks, one per stage (H3, what happens, what you get) | `copy/how-we-work.md` §Stage detail |
| 4 | Blank | Lightest 1 | Text (H2 "What we won't do") + bullets | `copy/how-we-work.md` §Principles |
| 5 | Blank | **Darkest 1** | Text (H2) + Button | `copy/how-we-work.md` §CTA |

## Clouds (`/clouds`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank | Lightest 1 | Text (eyebrow, H1, lede) | `copy/clouds.md` §Intro |
| 2 | Blank | Lightest 1 | **Code Block** clouds list | `code-blocks/clouds-list.html` |
| 3 | Blank | **Darkest 1** | Text (H2) + Button | `copy/clouds.md` §CTA |

## About (`/about`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank, 2 columns | Lightest 1 | Left: Text (eyebrow, H1, lede). Right: Image block (founder photo) | `copy/about.md` §Intro |
| 2 | Blank | Lightest 1 | Text: four principles | `copy/about.md` §Principles |
| 3 | Blank | Lightest 1 | Text (H2 "Certifications") + bullets or badge images | `copy/about.md` §Certifications |
| 4 | Blank | **Darkest 1** | Text (H2) + Button | `copy/about.md` §CTA |

## Contact (`/contact`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank, 2 columns | Lightest 1 | Left: Text (eyebrow, H1, lede, contact lines). Right: Form block | `copy/contact.md` |
| 2 | Blank | Lightest 1 | Text (H2 "What happens after you send this") + numbered list | `copy/contact.md` §After |

## Footer (all pages)

Darkest 1 theme, three columns, then the legal line. Content in `copy/home.md` §Footer.

## Not-found page

Pages → Not linked → System pages → 404. Heading: *This page has been retired.* Body: *Like a Process Builder,
it was replaced by something better. Try the menu above.* Button: Home.
