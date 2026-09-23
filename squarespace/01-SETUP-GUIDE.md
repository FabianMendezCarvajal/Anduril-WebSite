# Anduril on Squarespace: build guide

This guide turns the design in `preview/index.html` into a live Squarespace 7.1 site. The design is
art-directed after current Awwwards-winning agency sites; see `03-DESIGN-REFERENCES.md` for what was borrowed
and why. Build time: about a day if you follow it top to bottom.

| What | Where it goes in Squarespace | File |
|---|---|---|
| Page structure | Pages panel | `02-SITE-MAP.md` |
| Page text | Text blocks on each page | `copy/*.md` |
| Colours, fonts, header, buttons, forms, cursor, grain | Design → Custom CSS | `custom-css.css` |
| Fonts + motion scripts | Settings → Advanced → Code Injection | `code-injection/header.html`, `footer.html` |
| Designed components | Code Blocks on the relevant page | `code-blocks/*.html` |

## Plan requirement

* **Custom CSS** works on every plan. That covers the palette, type, the transparent blend-mode header, the
  ember overlay menu, pill buttons, underline form fields and the film grain.
* **Code Blocks** with HTML and CSS work on every plan. Every component in `code-blocks/` is HTML and CSS only.
* **Code Injection** (Core plan or higher, formerly "Business") adds the motion layer: custom cursor, scroll
  reveals, counting numbers, animated bars, the hero glow and the local clock. Without it the site is still
  complete, just still.

## Step 1: Create the site

1. squarespace.com → **Get started** → choose a minimal 7.1 template (*Bailard*, *Marquee* or *Paloma*). You
   replace the styling anyway.
2. Site title: **ANDURIL** (all caps). Settings → Site availability → keep private until launch.
3. Settings → Domains → connect your domain when ready.

## Step 2: Set the colour palette

Design → Colors → **Edit palette**:

| Slot | Hex | Used for |
|---|---|---|
| White | `#EEF0F2` | steel-white counter sections |
| Light accent | `#E2E6EA` | subtle panels on light sections |
| Accent | `#FF5A2D` | ember: buttons, links, labels, overlay menu |
| Dark accent | `#181D25` | cards on dark sections |
| Black | `#0E1116` | forge black: the default ground |

Section themes you will use:

* **Darkest 1** (default): background Black, headings `#ECEFF3`, paragraph `#B9C0CB`, button Accent with text Black.
* **Lightest 1**: background White, headings Black, paragraph `#3A4454`, button Black with text White.

Set the site default theme to **Darkest 1** (Design → Colors → Site default section theme).

## Step 3: Set the fonts

Design → Fonts → **Global text styles**.

* Headings: **Bricolage Grotesque** if listed, otherwise **Sora**; the Custom CSS forces Bricolage Grotesque via Google Fonts regardless.
* Paragraphs: **IBM Plex Sans**. Buttons and miscellaneous: **IBM Plex Mono**.

Sizes (Design → Fonts → Assign styles): Heading 1 ≈ 8 rem desktop, Heading 2 ≈ 4.5 rem, Heading 3 ≈ 1.6 rem,
Paragraph 1.06 rem, line height 1.6. Heading letter-spacing `-0.04em`. Custom CSS refines these.

## Step 4: Buttons and spacing

* Design → Buttons: Primary solid, shape **pill**, padding large. Secondary outline, pill.
* Design → Spacing: section padding *large*; site width *wide*.

## Step 5: Custom CSS

Design → **Custom CSS** → paste the full contents of `custom-css.css`. Save.

Two lines in that file hide the inline navigation and show the burger on every screen size, which gives the
full-screen ember overlay menu. If you would rather keep visible links on desktop, comment them out (they are
marked in the file).

## Step 6: Code Injection (Core plan or higher)

Settings → Advanced → **Code Injection**.

* **Header**: paste `code-injection/header.html`.
* **Footer**: paste `code-injection/footer.html`.

Skip on lower plans; fonts still load through the `@import` at the top of the Custom CSS.

## Step 7: Header

Edit → Header.

1. Site title **ANDURIL**. The CSS adds the ember diamond before it.
2. Navigation order: Services, Process, Proof, About, Contact (these are the pages from Step 8; Proof is an
   anchor link to the home page's proof section: `/#proof`).
3. Elements → **Button** on: text *Book a free org review*, link to Contact, style Primary. It appears inside the overlay menu.
4. Style: **transparent** background, fixed position on, no blur. The CSS sets `mix-blend-mode: difference` so
   the header inverts over dark and light sections.
5. Mobile / overlay menu: Design → Colors → **Header menu** theme: background Accent, text Black. The CSS makes the links huge.

## Step 8: Create the pages

Follow `02-SITE-MAP.md`. Recipe for every section:

1. Pages → **+** → Blank Page → name it.
2. **Add section** → Blank → set its theme (Darkest 1 or Lightest 1) and padding.
3. Drop in the blocks listed. Text blocks take the copy from `copy/<page>.md`; labels marked *Eyebrow* use the
   Monospace text style so the CSS styles them as small tracked labels.
4. **Code Blocks**: Add block → **Code** → Type **HTML**, untick *Display source*, paste from `code-blocks/`.
5. Hero section: set the section to **full width** and the block to span the whole row.

Set Home as the homepage (Pages → hover Home → gear → *Set as homepage*).

## Step 9: Contact form

Contact page, right column, **Form Block**:

| Field | Type |
|---|---|
| Your name | Name, required |
| Company | Text, required |
| Work email | Email, required |
| Salesforce products in use | Select: Sales Cloud / Service Cloud / Sales + Service Cloud / Marketing Cloud / Several clouds / Not on Salesforce yet |
| What is not working today? | Text area |

Storage: **Email** to your address. Button text: *Request the review*. Post-submit message: *Thanks. A
consultant, not a sequence, will reply within one business day.*

**Leads into Salesforce:** Form → Storage → **Zapier** (or Make). Trigger "Squarespace: New Form Submission" →
action "Salesforce: Create Lead". Map Company, Name, Email; put the select answer in a custom Lead field.

## Step 10: Footer

Edit → Footer, Darkest 1 theme, two sections:

1. A row: left, a Text block with the five page links in Monospace style; right, LinkedIn · Trailblazer · Privacy.
2. A full-width section, padding none, with **Code Block** `code-blocks/footer-wordmark.html`, then a small Text
   block with the copyright and the Salesforce trademark disclaimer from `copy/home.md`. Keep the disclaimer.

## Step 11: SEO and launch checklist

* Settings → SEO → title format `%p | Anduril · Salesforce consultancy`; description from `copy/home.md`.
* Each page: Page settings → SEO → paste its meta description.
* Favicon: a 512×512 ember diamond on forge black. Social sharing image 1200×630: "Salesforce, reforged." on forge black.
* Replace every placeholder: `hello@your-domain.com`, the three case cards, the three numbers, the availability line.
* Test on a phone: overlay menu opens and closes, form submits, code-block grids stack, the marquee scrolls.
* Check the header over the light sections: it should invert to dark text automatically.
* Settings → Site availability → **Public**.

## Things you may want to change

* **Name check.** "Anduril" is also the name of Anduril Industries, a large US defence company. Check trademark
  registrations in your country before investing in the domain.
* **"Salesforce Partner" wording.** Copy says *independent Salesforce consultancy*. Say *Salesforce Consulting
  Partner* only if registered in the partner program.
* **Numbers and case cards** are illustrative. Replace them before going public.
