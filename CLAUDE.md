# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal academic website for Chenming Tang, deployed at jamydon.online (custom domain) via GitHub Pages. Built with Jekyll on the AcademicPages template (Minimal Mistakes fork). Only 4 pages are active: Home (about), CV, Publications, and Contact.

## Build & Development

Requires **Ruby 3.x** (not 4.x — Jekyll 3.x/Liquid 4.x uses removed `tainted?` method on Ruby 4). On macOS:

```bash
export PATH="/opt/homebrew/opt/ruby@3.3/bin:/opt/homebrew/lib/ruby/gems/3.3.0/bin:$PATH"
bundle install
bundle exec jekyll serve -l -H localhost   # http://127.0.0.1:4000/
```

Changes to `_config.yml` require restarting the server (not live-reloaded).

## Architecture

### Template Hierarchy

```
compress.html → default.html → archive.html  (CV, Publications list)
                             → single.html   (individual publication pages)
```

`default.html` includes: `head.html`, `masthead.html`, `footer.html`, `scripts.html`

### Content

- `_pages/` — `about.md` (home at `/`), `cv.md`, `publications.md`, `contact.md`, `404.md`
- `_publications/` — One file per paper, named `YYYY-VENUE-ShortName.md`
- `_data/navigation.yml` — Top nav menu
- `images/` — Avatar and site images
- `files/CV.pdf` — Downloadable CV

### Publication File Format

```yaml
---
title: "Paper Title"
collection: publications
permalink: /publication/YYYY-VENUE-ShortName
date: YYYY-MM-DD
---

**Authors**\
_Venue_ **(Abbreviation YEAR)**\
[Publication](url) | [Preprint](url) | [Code](url)
```

### Key Includes

- `author-profile.html` — Sidebar rendered from `_config.yml` `author:` section; empty fields are hidden
- `archive-single.html` — Renders each pub in the `/publications/` list
- `base_path` — Must be included once per template before using `{{ base_path }}`

### Styling

SCSS in `_sass/`, compiled via `assets/css/main.scss`. Key variables in `_variables.scss`. Vendor libs (Font Awesome, Susy, Breakpoint) in `_sass/vendor/`.

### Theming (Light/Dark Mode)

Colors use CSS custom properties defined in `_sass/_theme.scss`. Light values on `:root`, dark overrides on `html[data-theme="dark"]`. Key files:

- `_includes/head/custom.html` — early inline script reads `localStorage` / `prefers-color-scheme` and sets `data-theme` before CSS loads
- `_includes/masthead.html` — contains the fixed-position toggle button (`#theme-toggle`) and its inline `<script>` with the click handler (must be before `main.min.js` to avoid jQuery intercepting clicks)
- `_sass/_theme.scss` — all CSS custom property definitions + `.theme-toggle` button styles

When adding new colors, use `var(--...)` from `_theme.scss` rather than raw SCSS color variables so dark mode stays consistent.

### Important Caveats

- **compress.html layout** minifies all HTML into one line — never use `//` comments in inline `<script>` blocks (they comment out the rest of the line). Use `/* */` or no comments.
- **main.min.js** (jQuery + greedy-nav + plugins) intercepts click events — any new interactive elements should register handlers BEFORE `main.min.js` loads (place `<script>` in `masthead.html` or before `scripts.html`), and use `e.stopPropagation()`.
- **Custom domain**: site is served at `jamydon.online`. The `url` in `_config.yml` must match. CSS/JS use root-relative paths (`/assets/...`) to avoid protocol issues.

## Deployment

Push to `master` → GitHub Pages auto-builds. The `github-pages` gem pins Jekyll/plugin versions to match the GH Pages environment.
