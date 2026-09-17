# Subculture Zine Newsletter — Issue 01

A punk-zine style HTML email newsletter for Subculture Group
(West Palm Beach · Lake Worth Beach · Delray).

**[View the newsletter →](https://tstrycharz-ui.github.io/subculture-zine-newsletter/)**

## ⚠️ Draft — not for distribution

This issue is a work in progress. Several items are **unconfirmed or invented placeholders**
and must not be treated as real offers:

- The **$22** Simmer Down oxtail deal — invented, pending confirmation
- The **$18** El Segundo Taco Tuesday deal — invented, pending confirmation
- The **$12** Howley's midweek deal — invented, pending confirmation
- Man Ray opening date, Hacienda hours and opening date, Howley's hours — open slots
- Several Sampler dishes and two calendar shows — open slots

Every one of these renders on the page as a visible dashed `[ ... ]` slot or carries a
"Draft terms — X to confirm before send." line. That is by design: the zine reads as
in-progress on purpose. A bracketed slot is on-brand; an invented fact presented as
confirmed is not.

## What's here

```
index.html                 the newsletter — one self-contained file
assets/                    the scans and photos it references
subculture-zine-v4.pdf     a single-page render, for review
new-issue.md               checklist for producing the next issue
```

## How it works

No framework, no build step. A fixed 660px cream paper card on a dark desk; the desk
scrolls horizontally rather than the composition reflowing, because this is an email and
behaves like a printed sheet.

Nothing is drawn. Every texture is a scan of real paper, real masking tape, a real
photocopy or a real tear. Type sits *in* the paper via `mix-blend-mode: multiply` and
ink-dropout masks, not on top of it. Everything is pinned a few degrees off-axis and every
pinned thing has hardware — tape or a thumbtack. One red band per issue.

Torn edges and ticket perforations come from `assets/masks.css`; worn ink comes from
`assets/ink.css`. Both are embedded as data URLs, because `mask-image: url()` fetches are
CORS-gated in some hosts and fail silently. Fonts load from Google Fonts and rough.js loads
from a CDN for the header scribble and the Sampler rule.

## Running it locally

Open `index.html` in a browser, keeping `assets/` beside it. Or serve it:

    python3 -m http.server 8731

then visit `http://localhost:8731/`.

If the paper and tape do not appear and you only see text, the page is being loaded in a
way that rewrites it as a `data:` URL, which severs the relative `assets/` paths. Serve it
over HTTP instead.

## Making the next issue

See `new-issue.md`. The system is fixed — paper, type, palette, components, rules. The
composition is rolled fresh each issue. It is deliberately not a rigid template.
