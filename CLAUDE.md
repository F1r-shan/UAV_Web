# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**KhachatryanUAV** is a static website for an Armenian UAV engineering company. No build step, no dependencies, no package manager — open any HTML file directly in a browser to preview.

## Files

- **`uav-website/index.html`** — Main landing page (single-file: CSS + HTML + JS all inline)
- **`uav-website/simulator.html`** — Standalone 3D UAV flight simulator page (also single-file)

## Architecture

### index.html

1. **CSS** — in a `<style>` block in `<head>`. Organized with section comments (e.g. `/* ── NAV */`, `/* ── HERO */`). Uses CSS custom properties defined in `:root` for the color theme.
2. **HTML** — page sections in order: `<nav>`, `.hero`, `#about`, `#models`, `#donate`, `<footer>`
3. **JavaScript** — inline `<script>` at the bottom. Handles mobile nav toggle, donation amount selection, and the (stub) `donate(method)` function.

### simulator.html

A full-screen 3D flight simulator built with raw Canvas/WebGL (no Three.js or other libraries). Key parts:
- Fixed nav bar with model selector (Kh-25 / Kh-26) and a back link to `index.html`
- `<canvas id="c">` occupies the remaining viewport below the nav
- HUD overlay panels (left: flight data + battery bars; right: telemetry stats) rendered as HTML over the canvas
- Controls legend panel (bottom-right)
- All simulation logic is inline JavaScript at the bottom of the file

The simulator uses `--accent2: #a855f7` (purple) instead of the orange used in `index.html`.

## Theme / Design System

Colors are controlled via CSS variables in `:root`:
```css
--accent:  #00c8ff   /* cyan — primary accent */
--accent2: #ff6b00   /* orange — CTA buttons */
--dark:    #080c14   /* page background */
--card:    #0e1623   /* card backgrounds */
```

## Key Notes

- The **donation system is frontend-only** — `donate(method)` shows an alert. Real payment integration (Stripe, PayPal SDK, crypto) needs to replace that function.
- UAV illustrations are **inline SVGs** inside the HTML, not external image files.
- Responsive breakpoints target mobile below `700px` via media queries.
- The site targets **no external dependencies** — no frameworks, no CDN links.
KhachatryanUAV is a single-page static website for an Armenian UAV engineering company, showcasing the Kh-25 and Kh-26 fixed-wing UAV platforms. The site includes a donation UI (frontend only — no payment backend is connected).

## Running the Site

No build tools or package manager. Open `uav-website/index.html` directly in a browser, or serve it with any static file server:

```bash
# Python
python -m http.server 8080 --directory uav-website

# Node (npx)
npx serve uav-website
```

## Architecture

The entire site lives in a single file: `uav-website/index.html`. It contains:

- **Inline `<style>`** — all CSS, organized by section with comments (NAV, HERO, ABOUT, MODELS, DONATE, FOOTER, RESPONSIVE)
- **Inline `<script>`** — donation logic (amount selection, custom input, payment method UI, progress bar)
- **Inline SVG** — aircraft illustrations embedded directly in the HTML

## Theme / Design System

CSS custom properties are declared in `:root` at the top of the `<style>` block:

```css
:root {
  --dark:    #080c14;
  --darker:  #050810;
  --card:    #0e1623;
  --border:  #1a2640;
  --accent:  #00c8ff;   /* cyan */
  --accent2: #ff6b00;   /* orange */
  --text:    #cdd8e8;
  --muted:   #5a7090;
  --white:   #f0f6ff;
}
```

All color changes should go through these variables.

## Key Integration Points

- **Donation payments** — the `donate(method)` JS function is the stub to replace with real payment SDKs (PayPal, Stripe, crypto wallets).
- **Responsiveness** — media queries at the bottom of the `<style>` block target breakpoints around 700px and 900px.
