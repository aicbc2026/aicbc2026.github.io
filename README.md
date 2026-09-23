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
  ws-confocal.webp        workshop figure - simulated field, confocal
  ws-sim.webp             the same field, Lattice SIM
  ws-sted.webp            the same field, STED
  ws-bleach-sim.webp      time-lapse bleaching series, Lattice SIM
  ws-bleach-sted.webp     the same series, STED
  ws-bleach-curve.webp    signal-remaining curves for both
workshop-poster.pdf     A3 poster for the superresolution workshop (print)
workshop-poster.png     the same poster at 300 dpi, for screens and slides
workshop-banner.jpg     1200x630 workshop banner for WhatsApp / X / LinkedIn
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

### Superresolution workshop (added Sep 2026)

Search `index.html` for `TODO(WS)`. The workshop section is live but three
things are still placeholders:

- `WORKSHOP_FORM_URL` at the end of the workshop section is empty. Paste the
  Google Form link between the quotes and commit — both Apply buttons switch
  from "Applications opening shortly" to a live link on their own. Nothing else
  needs changing.
- Figures marked with a small degree sign (class `prov`) are provisional:
  24 places, 31 Oct application deadline, 15 Nov decisions, and the fee. Confirm
  each with the organisers, correct it, then delete the `prov` class so the
  marker and its footnote disappear.
- The poster carries the same provisional figures. If any of them change,
  the poster has to be regenerated as well as the page edited.

The three-panel resolution figure (page and poster) is **simulated**, and says
so in its caption: ground truth drawn at 10 nm/px, convolved with a Gaussian PSF
at each modality's FWHM (~230 / ~115 / ~50 nm), then given shot noise. It is
there because there was no real data to hand. Swapping in genuine confocal,
Lattice SIM and STED frames of the same field from the two facilities would be
better in every way - replace the three `img/ws-*.webp` files and drop the
"Simulation, for illustration" line from the caption.

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
