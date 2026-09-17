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
- Hacienda hours and opening date, Man Ray opening date, Howley's hours — open slots
- Sampler dishes for Shanghai'd, Chhauka and Kill Your Idol — open slots
- Two further calendar shows, the partner business card, the RHCP photo credit — open slots

Each of these renders on the page as a visible dashed `[ ... ]` slot or carries a
"Draft terms — X to confirm before send." line. That is deliberate: the zine reads as
in-progress by design. A bracketed slot is on-brand; an invented fact presented as
confirmed is not.

Menu prices shown (Dada 19, Hullabaloo 18, Howley's 19.95, Man Ray 34/10) are transcribed
from menu scans that carry no date. They are *sourced*, not confirmed current.

## Image credits

- The Hacienda storefront photo is a **Google Street View** capture, credited in-page.
- The Red Hot Chili Peppers band portrait's rights are unresolved; its credit is an open slot.
- Venue photography, food photography, logo scraps, flyers and the 1989 handbill are the
  client's own or venue ephemera.

## What's here

```
index.html   the newsletter — one self-contained file
assets/      the scans and photos it references
new-issue.md checklist for producing the next issue
```

## How it works

No framework, no build step. A fixed 660px cream paper card on a dark desk; the desk scrolls
horizontally rather than the composition reflowing, because this is an email and behaves like
a printed sheet.

Nothing is drawn. Every texture is a scan of real paper, real masking tape, a real photocopy
or a real tear. Type sits *in* the paper via `mix-blend-mode: multiply` and ink-dropout masks,
not on top of it. Everything is pinned a few degrees off-axis and every pinned thing has
hardware. One red band per issue.

Torn edges and ticket perforations come from `assets/masks.css`; worn ink from
`assets/ink.css`. Both are embedded as data URLs, because `mask-image: url()` fetches are
CORS-gated in some hosts and fail silently. Fonts load from Google Fonts and rough.js from a
CDN for the cover rule.

## Running it locally

    python3 -m http.server 8731

then visit `http://localhost:8731/`.

If the paper and tape do not appear and you only see text, the page is being loaded in a way
that rewrites it as a `data:` URL, which severs the relative `assets/` paths. Serve it over
HTTP instead.
