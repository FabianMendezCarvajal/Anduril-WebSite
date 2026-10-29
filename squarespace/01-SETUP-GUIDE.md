# Anduril on Squarespace: build guide

This guide turns the design in `preview/index.html` into a live Squarespace 7.1 site. The design applies
**Proposal B, the West** from the Anduril Visual Identity project: a compass rose that points west, Fraunces
italic, ivory paper, pine ink and a line of gilt. See `03-DESIGN-REFERENCES.md` for the system and what was
borrowed from award-winning sites. Build time: about a day if you follow it top to bottom.

| What | Where it goes in Squarespace | File |
|---|---|---|
| Page structure | Pages panel | `02-SITE-MAP.md` |
| Page text | Text blocks on each page | `copy/*.md` |
| Colours, fonts, header, buttons, forms, cursor, grain, sheet frame | Design → Custom CSS | `custom-css.css` |
| Logo files | Header logo, favicon, social image | `assets/` |
| Fonts + motion scripts | Settings → Advanced → Code Injection | `code-injection/header.html`, `footer.html` |
| Designed components | Code Blocks on the relevant page | `code-blocks/*.html` |

## Plan requirement

* **Custom CSS** works on every plan. That covers the palette, type, the ivory header with the italic wordmark, the
  pine overlay menu, squared buttons, underline form fields, the paper grain, and the night palette that follows the
  visitor's system setting.
* **Code Blocks** with HTML and CSS work on every plan. Every component in `code-blocks/` is HTML and CSS only.
* **Code Injection** (Core plan or higher, formerly "Business") adds the motion layer: the star sky behind every sheet, the day/night switch (a sun
  and a moon in the header), the sheet frame with ticks, the contours, the custom cursor (a sun by day, a moon by night), scroll reveals, counting
  numbers, animated bars and the local clock. Without it the site is still complete, just still, and night mode
  follows the visitor's system setting with no manual switch.

## Step 1: Create the site

1. squarespace.com → **Get started** → choose a minimal 7.1 template (*Bailard*, *Marquee* or *Paloma*). You
   replace the styling anyway.
2. Site title: **Anduril** (title case; the CSS sets it in Fraunces italic). Settings → Site availability → keep private until launch.
3. Settings → Domains → connect your domain when ready.

## Step 2: Set the colour palette

Design → Colors → **Edit palette**:

| Slot | Hex | Name in the identity | Used for |
|---|---|---|---|
| White | `#F4EFE4` | Ivory | the ground: pages, cards, print |
| Light accent | `#E9E2D0` | Vellum | panels and alternate sections |
| Accent | `#C9A14B` | Gilt | the flame of the West: one point, one word, one line per surface. Never body text. |
| Dark accent | `#3F6D58` | Moss | secondary text and contours |
| Black | `#143D31` | Pine | the ink, and the ground of the footer and contact section |

Proportion: 78 ivory, 18 pine, 4 gilt. Two more values live only in the CSS: Gilt Deep `#7A5D18` for italic
phrases on ivory (gilt itself fails contrast as text) and Sage `#6E8A7D` for labels.

Section themes you will use:

* **Lightest 1** (default): background White (ivory), headings Black (pine), paragraph `#3F6D58`, primary button Black with text White.
* **Lightest 2**: background Light accent (vellum), the same text colours. For the Routes, the free survey and the legend strip.
* **Darkest 1**: background Black (pine), headings White (ivory), paragraph `#7E9A8C`, primary button White with text Black. For Coordinates and the footer.

Set the site default theme to **Lightest 1** (Design → Colors → Site default section theme).

**The star sky.** The footer script lays a fixed star field behind every section: ivory stars with a slow twinkle
and a rare meteor by night, the same field printed faintly in pine on the paper by day. Ivory sections are
transparent so it shows through; vellum and pine sections are lightly translucent. Delete the first block of the
footer script to turn it off.

**Night.** The site has a night palette: the pine set reversed, ivory as the ink, pine deep `#0E2B23` as the paper,
vellum becoming `#123529`, hairlines `#22493D`, and gilt reading directly on the ground. It switches with the sun
and moon button that the footer script adds to the header, remembers the choice on the visitor's device, and
otherwise follows the system setting. The celestial chart's disc is always night; only its ring and caption change.
The legend band under the hero runs against the paper for contrast: a pine band with ivory type by day, a
vellum band with moss type by night (the `--and-band` tokens).

## Step 3: Set the fonts

Design → Fonts → **Global text styles**.

* Headings: **Fraunces** (it is in the picker). Weight 500. The Custom CSS sets the optical size to 144 and SOFT to 30.
* Paragraphs: **Instrument Sans** 400. Buttons: Instrument Sans 600. Miscellaneous: **DM Mono**.

Sizes (Design → Fonts → Assign styles): Heading 1 ≈ 7 rem desktop, Heading 2 ≈ 4.5 rem, Heading 3 ≈ 1.6 rem,
Paragraph 1.06 rem, line height 1.55. Heading letter-spacing `-0.02em`.

**The turn of phrase.** Select a word or two in any heading and press Cmd/Ctrl+I: italics inside headings
render in Fraunces italic with the wonky alternates, in Gilt Deep on ivory and Gilt on pine. The copy files mark
these words with *asterisks*. One turn of phrase per heading.

Section headings carry a sheet number (02 to 09). Every numbered section starts with the same
`code-blocks/chapter-head.html` block: a hairline with survey ticks, the number in Fraunces italic and the label in
DM Mono on one baseline at left, the heading at right. Copy the block, change the number, the label and the
heading, and add the `pine` class on the pine section.

## Step 4: Buttons and spacing

* Design → Buttons: Primary solid, shape **square** (corner radius 2 px), padding medium. Secondary outline, square. The CSS sets the DM Mono label and the gilt hover.
* Design → Spacing: section padding *large*; site width *wide* (the CSS caps content at 1360 px).

## Step 5: Custom CSS

Design → **Custom CSS** → paste the full contents of `custom-css.css`. Save.

The header keeps inline links on desktop (Survey · Services · Field notes · Contact) and uses Squarespace's
burger on mobile, which the CSS turns into a full-screen pine overlay with large Fraunces links.

## Step 6: Code Injection (Core plan or higher)

Settings → Advanced → **Code Injection**.

* **Header**: paste `code-injection/header.html`.
* **Footer**: paste `code-injection/footer.html`.

Skip on lower plans; fonts still load through the `@import` at the top of the Custom CSS.

## Step 7: Header

Edit → Header.

1. Site title **Anduril**. The CSS sets it in Fraunces italic, SOFT 50, with the wonky alternates: the recommended
   wordmark cut from the identity. Keep it as text, not an image.
2. Logo: upload `assets/rose-on-ivory.svg` as the logo **beside** the title (Header → Site title & logo → choose
   "logo and title" if your template offers it; otherwise upload the horizontal lockup exported from the identity
   canvas, board B1). Height 30 px.
3. Navigation order: Survey, Services, Field notes, Contact. Survey is an anchor to the home page (`/#survey`);
   Field notes is the Findings page.
4. Elements → **Button** on: text *Book a survey*, link to Contact, style Primary.
5. Style: **solid** background, fixed position on. The CSS makes it translucent ivory with a hairline beneath.
6. Mobile menu: Design → Colors → **Header menu** theme: background Black (pine), text White (ivory).

## Step 8: Create the pages

Follow `02-SITE-MAP.md`. Recipe for every section:

1. Pages → **+** → Blank Page → name it.
2. **Add section** → Blank → set its theme (Lightest 1 ivory, Lightest 2 vellum, or Darkest 1 pine) and padding.
3. Drop in the blocks listed. Text blocks take the copy from `copy/<page>.md`; labels marked *Coordinates* use the
   Monospace text style so the CSS sets them in DM Mono as small tracked labels.
4. **Code Blocks**: Add block → **Code** → Type **HTML**, untick *Display source*, paste from `code-blocks/`.
5. Hero section: one tall full-width section. The hero block, centred, with the **celestial chart** block
   (`code-blocks/celestial-chart.html`) anywhere in the same section. The chart positions itself: its disc becomes
   the section's background, a planisphere wheel rising from the bottom edge with its top half in view, and its
   controls fold into a small round dial at the right, beside the wheel, that opens a panel with the *Turn the sky*
   buttons, the caption and the coordinates (the Custom CSS makes the first section clip it and reserves the space).
   The chart faces south in the northern hemisphere so the ecliptic, Sun and Moon are in the visible half. The chart is a working planisphere: it computes the sky above your
   coordinates right now (bright stars, the ecliptic with the twelve zodiac signs, the Sun, the Moon and its
   phase) inside a calendar ring that marks today, and refreshes every thirty seconds. Set your coordinates in the
   block's two `data-lat` / `data-lon` attributes; visitors can also type their own or press *Use my location*.
   It carries its own script, so it needs the Core plan or higher; on lower plans leave the right column empty and
   the hero's contours take its place.
6. The method (home sheet 04 and the How we work page): one **Code Block** with `code-blocks/method-routes.html`
   under its chapter head. The six route tabs are CSS only and work on every plan. Use the same block on both pages;
   the services list links each service to its route on How we work (`/how-we-work#and-route-crm` and so on).

Set Home as the homepage (Pages → hover Home → gear → *Set as homepage*).

## Step 9: Client logos

The clients grid (`code-blocks/clients-grid.html`) shows two clients, FIFA World Cup 26 and Colsubsidio, with their one-colour
white logos embedded in the block on a pine panel, so it works as pasted. The source files are in `assets/clients/` (see its README for where each came from).

Before publishing:

1. Confirm each client's written permission to show its logo. FIFA in particular controls every use of the FIFA World
   Cup 26 emblem; ask your FIFA contact for the approved artwork and usage terms, and swap it in if it differs.
2. Check that each brand allows its one-colour white (reverse) version on a dark background, and use the client's own white
   artwork if they supply it. Don't crop or redraw either logo.

To add a client: copy a cell, upload the client's white logo under Design → Custom CSS → **Manage Custom Files**, click it to copy its
URL, and use that as the `img src` (class `tall` for upright marks, `wide` for wordmarks). Edit the `and-tag` text to the
client's industry and place, or the route you took with them. With four or more clients, change the grid to `repeat(4,…)`.

## Step 10: Contact form

Contact page, right column, **Form Block**:

| Field | Type |
|---|---|
| Your name | Name, required |
| Company | Text, required |
| Work email | Email, required |
| Where should we start? | Select: Digital transformation / CRM / Data & analytics / Custom solutions / Integrations & automation / Managed services & adoption / Not sure yet |
| What is not working today? | Text area |

Storage: **Email** to your address. Button text: *Book the survey*. Post-submit message: *Thanks. A consultant,
not a sequence, will reply within one business day.*

**Leads into your CRM:** Form → Storage → **Zapier** (or Make). Trigger "Squarespace: New Form Submission" →
action "Create Lead" in your CRM (Salesforce, HubSpot and most others have one). Map Company, Name, Email; put the
route from the select in a custom field so each lead arrives sorted by route.

## Step 11: Coordinates and footer

The contact section and the footer share one pine ground, as the identity's proportion asks (78 ivory, 18 pine, 4 gilt).

1. Contact page, Darkest 1 theme: `chapter-head.html` with class `pine` (09 Coordinates, "Let's *chart it.*"),
   then two columns: left the email link and the three contact lines, right the Form block.
2. Edit → Footer, Darkest 1 theme, two sections: a row of links in Monospace style (left: Survey · Services · How we
   work · Platforms · Field notes · Clients · About · Contact; right: LinkedIn · Privacy), then a full-width section,
   padding none, with **Code Block** `code-blocks/footer-wordmark.html` (the rose in ivory above the wordmark) and a
   small Text block with the copyright, "Transformation, mapped." and the two disclaimers from `copy/home.md`. Keep both disclaimers.

## Step 12: SEO and launch checklist

* Settings → SEO → title format `%p | Anduril · Digital transformation`; description from `copy/home.md`.
* Each page: Page settings → SEO → paste its meta description.
* Favicon: export `assets/favicon.svg` at 512×512 (the rose on ivory). Social sharing image 1200×630: "Know the ground *before you change it.*" in Fraunces on ivory with the rose, or the profile banner from the identity canvas (board B4).
* Coordinates: the celestial chart and the sheet frame use sample coordinates (51.5074° N, 0.1278° W, London). Set your office's in the chart block's `data-lat` and `data-lon` so the default sky is yours.
* The header's centre line shows only the consultancy label and the local clock; add an availability note there if you want one.
* Replace every placeholder: `hello@your-domain.com`, the three case cards, the three numbers, the availability line.
* Test on a phone: overlay menu opens and closes, form submits, code-block grids stack, the marquee scrolls, the method's route tabs switch.
* Test the route links: open a service row on Services, click *See the route*, and check that How we work opens on that route.
* Check the sheet frame on a phone: it tightens to 8 px and drops the coordinate label.
* Settings → Site availability → **Public**.

## Things you may want to change

* **Name check.** "Anduril" is also the name of Anduril Industries, a large US defence company, and Middle-earth
  names are trademarked in several categories. Check registrations in your country before investing in the domain.
  The rose, the palette and the type are yours; only the name and its meaning come from Tolkien.
* **Partner wording.** Copy says *independent consultancy* and names Salesforce as the CRM we implement. Say
  *Salesforce Consulting Partner* (or any other vendor's partner title) only if registered in that partner program.
* **Platforms.** `code-blocks/platforms-list.html` names categories for data and BI rather than products. Name the
  warehouse and BI tools you are certified in once you have chosen which to show.
* **Numbers and case cards** are illustrative. Replace them before going public.
