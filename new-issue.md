# Making the next issue from this file

`subculture-zine-v4.html` is Issue 01 (October 2026), ported flat from
`newsletters/Subculture Zine Newsletter v4.dc.html`. It is one self-contained HTML file plus
the `assets/` folder beside it. No framework, no build step.

This is **not a template**. The system is fixed — paper, type, palette, components, rules.
The composition is rolled fresh every issue. Do not turn the roll into a default.

---

## 0. Set up

    cp subculture-zine-v4.html subculture-zine-<issue>.html

Keep `assets/` beside it. Open it in a browser to work. If you want a local server:

    python3 -m http.server 8731

then go to `http://localhost:8731/`. Opening the file directly also works; a preview pane
that inlines the page as a `data:` URL will break the relative `assets/` paths — that is the
harness, not the file.

## 1. Gather and fact-check first

Per `PLAYBOOK.md` §0. One folder per venue: photos, logo scraps, verbatim copy, deal terms
with the name of whoever approved them. Write a `FACT-CHECK.md` with three lists: confirmed,
open slots, invented. Everything in lists 2 and 3 ships as a visible dashed slot or carries a
"Draft terms — X to confirm before send." line. Never fill a slot yourself.

New logo scraps arrive with a checkerboard baked into the pixels — run
`scripts/checker-cut.js` before use (recipe in `COMPONENTS.md` → "Checker cut").

## 2. Roll the variation — write the roll down

Actually roll it. Dice, RNG, anything. Record the result in the issue's notes.

| Roll | Options |
|---|---|
| Hero paper | cream-2 sheet · manila sheet · straight on the board |
| Hero hardware | one tape top-centre-ish · tape at two opposite corners · one thumbtack |
| Red band position | after hero · after first mid section · before the Sampler |
| Which mid sections go dark | 1 of them · 2 of them (never adjacent) |
| Featured deal treatment | red dashed coupon · manila price tag · dark card with manila tag |
| Lore card hardware | tape top-left · tape top-right · thumbtack |
| Ticket stock | cream-2 · manila |
| Global tilt sign | first section tilts negative · first section tilts positive |

Then: alternate tilt signs down the page (−, +, −, +), magnitudes 0.5°–3.8°, no two adjacent
sections within 0.4°. Tape strips 48–84px wide, angles drawn from
`{−58, −38, −36, −34, −31, −24, −23, −21, −19, −17, −16, −14, −12, −11, −9, −7, −4, −3, 19,
23, 24, 27, 28, 36, 39, 41, 47, 52, 78}` — never the same angle twice on one screen.

**Issue 01 used:** header −1.1° / tape −58° · hero +0.6° / tape −3° · Hacienda red band −0.7°
· Man Ray dark +0.8° · El Segundo −1.2° · calendar dark −0.6° · Howley's on the board ·
Sampler −0.9° (two tapes, −11° and +52°) · Valt File −2.4° · Book the room −0.6° ·
membership −2.6° / tape −21°. Roll something different.

## 3. Swap the content, section by section

The spine never changes: **header · hero · one red band · 2–4 mid sections · Sampler ·
Valt File · Book the room · membership · directory.** Drop or add mid sections freely.

Per section: swap copy and images → apply the roll (paper, tilt, hardware, deal treatment) →
check against `RULES.md`. The featured restaurant **always** carries a deal block, even if
the terms are a draft.

**Standing, do not touch:** the header strip. Same wordmark, same scribble, same cities line,
same hand-drawn SVG underline. Only the eyebrow ("The July newsletter") changes.

**File-specific notes for whoever edits this port:**
- Two `<canvas>` elements are drawn by the inline script at the bottom: `#scribble` (header,
  zigzag `linearPath`, roughness 1.4 / bowing 2.2) and `#sampler` (double rule, roughness 0.9
  / bowing 0.6). Keep those numbers — higher values fan strokes across the canvas.
- Link hover states are the `hv1`–`hv5` classes in the `<style>` block. Reuse them; don't
  add inline hover attributes.
- Torn edges and perforations are the `rip-b70` / `tk-hard` classes from `assets/masks.css`,
  and worn ink is `ink-worn` / `ink-worn-2` from `assets/ink.css`. Both are data-URL masks.
  If an edge goes square, the file is being served somewhere that blocks data URLs — say so,
  do not replace it with a drawn edge.

## 4. Review pass — walk it top to bottom

- **Whitespace.** Any column ending well short of its neighbour? Fill with a lore card, a menu
  card, a polaroid or an extra Sampler row. Never with padding.
- **Red count.** Exactly one red band. Coupons, stamps, eyebrows and prices in red are fine.
- **Tape.** Nothing uniform, nothing centred, nothing symmetric, no repeated angle. Every
  pinned thing has tape or a thumbtack — including lore cards, polaroids, menu cards, coupons.
- **Ink in the paper.** `mix-blend-mode: multiply` on type over paper; `ink-worn` +
  `blur(.25px) contrast(1.15)` on ticket and coupon type. Contrast ≥ 4.5:1.
- **Slots visible.** Every `[ ... ]` renders as a dashed box or dashed underline.
- **Wordmarks unbroken.** No venue name split across lines — shrink the type instead.
- **Alt text.** Every image keeps a real description.
- Screenshot the page and compare against the previous issue before calling it done.

## 5. Ship

Export to PDF or send the HTML. Fill the dashed slots first, or send them as visible slots on
purpose — a bracketed slot is on-brand, an invented fact is not.

## Never

Modernise or flatten the layout. Replace a scan with a gradient, filter or SVG texture. Draw
a torn edge. Invent a URL. Rewrite supplied copy or its spellings ("The Valt File #107"). Add
sections, stats, icons or emoji.
