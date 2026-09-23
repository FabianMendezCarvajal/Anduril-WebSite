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
