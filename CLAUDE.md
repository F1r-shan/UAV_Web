# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

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
