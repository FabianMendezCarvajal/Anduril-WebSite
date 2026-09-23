# Anduril on Squarespace: build guide

This guide turns the design in `preview/index.html` into a live Squarespace 7.1 site.
Total build time: about half a day if you follow it top to bottom.

Everything you paste is in this folder:

| What | Where it goes in Squarespace | File |
|---|---|---|
| Page structure | Pages panel | `02-SITE-MAP.md` |
| Page text | Text blocks on each page | `copy/*.md` |
| Colours, fonts, buttons, forms | Design → Custom CSS | `custom-css.css` |
| Fonts + small scripts | Settings → Advanced → Code Injection | `code-injection/header.html`, `footer.html` |
| Designed components | Code Blocks on the relevant page | `code-blocks/*.html` |

## Plan requirement

* **Custom CSS** works on every Squarespace plan.
* **Code Injection** and **JavaScript inside Code Blocks** need the Core plan or higher (formerly "Business").
* Every code block in this kit is HTML and CSS only, so the *components* work on any plan. Only the small
  scripts in `code-injection/footer.html` (mobile menu polish, bar animation) need Core or higher. The site
  looks and works fine without them.

## Step 1: Create the site

1. Go to squarespace.com → **Get started** → pick any minimal template (Squarespace 7.1; all current
   templates are). Good starting points: *Bailard*, *Marquee* or *Paloma*. You will replace the styling anyway.
2. Site title: **Anduril**. Settings → Site availability → keep it private until launch.
3. Settings → Domains → connect your domain when ready.

## Step 2: Set the colour palette

Design → Colors → **Edit palette**. Set the five palette colours:

| Slot | Hex | Used for |
|---|---|---|
| White | `#EDF0F3` | page ground (cool steel) |
| Light accent | `#E2E7EC` | subtle panels |
| Accent | `#E4572E` | ember: buttons, links, eyebrow labels |
| Dark accent | `#14213A` | dark surfaces |
| Black | `#0B1422` | text on light, ground on dark sections |

Then set the **section themes** you will use:

* **Lightest 1** (default for most sections): background White, headings Black, paragraph `#33415A`, button background Accent, button text `#FFFFFF`.
* **Darkest 1** (used for *How we work* and the footer): background Black, headings `#E8EDF3`, paragraph `#94A3B8`, button background Accent.

Custom CSS refines everything else.

## Step 3: Set the fonts

Design → Fonts → **Global text styles**.

* Headings: search **Bricolage Grotesque**. If your font picker does not list it, pick **Sora** for now;
  the Custom CSS in Step 5 forces Bricolage Grotesque on headings via Google Fonts regardless.
* Paragraphs: **IBM Plex Sans** (available in the picker).
* Buttons: same as paragraphs, weight 600.
* Miscellaneous (labels, nav): **IBM Plex Mono** if listed, otherwise leave as paragraph font.

Sizes (Design → Fonts → Assign styles): Heading 1 ≈ 5 rem desktop, Heading 2 ≈ 3.2 rem, Heading 3 ≈ 1.5 rem,
Paragraph 1.06 rem, line height 1.6. Turn heading letter-spacing to `-0.02em`.

## Step 4: Buttons and spacing

* Design → Buttons: Primary = solid, corner radius **6 px**, padding medium, no shadow.
* Design → Spacing: section padding *large* on desktop, *medium* on mobile. Site width *wide* (max ≈ 1180 px is set in CSS).

## Step 5: Paste the Custom CSS

Design → **Custom CSS** → paste the full contents of `custom-css.css`. Save.

## Step 6: Code Injection (Core plan or higher)

Settings → Advanced → **Code Injection**.

* **Header**: paste `code-injection/header.html` (loads the Google Fonts and sets the theme colour for mobile browsers).
* **Footer**: paste `code-injection/footer.html` (animates the bars in the org-health card; makes external links open in new tabs).

If you are not on Core or higher, skip this step. Fonts still load through the `@import` at the top of the Custom CSS.

## Step 7: Build the header

Edit → Header.

1. Site title: **ANDURIL** (all caps; letter-spacing is handled in CSS). Optional: upload `preview` mark as a logo later.
2. Navigation links come from the pages you create in Step 8. Order: Services, How we work, Clouds, About, Contact.
3. Header → **Elements** → turn on **Button**. Text: *Book a free org review*. Link: the Contact page. Style: Primary.
4. Header → Style: *Solid* background, fixed position **on**, "Blur" off (CSS adds a subtle blur).
5. Mobile menu: keep the default hamburger. The CSS styles it.

## Step 8: Create the pages

Follow `02-SITE-MAP.md` page by page. The general recipe for every section is:

1. Pages → **+** → Blank Page → name it.
2. **Add section** → choose the section type listed in the site map.
3. Drop in the blocks listed (Text, Button, Form, Code, Image).
4. Paste the copy from `copy/<page>.md`. Headings use *Heading 2*; labels marked *Eyebrow* in the copy use
   *Monospace* style (Text block → "…" → Monospace) so the CSS picks them up as ember labels.
5. For **Code Blocks**: Add block → **Code** → set *Type* to **HTML**, untick *Display source*, paste the file from `code-blocks/`.
6. Section → **Edit section** → set the theme (Lightest 1 or Darkest 1) and section padding.

Set the **Home** page as the site's homepage (Pages → hover Home → gear → *Set as homepage*).

## Step 9: The contact form

On the Contact page, add a **Form Block** with these fields (all marked required except the last two):

| Field | Type |
|---|---|
| Your name | Name |
| Company | Text |
| Work email | Email |
| Which Salesforce products do you use? | Select: Sales Cloud / Service Cloud / Sales + Service Cloud / Marketing Cloud / Several clouds / Not on Salesforce yet |
| What is not working today? | Text area |

Form → Storage: **Email** to your address. Submit button text: *Request the review*.
Post-submit message: *Thanks. A consultant, not a sequence, will reply within one business day.*

**Sending leads straight into Salesforce:** Form → Storage → **Zapier** (or use Make). Create a Zap: trigger
"Squarespace: New Form Submission" → action "Salesforce: Create Lead". Map Company, Name, Email, and put the
select answer into a custom Lead field such as `Current_Products__c`.

## Step 10: Footer

Edit → Footer → Add section (Darkest 1 theme). Three columns:

* Column 1: **ANDURIL** as Heading 3, then the one-line description from `copy/home.md` (Footer section).
* Column 2: "Site" (monospace label) + links to each page.
* Column 3: "Elsewhere" + LinkedIn, Trailblazer profile, Privacy policy.

Below, a small text block with the copyright line and the Salesforce trademark disclaimer (in `copy/home.md`).
Keep the disclaimer: it protects you from trademark issues and is standard for independent consultancies.

## Step 11: SEO and launch checklist

* Settings → SEO → Site title format: `%p | Anduril · Salesforce consultancy`. Description: use the meta description in `copy/home.md`.
* Every page: Page settings → SEO → paste the page's meta description from its copy file.
* Upload a favicon: export the ember mark from `preview/index.html` (the SVG in the header) at 512×512 or use any square version of your logo.
* Settings → Marketing → Social sharing image: a 1200×630 image with "Salesforce, reforged." on the steel background.
* Replace every placeholder in the copy: `hello@your-domain.com`, the two client quotes, the results figures.
* Test on a phone: menu opens, form submits, the code-block grids stack to one column.
* Settings → Site availability → **Public**.

## Things you may want to change

* **Name check.** "Anduril" is also the name of a large US defence company (Anduril Industries). That does
  not stop you using it for a Salesforce consultancy, but check trademark registrations in your country and
  make sure the domain and LinkedIn name you pick are clearly yours.
* **"Salesforce Partner" wording.** The copy says *independent Salesforce consultancy*. Only say *Salesforce
  Consulting Partner* if you are registered in the Salesforce Partner Program.
* **Results numbers** on the home page are illustrative. Replace them with your own before going public.
