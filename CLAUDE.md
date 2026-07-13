# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Static HTML website for ITEna Solutions, published via GitHub Pages directly from the repo root of `hpwp7.github.io` (custom domain `itenasolutions.com`, set via `CNAME`). **Any commit pushed to `main` goes live immediately** — there is no staging/build/review step in between.

The site was redesigned using Claude (design tool) and the exported HTML was copied directly into this repo. There is no source project, bundler, or template system behind it — the committed `.html` files are the actual deployed output.

## Commands

There is no build, lint, or test tooling — it's plain static HTML/CSS. To preview locally, just open the HTML files in a browser, or serve the directory with any static file server (e.g. `python -m http.server`). To publish, commit and push to `main`.

## Architecture

- `index.html`, `Solutions.html`, `contactUs.html` — the three pages of the site. Each is a fully self-contained HTML file with **all CSS inline** (mostly via `style="..."` attributes, plus a small `<style>` block in `<head>` for hover states and the `@media (max-width:900px)` responsive/mobile-nav breakpoint). There are no shared `.css` or `.js` files.
- Because styling is inline and duplicated per file, **header/nav/footer markup and shared styles (colors, fonts, spacing) must be edited in all three HTML files together** to stay consistent — there is no shared partial/include mechanism.
- Mobile nav menu is pure CSS (checkbox hack): a hidden `<input type="checkbox" id="nav-toggle">` toggled by a `<label>`, showing `.nav-links` via the `.nav-toggle-input:checked ~ .nav-links` selector. No JavaScript on the site.
- Fonts are loaded from Google Fonts (`Archivo` for headings, `IBM Plex Sans` for body text).
- Brand colors: dark navy `#1E2530` (backgrounds/text), red accent `#D21F23` / hover `#A8181C` (CTAs, highlights), grays `#4A5261`/`#6B6F76`/`#8B93A0` for secondary text.
- `assets/` holds the logo and favicon; `images/` holds page content images (hero backgrounds, icons, etc.).
- `CNAME` configures the custom domain for GitHub Pages — do not remove unless intentionally changing domains.

## Editing pages

When editing content or styling, match the existing inline-style conventions already in the file rather than introducing a `<style>` block, external stylesheet, or CSS classes for one-off styling — the current pages are consistent in doing everything inline except shared hover/responsive rules.
