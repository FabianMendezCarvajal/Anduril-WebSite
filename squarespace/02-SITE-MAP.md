# Site map and section blueprint

Five pages plus the shared header and footer. Each row lists the Squarespace section type, the blocks inside,
the section theme, and where the content comes from.

Section types are the ones in Squarespace 7.1's **Add section** panel. "Blank" means a blank section you fill
with blocks yourself (Fluid Engine). Inner-page tables still say "Lightest 1" / "Darkest 1" where unchanged; Dark = Darkest 1, Light = Lightest 1.

## Navigation

Services · Process · Proof · About · Contact · [Button, inside the overlay menu] Book a free org review

## Home (`/`)

Default theme Darkest 1. "Light" below means Lightest 1 (steel-white).

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank, full width | Dark | **Code Block** hero | `code-blocks/hero-headline.html` |
| 2 | Blank, padding small | Dark | **Code Block** marquee | `code-blocks/marquee.html` |
| 3 | Blank | Dark | Text (manifesto paragraph, Heading 2 weight regular) + Text (small note) | `copy/home.md` §Manifesto |
| 4 | Blank | Dark | Text (eyebrow + H2), **Code Block** ledger | `copy/home.md` §Symptoms + `code-blocks/symptoms-ledger.html` |
| 5 | Blank | **Light** | Text (eyebrow, H2, lede), **Code Block** services list | `copy/home.md` §Services + `code-blocks/services-list.html` |
| 6 | Blank | Dark | Text (eyebrow, H2, lede), **Code Block** process stack | `copy/home.md` §Process + `code-blocks/process-stack.html` |
| 7 | Blank | Dark | Text (eyebrow + H2), **Code Block** proof | `copy/home.md` §Proof + `code-blocks/proof-numbers.html` |
| 8 | Blank, 2 columns | **Light** | Left: Text (eyebrow, H2, lede) + Button. Right: **Code Block** org-health card | `copy/home.md` §Review + `code-blocks/org-health-card.html` |
| 9 | Blank, 2 columns | **Light** | Left: Text (eyebrow + big paragraph). Right: **Code Block** principles | `copy/home.md` §About + `code-blocks/principles.html` |
| 10 | Blank, 2 columns | Dark | Left: Text (eyebrow, H2, email link, contact lines). Right: **Form block** | `copy/home.md` §Contact |

The home page is a long single page that mirrors the preview. The inner pages repeat their section with more
depth so the navigation has proper destinations for SEO.

## Services (`/services`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank | Lightest 1 | Text (eyebrow, H1, lede) | `copy/services.md` §Intro |
| 2 | Blank | **Light** | **Code Block** services list | `code-blocks/services-list.html` |
| 3 | Blank | Lightest 1 | Six Text blocks, one per service (H3 + paragraph + bullets + "Best for") | `copy/services.md` §Service detail |
| 4 | Blank | Lightest 1 | Accordion block: "Questions before you book" | `copy/services.md` §FAQ |
| 5 | Blank | **Darkest 1** | Text (H2) + Button | `copy/services.md` §CTA |

## How we work (`/how-we-work`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank | Lightest 1 | Text (eyebrow, H1, lede) | `copy/how-we-work.md` §Intro |
| 2 | Blank | Dark | **Code Block** process stack | `code-blocks/process-stack.html` |
| 3 | Blank | Lightest 1 | Five Text blocks, one per stage (H3, what happens, what you get) | `copy/how-we-work.md` §Stage detail |
| 4 | Blank | Lightest 1 | Text (H2 "What we won't do") + bullets | `copy/how-we-work.md` §Principles |
| 5 | Blank | **Darkest 1** | Text (H2) + Button | `copy/how-we-work.md` §CTA |

## Clouds (`/clouds`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank | Lightest 1 | Text (eyebrow, H1, lede) | `copy/clouds.md` §Intro |
| 2 | Blank | Dark | **Code Block** clouds list | `code-blocks/clouds-list.html` |
| 3 | Blank | **Darkest 1** | Text (H2) + Button | `copy/clouds.md` §CTA |

## About (`/about`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank, 2 columns | Lightest 1 | Left: Text (eyebrow, H1, lede). Right: Image block (founder photo) | `copy/about.md` §Intro |
| 2 | Blank | **Light** | **Code Block** principles | `code-blocks/principles.html` |
| 3 | Blank | Lightest 1 | Text (H2 "Certifications") + bullets or badge images | `copy/about.md` §Certifications |
| 4 | Blank | **Darkest 1** | Text (H2) + Button | `copy/about.md` §CTA |

## Contact (`/contact`)

| # | Section | Theme | Blocks | Content |
|---|---|---|---|---|
| 1 | Blank, 2 columns | Lightest 1 | Left: Text (eyebrow, H1, lede, contact lines). Right: Form block | `copy/contact.md` |
| 2 | Blank | Lightest 1 | Text (H2 "What happens after you send this") + numbered list | `copy/contact.md` §After |

## Footer (all pages)

Dark. A row of links, then the giant wordmark (`code-blocks/footer-wordmark.html`) and the legal line. Content in `copy/home.md` §Footer.

## Not-found page

Pages → Not linked → System pages → 404. Heading: *This page has been retired.* Body: *Like a Process Builder,
it was replaced by something better. Try the menu above.* Button: Home.
