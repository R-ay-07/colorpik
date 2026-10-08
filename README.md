# colorpik

**A color picking & palette studio for designers.** Pick a base color — get a complete, ready-to-use palette.

colorpik is a cross-platform color tool for designers, illustrators, interior stylists, e-commerce artists and shop owners. Choose an industry, pick a base color on the wheel, and the app generates a full palette by its color-matching logic — ready for posters, storefronts, UI design and more.

> **Live demo:** https://colorpik-web2.pages.dev/ *(deployed on Cloudflare Pages)*
>
> **Note:** This repository hosts the product introduction and screenshots only. The application source code is maintained in a separate private repository.

---

## Demo

**Pick, blend, ramp** — the picker, blending two colors by ratio, then a gradient:

![colorpik demo](assets/videos/picker-demo.gif)

**Layout preview & image picking** — set the grid, import a photo, extract its colors, then select swatches and send them to the palette:

![Layout preview and color extraction demo](assets/videos/preview-demo.gif)

Higher quality: [picker-demo.mp4](assets/videos/picker-demo.mp4) · [preview-demo.mp4](assets/videos/preview-demo.mp4)

---

## Screenshots

**Desktop · 1280 × 800**

| Picker | Mix | Gradient |
| --- | --- | --- |
| ![Picker — hue wheel, lightness and opacity sliders, neighbor swatch row](assets/screenshots/picker.png) | ![Mix — two colors blended by ratio](assets/screenshots/mix.png) | ![Gradient — multi-stop ramp with angle and segment controls](assets/screenshots/gradient.png) |

| Overlay | Schemes | Style |
| --- | --- | --- |
| ![Overlay — stacked colors with top-layer opacity](assets/screenshots/overlay.png) | ![Schemes — harmony sets from the current color](assets/screenshots/schemes.png) | ![Style — curated color-family palettes](assets/screenshots/style.png) |

| Color name search | Industry presets | Settings |
| --- | --- | --- |
| ![Search a color by name](assets/screenshots/name-search.png) | ![Industry presets dropdown](assets/screenshots/industry-menu.png) | ![Settings sheet](assets/screenshots/settings.png) |

**Phone · 340 × 720**

| Picker | Schemes | Industry |
| --- | --- | --- |
| ![Phone — picker](assets/screenshots/phone-picker.png) | ![Phone — schemes](assets/screenshots/phone-schemes.png) | ![Phone — industry picker](assets/screenshots/phone-industry.png) |

*All images live in `assets/screenshots/` and `assets/videos/`. See [Asset inventory](#asset-inventory) below.*

---

## What it does

colorpik is built around one idea: **you should not have to guess the second color.**

Pick a base color once. Then use the industry presets and color-science layer to derive every other color you need — a mix, a gradient, an overlay, a harmonious scheme, or a complete style palette — and export the whole thing as a color card.

---

## Modules

| Module | What it does |
| --- | --- |
| **Picker** | Hue around the wheel, saturation vertically; the bottom slider sets the hue / saturation segment length; the left and right sliders adjust lightness and opacity. Switchable short / long hue range and a 12- or 24-swatch neighbor row. Type or paste HEX / RGB(A) / HSL(A), or search a color by name. |
| **Mix** | Blend 2–4 colors by their own ratios into one new color. Choose the blend space — perceptual (OKLCH) or numeric (sRGB) — and lock the result so the app back-solves one input to keep the mix unchanged while you tune the rest. |
| **Gradient** | Transition between colors and generate the in-between stops. Adjust segment count and angle, tap a stop to select it, then add it to the palette. |
| **Overlay** | Stack colors with a top layer that carries its own opacity — a different opacity lets a different amount of the layer below show through. Includes glaze, lighten, darken, tulle, sunlight and shadow presets. |
| **Schemes** | Generate harmonious schemes from the current color — analogous, complementary, triadic, split-complementary, tetradic and monochrome — plus a layout preview with photo import and automatic color extraction. |
| **Style** | 30+ curated color-family styles (Morandi, cream, macaron, dopamine, wabi-sabi, wafu, Klein blue, Chinese traditional, Y2K, cyberpunk, Memphis, Mondrian and more), each with its own palette set. |
| **Industry** | Seven industry presets — general, painting, fashion, home decor, UI design, e-commerce and nail art — that swap the picker swatches, the Style palettes and the Schemes suggestions in one tap. |

---

## Feature highlights

- **Industry-aware palettes.** Pick an industry and every module follows: the picker's neighbor swatches, the Style palette library and the Schemes suggestions are all replaced with domain-specific colors and recipes.
- **Color science, not guesswork.** WCAG 2.1 contrast verdicts (AA / AAA) with an automatic best-text-color suggestion, OKLab / OKLCH perceptual interpolation for gradients and mixes, and linear-light compositing for physically correct alpha blending.
- **Layout preview & image picking.** Import a photo or take one, place it into the layout preview, and extract its dominant colors straight into the grid — similar colors are merged automatically.
- **Area-ratio guidance.** A built-in 60 / 30 / 10 (wall / ceiling / floor, or primary / secondary / accent) weighting check with plain-language advice when a palette reads too dark or too light.
- **Copy anywhere.** Every color card copies as HEX, RGB, RGBA, HSL or HSLA in one tap, and can be pushed to the palette or set as the current color.
- **Palette library & export.** Save named palettes locally, then export a PNG color card containing exactly the sections you select (picker, mix, gradient, overlay, grid).
- **Result lock.** Freeze a mixed color and keep tuning the other inputs — the app solves the remaining one so the result never drifts.
- **Undo & local history.** Undo the last deletion, and restore any previously saved palette in a single tap.

---

## Color science

colorpik keeps a strict separation between *picking* and *judging*:

| Layer | Responsibility |
| --- | --- |
| **sRGB ↔ linear-light** | Gamma-correct conversion following the WCAG 2.1 threshold. |
| **WCAG 2.1 contrast** | Contrast ratio (1–21) with AA / AAA pass-fail for body and large text, plus an automatic black-or-white text recommendation. |
| **OKLab / OKLCH** | Perceptually uniform interpolation — linear luminance, shortest hue path — so midpoints do not turn muddy and complements do not turn gray. |
| **Linear-light compositing** | Physically correct `source-over` alpha blending, available side by side with the browser's gamma-space result. |

Where a result is ambiguous, the app shows both the perceptual and the numeric answer so you can compare them directly.

---

## Industries

`General` · `Painting` · `Fashion` · `Home Decor` · `UI Design` · `E-commerce` · `Nail Art`

Each industry ships with its own palette groups, fixed schemes, mix recipes, gradient presets and overlay presets.

---

## Languages

English · 简体中文 · 日本語 · 한국어

All four are full UI translations, including the industry data and color names.

---

## Platforms

One codebase, three layout tiers:

- **Phone** — portrait-first, full-screen PWA
- **Tablet** — adapted wheel and panel sizing
- **Desktop / laptop** — multi-column layout with the full toolbar

Every layout is tuned per screen size rather than scaled wholesale, so the color wheel, sliders and swatches stay aligned at any resolution.

---

## Privacy

**All color data stays on your device.** Palettes, saved colors and settings are stored locally. No account is required, and no personal information is collected.

---

## Tech stack

- **Flutter** (Dart) — single codebase for web, Android and iOS
- **Riverpod** — state management
- **Hive** — local, offline-first storage
- **Cloudflare Pages** — static hosting of the web build

---

## Build from source

*The application source lives in a private repository. For maintainers:*

```bash
flutter pub get
flutter build web --release
# output: build/web
```

Deploy the `build/web` directory to Cloudflare Pages.

---

## Asset inventory

Captured at **1280 × 800 (desktop)** and **340 × 720 (phone)** and stored under `assets/`:

| File | Screen |
| --- | --- |
| `screenshots/picker.png` | Picker — wheel, L/A sliders, HUE track, neighbor swatch row |
| `screenshots/mix.png` | Mix — two colors blended by ratio |
| `screenshots/gradient.png` | Gradient — multi-stop ramp, angle and segment controls |
| `screenshots/overlay.png` | Overlay — stacked colors with top-layer opacity |
| `screenshots/schemes.png` | Schemes — harmony sets from the current color |
| `screenshots/style.png` | Style — curated color-family palette |
| `screenshots/name-search.png` | Picker — Name tab (search a color by name) |
| `screenshots/industry-menu.png` | Industry presets dropdown (desktop top bar) |
| `screenshots/settings.png` | Settings sheet |
| `screenshots/phone-picker.png` | Phone — Picker |
| `screenshots/phone-mix.png` | Phone — Mix |
| `screenshots/phone-gradient.png` | Phone — Gradient |
| `screenshots/phone-overlay.png` | Phone — Overlay |
| `screenshots/phone-schemes.png` | Phone — Schemes |
| `screenshots/phone-style.png` | Phone — Style |
| `screenshots/phone-industry.png` | Phone — Industry picker |
| `videos/picker-demo.mp4` | Demo recording — picker → mix ratio → gradient (H.264, ~8 s) |
| `videos/picker-demo.gif` | Same recording as an inline GIF |
| `videos/preview-demo.mp4` | Demo recording — layout preview, import photo, extract colors, select and add to palette (H.264) |
| `videos/preview-demo.gif` | Same recording as an inline GIF |

---

## Contact

Questions, bug reports or feature requests: **colorpik25@outlook.com**

---

## License

Personal, non-commercial use only. Redistribution or resale is not allowed.