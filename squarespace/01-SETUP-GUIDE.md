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
| White | `#F1EFEA` | paper counter sections |
| Light accent | `#E6E3DD` | subtle panels on light sections |
| Accent | `#E0663A` | copper: italic emphasis, hover sweeps, small marks |
| Dark accent | `#141821` | cards on dark sections |
| Black | `#0B0D11` | forge black: the default ground |

Section themes you will use:

* **Darkest 1** (default): background Black, headings `#EDEBE6`, paragraph `#B4B6BC`, primary button `#EDEBE6` with text Black.
* **Lightest 1**: background White, headings Black, paragraph `#454A55`, primary button Black with text White.

Set the site default theme to **Darkest 1** (Design → Colors → Site default section theme).

## Step 3: Set the fonts

Design → Fonts → **Global text styles**.

* Headings: **Bricolage Grotesque** if listed, otherwise **Sora**; the Custom CSS forces Bricolage Grotesque via Google Fonts regardless.
* Paragraphs: **IBM Plex Sans**. Buttons and miscellaneous: **IBM Plex Mono**.
* The serif italic counterpoint (**Instrument Serif**) loads from the CSS. To use it, select a word in any heading and press Cmd/Ctrl+I: italics inside headings render in the serif, and in H1/H2 they take the copper colour. The copy files mark these words with *asterisks*.

Sizes (Design → Fonts → Assign styles): Heading 1 ≈ 8 rem desktop, Heading 2 ≈ 4.5 rem, Heading 3 ≈ 1.6 rem,
Paragraph 1.06 rem, line height 1.6. Heading letter-spacing `-0.04em`. Custom CSS refines these.

Section headings in the copy carry a chapter number (01 to 08). Every numbered section starts with the same
`code-blocks/chapter-head.html` block: hairline on top, the number and label on one baseline at left, the heading
at right. Copy the block, change the number, the label and the heading, and add the `light` class on paper sections.

## Step 4: Buttons and spacing

* Design → Buttons: Primary solid, shape **pill**, padding large. Secondary outline, pill.
* Design → Spacing: section padding *large*; site width *wide*.

## Step 5: Custom CSS

Design → **Custom CSS** → paste the full contents of `custom-css.css`. Save.

Two lines in that file hide the inline navigation and show the burger on every screen size, which gives the
full-screen paper overlay menu. If you would rather keep visible links on desktop, comment them out (they are
marked in the file).

## Step 6: Code Injection (Core plan or higher)

Settings → Advanced → **Code Injection**.

* **Header**: paste `code-injection/header.html`.
* **Footer**: paste `code-injection/footer.html`.

Skip on lower plans; fonts still load through the `@import` at the top of the Custom CSS.

## Step 7: Header

Edit → Header.

1. Site title **ANDURIL**. The CSS adds the ember diamond before it.
2. Navigation order: Services, Process, Proof, Clients, About, Contact (pages from Step 8; Proof and Clients
   are anchor links to the home page sections: `/#proof`, `/#clients`).
3. Elements → **Button** on: text *Book a free org review*, link to Contact, style Primary. It appears inside the overlay menu.
4. Style: **transparent** background, fixed position on, no blur. The CSS sets `mix-blend-mode: difference` so
   the header inverts over dark and light sections.
5. Mobile / overlay menu: Design → Colors → **Header menu** theme: background White (paper), text Black. The CSS makes the links large and light.

## Step 8: Create the pages

Follow `02-SITE-MAP.md`. Recipe for every section:

1. Pages → **+** → Blank Page → name it.
2. **Add section** → Blank → set its theme (Darkest 1 or Lightest 1) and padding.
3. Drop in the blocks listed. Text blocks take the copy from `copy/<page>.md`; labels marked *Eyebrow* use the
   Monospace text style so the CSS styles them as small tracked labels.
4. **Code Blocks**: Add block → **Code** → Type **HTML**, untick *Display source*, paste from `code-blocks/`.
5. Hero section: set the section to **full width** and the block to span the whole row.

Set Home as the homepage (Pages → hover Home → gear → *Set as homepage*).

## Step 9: Client logos

The clients grid (`code-blocks/clients-grid.html`) ships with invented placeholder wordmarks. To show real clients:

1. Get a horizontal SVG (or transparent PNG, at least 600 px wide) and written permission from each client.
2. Design → Custom CSS → **Manage Custom Files** → upload the logo → click it to copy its URL.
3. In the code block, replace `<span class="and-logo-text">Northwind</span>` with `<img src="PASTE-URL" alt="Client name">`.
4. Edit the `and-tag` text to the client's industry and the cloud you worked in.
5. Delete the "Placeholder wordmarks" note.

Native alternative without code: Add section → **Gallery** → *Grid: Simple*, 4 columns, upload the logos, and add
`.gallery-grid-image img { filter: grayscale(1); opacity: .62; }` to the Custom CSS. You lose the hover tags.

## Step 10: Contact form

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

## Step 11: Footer

Edit → Footer, Darkest 1 theme, two sections:

1. A row: left, a Text block with the five page links in Monospace style; right, LinkedIn · Trailblazer · Privacy.
2. A full-width section, padding none, with **Code Block** `code-blocks/footer-wordmark.html`, then a small Text
   block with the copyright and the Salesforce trademark disclaimer from `copy/home.md`. Keep the disclaimer.

## Step 12: SEO and launch checklist

* Settings → SEO → title format `%p | Anduril · Salesforce consultancy`; description from `copy/home.md`.
* Each page: Page settings → SEO → paste its meta description.
* Favicon: a 512×512 copper diamond on forge black. Social sharing image 1200×630: "Salesforce, *reforged.*" on forge black, the second word in the serif italic.
* Replace every placeholder: `hello@your-domain.com`, the three case cards, the three numbers, the eight client logos, the availability line.
* Test on a phone: overlay menu opens and closes, form submits, code-block grids stack, the marquee scrolls.
* Check the header over the light sections: it should invert to dark text automatically.
* Settings → Site availability → **Public**.

## Things you may want to change

* **Name check.** "Anduril" is also the name of Anduril Industries, a large US defence company. Check trademark
  registrations in your country before investing in the domain.
* **"Salesforce Partner" wording.** Copy says *independent Salesforce consultancy*. Say *Salesforce Consulting
  Partner* only if registered in the partner program.
* **Numbers and case cards** are illustrative. Replace them before going public.
