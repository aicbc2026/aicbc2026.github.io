# AICBC 2026 — Architecture of Life

Website for the **49th All India Cell Biology Conference & Symposium**
9–11 December 2026 · IISER Pune · co-hosted with NCCS Pune

Live at **https://aicbc2026.github.io**

## Files

```
index.html              the entire site — one page, no build step
img/                    all photographs and logos (WebP)
  hero-condensate.webp    masthead artwork
  iiser-campus.webp       IISER Pune main building
  poster-art.webp         background for the two poster cards
  logo-iscb.webp          Indian Society of Cell Biology
  logo-iiser.webp         IISER Pune
  logo-nccs.webp          NCCS Pune
share-card.jpg          1200x630 preview for WhatsApp / X / LinkedIn
favicon-32.png          browser tab icon
icon-512.png            high-resolution app icon
apple-touch-icon.png    iOS home-screen icon
```

**Keep `img/` next to `index.html`.** If the folder moves, every picture breaks.

## Making changes

Edit `index.html` on GitHub (pencil icon), commit, and the live site updates in
about a minute. Hard-refresh with Cmd+Shift+R if you still see the old version.

To swap a photograph, upload a replacement into `img/` **using the same
filename**. No HTML edit is needed.

## Still to do

Search `index.html` for `TODO(` — there is a numbered checklist at the top of
the file. Outstanding at the time of writing:

- Phone number is a placeholder (`+91-20-2590-XXXX`)
- Three organiser entries say TBA
- Fee table is marked "indicative placeholders"
- QR code is a placeholder until the abstract book has a URL
- Program & Abstract Book card has no target yet
- X / Instagram icons are commented out until accounts exist
- No accommodation section or abstract-submission guidelines yet

## Notes

- The masthead overlay is a Gray–Scott reaction–diffusion simulation, confined
  to the condensate by a mask derived from the artwork itself. It pauses when
  off-screen and respects `prefers-reduced-motion`.
- "Download Poster" generates an A3 PNG in the browser from the artwork and the
  three logos. Nothing is fetched over the network.
- Both features read pixel data from the images, so they need the page served
  over http(s). Opening `index.html` directly from disk (`file://`) disables
  them — the page still works, but the overlay covers the whole banner and the
  poster button reports "Poster unavailable". This is expected, and it works
  correctly on the live site.
