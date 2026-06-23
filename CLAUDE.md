# CLAUDE.md - Vastu Gurukul website

Canonical context for Claude Code. Read this first before editing anything.

## What this is
A single-page **explanation landing page** for **Vastu Gurukul**, the Astro Vastu &
MahaVastu brand founded and led by Acharya Monica. Static site - no framework, no
build step. One self-contained file (`index.html`) with CSS and JS inline, plus one image.

**Status:** Page 1 (Home / explanation) is built. A pricing page (Page 2) is planned
but NOT built yet. Do not build it unless asked.

## Brand hierarchy and Monica facts (keep all copy grounded in these facts - do not invent)
- **Vastu Gurukul** is the company/main brand. Acharya Monica is the founder and
  main teacher/consultant behind it.
- Astro Vastu & MahaVastu Consultant + Numerologist. Based in Gurugram; serves Delhi
  NCR in person and India + abroad online.
- MBA, Delhi University. Trained as an Astro-MahaVastu Acharya at the **MahaVastu
  Gurukul** under its founder **Khushdeep Bansal**.
- ~A decade of practice across corporate offices, homes, and commercial spaces.
- **The "Why Vastu Gurukul" story:** over ~10 years Monica studied six disciplines -
  **Astrology, Numerology, Vedic Science, Vastu, Astro Vastu, Angel Card Reading** -
  and folded all of them into one **MahaVastu** practice.
- Positioning: reads a space *through the client's own birth chart*; MahaVastu
  remedies need **no demolition** (relocate / rectify, don't rebuild).
- Real testimonials currently used (from acharyamonica.com): Sheenu Gupta
  (PestCure), Ajeet Kumar, Soniya Rao. Don't fabricate new ones.

## Brand tokens (defined as CSS vars in `index.html` `:root`)
- Palette is **green + blue**. Green = energy / CTA / accent. Blue = depth / structure.
  - `--ink #FFFFFF`  `--ink-2 #F6FAF8`  `--ocean #EAF5FA`
  - `--emerald #0E8F6B`  `--mint #15A87B` (primary accent/CTA)  `--sky #2E92CC`
  - `--cream #0C2233` (text)  `--slate #5E7686` (muted)
- Type: **Fraunces** (display/serif) + **Inter** (body), loaded from Google Fonts.

## File structure
```
MONICA MAHAVASTU/
├─ index.html              # the whole site (HTML + CSS + JS inline)
├─ images/
│  └─ monica-hero.png      # real photo of Monica used in hero/about sections
├─ CLAUDE.md               # this file
└─ README.md               # quick start
```

## The two signature pieces (don't downgrade these to generic effects)
1. **Hero** - white/light brand hero with Vastu Gurukul as the H1, blue/green
   atmosphere, and Monica's real photo. She lives at `images/monica-hero.png`.
2. **"The Convergence"** (section `#why`) - a dark feature-band canvas animation:
   six discipline nodes ring a glowing **Vastu Gurukul** core, particle streams flow inward, core pulses,
   3D cursor parallax, orchestrated reveal on scroll. It is the centrepiece.

## Conventions & guardrails
- Keep it **one self-contained `index.html`** unless there's a clear reason to split.
- No build tooling. Preview with: `python3 -m http.server 8000` -> http://localhost:8000
- **All element `id`s must be unique** across the page (the hero SVG already uses
  `id="stage"`, `id="sky"`, `id="cglow"`, etc. — don't reuse). An earlier bug was an
  id collision between the hero gradient and the convergence wrapper.
- Always keep: keyboard focus styles, `prefers-reduced-motion` fallbacks, and the
  canvas animation paused when off-screen (IntersectionObserver).
- **Never generate synthetic/AI images of Monica** - she is a real person. Only edit
  real photos she provides (cutout, crop, colour-grade).
- Match the existing visual language; avoid generic "AI default" looks.

## TODO / open items
- [ ] Wire real contact links (currently `#`): WhatsApp, email, Facebook, LinkedIn.
      Known real links to use: website https://acharyamonica.com ·
      Facebook https://www.facebook.com/MahaVastuExpertMonica/ . WhatsApp number +
      email: ASK MONICA — not yet provided.
- [x] Use the provided Monica image in the About section.
- [ ] Page 2: pricing/courses page (when requested).

## How to preview
```bash
cd "C:\Users\Abhay\OneDrive\Desktop\MONICA MAHAVASTU"
python3 -m http.server 8000
# open http://localhost:8000
```
