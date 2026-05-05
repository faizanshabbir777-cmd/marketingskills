# IKSIR — Logo Concepts (Global Brand Direction)

Direction-setting brand exploration for IKSIR, a heritage-Islamic supplement brand (creatine + collagen) for women in their 30s. This folder contains a critique of the existing logo system and six concept directions designed to take the mark from premium-niche to globally legible.

## What's here

```
brand-projects/iksir/
├── README.md         # this file
├── CRITIQUE.md       # what's working / what's blocking it from being global
├── showcase.html     # interactive preview — open in any browser
└── concepts/
    ├── 01-crescent-counter.svg          # wordmark
    ├── 01-crescent-counter-mark.svg     # standalone mark
    ├── 02-iksir-seal.svg                # bilingual lockup
    ├── 02-iksir-seal-mark.svg
    ├── 03-globe-crescent.svg
    ├── 03-globe-crescent-mark.svg
    ├── 04-drop-crescent.svg
    ├── 04-drop-crescent-mark.svg
    ├── 05-star-of-iksir.svg
    ├── 05-star-of-iksir-mark.svg
    ├── 06-refined-original.svg          # polish path, preserves existing equity
    └── 06-refined-original-mark.svg
```

## How to view

Open `showcase.html` in any modern browser:

```bash
# from the repo root
open brand-projects/iksir/showcase.html        # macOS
xdg-open brand-projects/iksir/showcase.html    # Linux
start brand-projects/iksir/showcase.html       # Windows
```

The showcase has three palette toggles (Heritage Gold, Sand &amp; Ink, Olive &amp; Saffron) and two mono fallbacks — every concept is rendered in all five so you can judge palette fit and mono survival side-by-side. Each concept also has a favicon strip (16, 32, 48, 64, 128px), an app-icon row, and an avatar test for circular crops.

> The browser fetches the SVGs over `file://`. If you see empty cards, you may need to serve the folder over HTTP. The simplest way:
>
> ```bash
> python3 -m http.server 8000 --directory brand-projects/iksir
> # then open http://localhost:8000/showcase.html
> ```

## The six concepts at a glance

| # | Name | Lever | Best for |
|---|------|-------|----------|
| 01 | Crescent-Counter | Mark-first identity | Apps, avatars, favicon-first markets |
| 02 | Iksir Seal | Bilingual badge | MENA launch, premium SKUs, packaging closures |
| 03 | Globe-Crescent | Literal "global" cue | Mission-led campaigns, sustainability story |
| 04 | Drop &amp; Crescent | Wellness-forward heritage | Mass-retail wellness aisles, US/UK launch |
| 05 | Star of Iksir | Geometric ornament heritage | Heritage editions, gifting, Ramadan campaigns |
| 06 | Refined Original | Polish, not redesign | Preserves equity if the current wordmark is already in market |

Read `CRITIQUE.md` for the rationale behind why each lever matters.

## SVG conventions

All SVGs follow the same rules so they drop into any toolchain cleanly:

- `viewBox` only — no fixed `width` / `height` (responsive)
- `currentColor` for primary fills — re-skin the whole mark by setting CSS `color`
- Self-contained — no `<image>` references, no external scripts
- Latin wordmarks fall back through Google-Fonts → system serif/sans, so the SVGs render acceptably even without internet
- Arabic glyphs (concept 02) fall back through Amiri → Noto Naskh Arabic → system serif

## What's intentionally not included

- **PNG / JPG exports.** Modern browsers and design tools render SVG natively at any resolution; export from there if needed. If we settle on a direction, the next pass adds an export pipeline (`scripts/svg_to_png.py` + size matrix).
- **Photographic showcase backgrounds.** A future iteration can run the chosen mark through a Nano-Banana-style background generator for pitch decks; left out here to keep the showcase fast and self-contained.
- **Trademark clearance.** Particularly important for concept 05 (8-point star) before any commercial use.
- **Final font licensing.** Concepts use Google-Fonts-licensed families (Cormorant Garamond, Inter, Plus Jakarta Sans, Playfair Display, Amiri, Noto Naskh Arabic) — production may want a paid pairing for distinctiveness.

## Next steps

1. Pick 1–2 directions from the showcase.
2. Reply with which concept(s) and what tweaks (single tweaks run sequentially, batch variations run in parallel — same convention as the upstream logo-creator skill).
3. Once a direction is locked, the next pass produces: full lockup system (master, product, mission, packaging, app, Amazon-compact, mono), bilingual lockup variants, and an export pipeline.
