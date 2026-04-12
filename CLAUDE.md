# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**KhachatryanUAV** is a single-page landing website for an Armenian UAV engineering company. It is a purely static site — one HTML file with all CSS and JavaScript inlined.

- **Entry point:** `uav-website/index.html`
- **No build step, no dependencies, no package manager**

To preview: open `uav-website/index.html` directly in a browser.

## Architecture

Everything lives in `uav-website/index.html`:

1. **CSS** — in a `<style>` block in `<head>`. Organized with section comments (e.g. `/* ── NAV */`, `/* ── HERO */`). Uses CSS custom properties defined in `:root` for the color theme.
2. **HTML** — page sections in order: `<nav>`, `.hero`, `#about`, `#models`, `#donate`, `<footer>`
3. **JavaScript** — inline `<script>` at the bottom. Handles mobile nav toggle, donation amount selection, and the (stub) `donate(method)` function.

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
