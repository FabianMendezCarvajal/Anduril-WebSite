# Design references (Awwwards research)

**What could and could not be scraped.** This environment's network policy blocks awwwards.com and the winning
sites themselves, so the pages were not fetched directly. The findings below come from web-search excerpts
of Awwwards listings, juror write-ups and trend round-ups, plus the patterns that recur across Site of the Day
winners. If you want a direct scrape, add `awwwards.com` to the environment's allowed domains and ask again.

## Sites surfaced by the research

| Site | Award | What is worth stealing |
|---|---|---|
| Heco Partners (helloheco.com), a creative consultancy | SOTD (7.03) and Honorable Mention 2026 | Two-colour palette, `#282828` on `#F9F7F7`. Motion in header, nav, cursor and footer. Categories: Business & Corporate, Unusual Navigation, Microinteractions. The closest peer to a consultancy site. |
| Unseen Studio (unseen.co) | SOTD, Design Studio of the Year | "Refined, type-led motion design with impeccable pacing". Typography is the hero; motion is choreographed, not scattered. |
| Pensatori Irrazionali, Boc.Studio, Noho, LxL Creative | SOTD, 17 to 20 Sept 2026 | The current run of agency winners: oversized grotesk headlines, dark or near-white grounds, one accent. |
| Carles Faus Arquitectura | SOTD 2026 | "Spatial silence": generous whitespace, one element per screen. |
| American Bitcoin Corp | Nominee, finance 2026 | Dark palette, high contrast, striking type. Proof that dark + big type reads as premium in B2B. |
| Mat Voyce portfolio | SOTD + GSAP Site of the Year | Kinetic type as the whole idea. |

## Patterns the winners share (and how Anduril applies them)

1. **Typography is the hero.** Oversized headline filling the viewport width, a grotesk paired with a serif
   italic (the pairing the Awwwards typography collection returns to most often). → "Salesforce," in Bricolage
   Grotesque 600, "reforged." in Instrument Serif italic, up to 196 px.
2. **Two colours and one accent.** Near-black or off-white ground, one accent, nothing else. → Forge
   black `#0B0D11`, paper `#F1EFEA` sheets, copper `#E0663A` kept for italics, marks and hover sweeps.
3. **Line-mask reveals and staggered entrances,** not scattered effects. → Headline lines slide up from a
   mask on load; sections fade up once, then stay.
4. **Meta line in the header:** local time, location, availability. → "07:16 PM local · Taking projects Q4 2026".
5. **Full-screen overlay menu** with enormous links. → Paper overlay, five links at 104 px with serif italic index numbers.
6. **The hover list.** Services as huge rows that invert on hover and expand on click. → Six rows, black
   fill sweeps in, ember plus-button.
7. **Marquee ticker** between hero and body. → Clouds and tools scroll as a marquee.
8. **Sticky card stack** for a sequence. → Five process stages stack under a fixed header offset.
9. **Numbers that count up** and proof cards with a hover glow. → Results section.
10. **Custom cursor** that grows over links, using `mix-blend-mode: difference`. → Thin ring with a centre dot.
11. **Film grain** overlay at 5 percent. → Present site-wide.
12. **Giant wordmark footer.** → "ANDURIL" at up to 280 px, fading into the ground.
13. **Sections as sheets.** Light sections with rounded top corners laid over the dark ground, a device that
    reads as physical paper. → Services, Review and About sit on one paper sheet.
14. **The jury's test:** "take away the animation and the static frames still look like someone made them on
    purpose." → Every section was checked as a still frame at desktop and phone width before publishing.

## The identity: Proposal B, the West

The site applies **Proposal B** from the Anduril Visual Identity canvas (boards B, B1, B3, B4, B5): a
map-maker's identity. A consultancy that inherits a Salesforce org inherits territory nobody has charted; it
surveys before it touches. The identity is that survey: paper, ink, contour lines, coordinates.

| Element | The system | On the site |
|---|---|---|
| The mark | An eight-point compass rose; the west point longer and lit in Gilt, the only accent the mark carries | Beside the wordmark in the header, ringed on the About sheet, in ivory above the footer wordmark |
| The wordmark | "Anduril" written rather than set: Fraunces italic 500, SOFT 50, WONK on, optical size 144 | Live type in the header and the giant footer wordmark |
| Colour | Ivory `#F4EFE4` ground · Pine `#143D31` ink and dark ground · Gilt `#C9A14B` the flame · Moss `#3F6D58` · Vellum `#E9E2D0` · Rule `#D3CAB4`. Proportion 78 / 18 / 4 | Ivory pages, vellum alternate sections, one pine ground for Coordinates and the footer. Gilt Deep `#7A5D18` carries italic phrases on ivory because Gilt itself fails as text |
| Type | Fraunces 500 opsz 144 SOFT 30 for display, italic 400 for the turn of phrase · Instrument Sans for reading · DM Mono for coordinates | Every heading, every label, every paragraph |
| The celestial sheet | A map-maker's instrument: the sky charted for a place and a moment | A working planisphere in the hero, drawn in the manner of the nineteenth-century star atlases (Peck's Edinburgh charts): a night disc with stars scaled by magnitude and rayed when bright, the Milky Way stippled in, the hour and declination grid, constellation names in spaced capitals, the ecliptic and zodiac, Sun and Moon, inside a calendar ring that marks today, rising from the bottom edge of the hero with its top half in view, facing south so the ecliptic is in view, and turned by the hour with two buttons |
| Contours | The org as terrain, behind headers and on card backs | On the field-note cards on hover |
| Margins | Every sheet gets a frame, ticks and coordinates | A fixed frame around the viewport with survey ticks and "Sheet 01" |
| Legend | Services and findings as map symbols | Symbols on the terrain rows, the routes and the survey sheet |
| The seven stars and the scale bar | A dotted route; a timeline scale | The route under the hero headline; the 0 to 90 days scale over the stages |
| Language | "Know the org before you change it." "Salesforce, mapped." Survey, chart, route, field notes, coordinates | The headline, the tagline, the navigation and every chapter label |

Day and night: the site carries a night palette, the pine set reversed, switched by a sun and a moon in the
header and remembered per device; the chart's disc stays night in both.

Sheets replace chapters: 01 the hero, 02 Terrain, 03 Routes, 04 The survey, 05 Field notes, 06 Charted, 07 The
free survey, 08 The map-maker, 09 Coordinates.

What was left out on purpose: the sword, elvish scripts, the seven-stars-between-moon-and-sun engraving and
anything that reads as fan art. The name and its meaning come from Tolkien; the rose, the palette and the type
do not. The footer notes the name's origin and that the site is not affiliated with the Tolkien Estate or
Middle-earth Enterprises.

## What was deliberately not copied

* 3D scroll-driven camera work. It scores well on Awwwards but costs performance, accessibility and Squarespace
  compatibility, and a consultancy buyer is not there for it.
* Horizontal scroll sections pinned with GSAP ScrollTrigger. Same reason. The sticky stack gives the same
  "one stage at a time" pacing in pure CSS.

## Sources

- https://www.awwwards.com/sites/heco-partners and https://www.awwwards.com/sites/heco-partners-1
- https://www.awwwards.com/sites/unseen-studio-2025-wrapped
- https://www.awwwards.com/websites/sites_of_the_day/
- https://www.awwwards.com/websites/typography/
- https://www.awwwards.com/websites/business-corporate/
- https://www.hontran.dev/blog/best-award-winning-websites-2026
- https://digitalstrategyforce.com/journal/why-are-immersive-experiences-dominating-the-2026-awwwards/
- https://www.figma.com/resource-library/web-design-trends/
- https://reallygooddesigns.com/web-design-trends-2026/
