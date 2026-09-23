# Anduril · visual identity (v1)

Brand assets and rules for **Anduril**, an independent Salesforce consultancy named after the sword in Tolkien's
Middle-earth that was reforged from the shards of one that broke. The identity extends the website's art
direction (see the site kit) into a logo, a palette, a type system and application rules.

```
brand/
  README.md          this file: the guidelines
  colors.json        palette with hex, RGB, CMYK, usage notes and measured contrast ratios
  tokens.css         CSS custom properties for every colour and typeface
  logo/
    mark/            the mark alone (on dark, on light, mono, and a small-size cut)
    wordmark/        ANDURIL as outlined paths (no font needed)
    lockup/          horizontal, stacked, signature (tagline) and descriptor lockups
    device/          the engraving: crescent, seven stars, rayed sun
    icon/            app icon 1024, favicon 32 (opaque and transparent)
    social/          square avatars, safe for circular crops
  png/               raster exports: icons, avatars, marks at 1000, lockups at 2x
```

Every SVG is self-contained: type is converted to outlines, so nothing depends on fonts being installed.

## 1. The idea

The name promises one thing: what broke can be made whole, and stronger than before. That is also the job,
because most Salesforce orgs a consultancy inherits are broken in some way. The identity says it with three
materials and no imagery:

* **Steel**: the mark, the type and the hairlines. Paper on dark, Forge Black on light.
* **The flame**: one copper accent, called Ember, used once per surface where it matters most.
* **The forge**: a near-black ground with a faint grain, and paper sheets laid over it.

No swords, no elvish script, no film references. The Middle-earth material appears only as the engraving on
the blade (crescent, seven stars, rayed sun) and in the name's meaning, "Flame of the West".

## 2. The mark: the seam

The mark is the letter A drawn as the point of a blade. It is cut in three pieces: the point, the crossbar and
the two legs, separated by hairline gaps. **The crossbar is the seam where the shards were joined.** In colour
it is Ember, the flame still in the steel. In one colour, the gaps alone show the seam.

Why not the four-pointed star from the website? The star stays inside the engraving, but as a standalone mark it
now reads as the universal "AI feature" sparkle. The seam is ownable, reads at 16 px, and carries the concept
by itself.

Geometry (100-unit box): apex at (50, 4), base from x 14 to 86 at y 96. Gaps 2 units at y 44 and 54; crossbar
from y 46 to 54; leg inner edges parallel to the outer edges. The small cut (`*-small-*`) widens the gaps to 3.5
and the crossbar to 10 units so the seam survives at 16 to 48 px.

### Versions

| File | Steel | Seam | Use |
|---|---|---|---|
| `mark/anduril-mark-on-dark.svg` | Steel `#EDEBE6` | Ember `#E0663A` | Any ground darker than Slate |
| `mark/anduril-mark-on-light.svg` | Forge Black `#0B0D11` | Ember Deep `#C9552C` | Paper, white, light photography |
| `mark/anduril-mark-mono-white.svg` | Steel | gaps only | Engraving, embroidery, one-colour print, `difference` headers |
| `mark/anduril-mark-mono-black.svg` | Forge Black | gaps only | Same, on light |
| `mark/anduril-mark-small-*.svg` | as above | as above | 16 to 48 px: favicons, tab icons, list bullets |

### Clear space and minimum size

* Clear space on every side is **the height of the crossbar band plus its gaps**, which is the same as one quarter of
  the mark's height. Nothing else, no text, no other logo, no edge, enters that zone.
* Minimum height: 24 px on screen, 6 mm in print for the standard cut; 16 px for the small cut.

## 3. The wordmark and the lockups

**ANDURIL**, set in Bricolage Grotesque SemiBold at optical size 96, letter-spacing -0.03 em, capitals only,
no accent on the U. The accented form Andúril appears only in running text about the name.

| Lockup | File | When |
|---|---|---|
| Horizontal | `lockup/anduril-horizontal-*.svg` | The default. Headers, documents, signatures, decks. |
| Stacked | `lockup/anduril-stacked-*.svg` | Square and portrait spaces: social cards, badges, the back of a business card. |
| Signature | `lockup/anduril-signature-*.svg` | With the tagline *Salesforce, reforged.* in Instrument Serif italic. Covers, proposals, the end of a deck. |
| Descriptor | `lockup/anduril-descriptor-*.svg` | With SALESFORCE CONSULTANCY in IBM Plex Mono. Where the audience does not know what Anduril does: event badges, directories, sponsor walls. |
| Wordmark alone | `wordmark/anduril-wordmark-*.svg` | Giant footer, merchandise, anywhere the mark is already present. |

Construction of the horizontal lockup: the mark is 1.28 cap heights tall, centred on the cap height; the gap
between mark and wordmark is 0.42 cap heights. Clear space around any lockup is one cap height of the wordmark.

Minimum width of the horizontal lockup: 120 px on screen, 30 mm in print. Below that, use the mark alone.

## 4. Colour

Ratios: Forge Black or Paper covers about 90 percent of any surface; steel greys and hairlines about 7; Ember
about 3. Ember is a signal, not a theme: one accent per screen, on the thing that matters most. Brass appears
only as the light that catches a hairline; it is never a fill and never text.

| Name | Hex | RGB | CMYK (approx.) | Use |
|---|---|---|---|---|
| Forge Black | `#0B0D11` | 11 13 17 | 35 24 0 93 | Primary ground; the mark on light |
| Paper | `#F1EFEA` | 241 239 234 | 0 1 3 5 | Light ground; print stock |
| Ember | `#E0663A` | 224 102 58 | 0 54 74 12 | The seam, italics, hover, one accent per screen (on dark) |
| Ember Deep | `#C9552C` | 201 85 44 | 0 58 78 21 | Ember on Paper |
| Brass | `#D9A45B` | 217 164 91 | 0 24 58 15 | Glints only |
| Steel | `#EDEBE6` | 237 235 230 | 0 1 3 7 | Text and mark on dark |
| Steel 2 | `#B4B6BC` | 180 182 188 | 4 3 0 26 | Secondary text on dark |
| Slate | `#767C88` | 118 124 136 | 13 9 0 47 | Labels on dark; large text only |
| Surface | `#141821` | 20 24 33 | 39 27 0 87 | Cards on Forge Black |
| Hairline | `#1F232B` | 31 35 43 | 28 19 0 83 | Rules on dark |
| Paper 2 | `#E6E3DD` | 230 227 221 | 0 1 4 10 | Panels on Paper |
| Graphite | `#454A55` | 69 74 85 | 19 13 0 67 | Secondary text on Paper |
| Paper Slate | `#7A7F8A` | 122 127 138 | 12 8 0 46 | Labels on Paper; large text only |
| Paper Line | `#D3D0C9` | 211 208 201 | 0 1 5 17 | Rules on Paper |

Print: specify Forge Black as a rich black (the CMYK above, never 100 K alone) and Ember as a spot colour if the
job allows; the closest coated references should be matched on press from the hex, not from this table.

### Contrast (WCAG 2.x)

| Pair | Ratio | Passes |
|---|---|---|
| Steel on Forge Black | 16.3 : 1 | AAA |
| Steel 2 on Forge Black | 9.6 : 1 | AAA |
| Slate on Forge Black | 4.6 : 1 | AA (normal text), use for labels only |
| Ember on Forge Black | 5.7 : 1 | AA |
| Forge Black on Paper | 16.9 : 1 | AAA |
| Graphite on Paper | 7.7 : 1 | AAA |
| Paper Slate on Paper | 3.5 : 1 | AA large text only |
| Ember Deep on Paper | 3.8 : 1 | AA large text only: use for headlines and marks, not body |
| Ember on Paper | 3.0 : 1 | Fails for text: never set text in Ember on Paper, use Ember Deep |
| Forge Black on Ember | 5.7 : 1 | AA: buttons with dark text on an Ember fill work, white text on Ember does not (2.9 : 1) |

## 5. Typography

Four faces, each with one job. All are open licence and on Google Fonts.

| Role | Face | Setting |
|---|---|---|
| Display | **Bricolage Grotesque** 500 to 600, optical size 96 | Headlines and the wordmark. Tight: -0.035 em to -0.045 em, line height 0.9 to 0.98. |
| Counterpoint | **Instrument Serif** italic | One word or phrase inside a headline, in Ember on dark or Ember Deep on light. The voice of the name. Never a whole headline, never body text. |
| Text | **IBM Plex Sans** 400 and 500 | Body, ledes, UI. 16 to 20 px, line height 1.5 to 1.6, measure 46 to 60 characters. |
| Labels | **IBM Plex Mono** 400 and 500 | Eyebrows, meta lines, buttons, captions: 11 to 12 px, uppercase, tracking +0.12 to +0.16 em. |

The pairing rule: the grotesk states, the serif italic turns. *Salesforce,* in Bricolage; *reforged.* in Instrument
Serif italic. Use the turn once per page.

Scale (desktop): display 96 to 196 px, H2 48 to 72, H3 26 to 32, lede 20, body 17, label 11. Mobile divides the
display sizes by roughly 2.5 and keeps everything else.

## 6. The device

The engraving on the blade: crescent, seven four-pointed stars, rayed sun, drawn as a 300 by 24 unit line in
`logo/device/`. It is a decoration, never a logo. Use it in Slate on dark or Paper Slate on light, at 150 to 260
px wide, in these places only: under a headline on a hairline, above the footer wordmark, as a section divider on
a paper sheet, and on the back of the business card. Never colour it Ember, never scale it above 300 px, never
use a single star from it as a standalone icon.

## 7. Texture and imagery

* Film grain at 4 to 5 percent over dark grounds, never over Paper.
* Paper sections have 32 px rounded top corners and sit over the dark ground like a sheet.
* No stock photography. If a photograph is unavoidable, it is monochrome, warm-toned, and sits on Paper.
* Diagrams and product screenshots are framed in Surface with a Hairline border and 16 to 20 px radius.

## 8. Voice, in one line

Direct, calm, specific. Short sentences. Numbers where they exist. The name's story is told once, in the About
page's name entry, and then left alone.

## 9. Don't

* Don't recolour the mark; the only accent inside it is the seam.
* Don't outline it, add a gradient, a glow or a drop shadow, or put it in a circle or a shield.
* Don't rotate it or use it as a letter inside other words.
* Don't set the wordmark in another face, add the accent to the U, or use mixed case.
* Don't place the mark on Ember or Brass fills, or on photography without a Forge Black or Paper field.
* Don't use Ember for more than one element per screen, or for body text on Paper.
* Don't pair the serif italic with anything but Bricolage, or use it for more than a phrase.
* Don't draw swords, rings, maps, runes or any Middle-earth imagery.

## 10. Legal note

Andúril is a name from Tolkien's works; Middle-earth names are registered trademarks in several classes.
Before printing at scale or filing a mark, check the name in your jurisdiction, and keep the site's footer
line stating that Anduril is not affiliated with the Tolkien Estate or Middle-earth Enterprises.
