# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal academic website for Chenming Tang, deployed at jamydon.online (custom domain) via GitHub Pages. Built with Jekyll on the AcademicPages template (Minimal Mistakes fork). 5 pages are active: Home (about), CV, Publications, Musings, and Contact.

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
compress.html → default.html → archive.html  (CV, Publications, Musings list)
                             → single.html   (individual musing pages)
```

`default.html` includes: `head.html`, `masthead.html`, `footer.html`, `scripts.html`

### Content

- `_pages/` — `about.md` (home at `/`), `cv.md`, `publications.md`, `musings.md`, `contact.md`, `404.md`
- `_data/publications.yml` — Structured publication data (title, authors, venue, links)
- `_data/navigation.yml` — Top nav menu
- `_musings/` — One markdown file per musing post, named `YYYY-MM-DD-slug.md`
- `images/` — Avatar and site images
- `files/CV.pdf` — Downloadable CV

### Publications (Data-Driven)

Publications are stored in `_data/publications.yml` (no individual pages). Schema per entry:

```yaml
- title: "Paper Title"
  authors: "**Chenming Tang**, Coauthor Name"   # markdown bold for self
  venue: "ACL 2026"                             # short name, shown in badge
  venue_full: "Proceedings of the 64th Annual Meeting..."  # shown in text
  date: YYYY-MM-DD                              # for ordering
  links:
    - label: Publication                        # first link used for title href
      url: https://...
    - label: Preprint
      url: https://...
    - label: Code
      url: https://...
```

Rendered by `_includes/publication-data-single.html` with pill-button links and venue badges.

### Musings (Jekyll Collection)

Blog-like short posts. Each file in `_musings/` with front matter:

```yaml
---
title: "Post Title"
collection: musings
permalink: /musings/short-slug
date: YYYY-MM-DD
excerpt: "One-line preview for the list page."
---
```

List page uses `_includes/musing-single.html` (compact layout: title + date badge + excerpt).

### Key Includes

- `author-profile.html` — Sidebar rendered from `_config.yml` `author:` section; empty fields are hidden
- `publication-data-single.html` — Renders a publication entry from `_data/publications.yml`
- `musing-single.html` — Renders a musing entry in the compact list
- `base_path` — Must be included once per template before using `{{ base_path }}`

### Styling

SCSS in `_sass/`, compiled via `assets/css/main.scss`. Key variables in `_variables.scss`. Vendor libs (Font Awesome, Susy, Breakpoint) in `_sass/vendor/`.

Shared UI components (defined in `_sass/_archive.scss`):
- `.pub-link` — Pill-button base class (rounded, colored, with icon)
- `.pub-link--publication` (blue), `--preprint` (orange), `--code` (green), `--scholar` (blue), `--cv` (purple), `--contact` (red)
- `.musing-item` — Compact list item with title, date badge, and excerpt
- `.musing-item__date-badge` — Inline date/venue badge
- `.contact-notice` — Styled callout card with left accent border

### Theming (Light/Dark Mode)

Colors use CSS custom properties defined in `_sass/_theme.scss`. Light values on `:root`, dark overrides on `html[data-theme="dark"]`. Key files:

- `_includes/head/custom.html` — early inline script reads `localStorage` / `prefers-color-scheme` and sets `data-theme` before CSS loads
- `_includes/masthead.html` — contains the fixed-position toggle button (`#theme-toggle`) and its inline `<script>` with the click handler (must be before `main.min.js` to avoid jQuery intercepting clicks)
- `_sass/_theme.scss` — all CSS custom property definitions + `.theme-toggle` button styles

When adding new colors, use `var(--...)` from `_theme.scss` rather than raw SCSS color variables so dark mode stays consistent. Dark-mode overrides for `.pub-link` variants are in `_sass/_archive.scss`.

### Anti-Crawling (Email Protection)

Email addresses are NOT stored in plain text anywhere in rendered HTML. On the contact page:
- `data-u` and `data-d` attributes store user/domain separately
- JavaScript assembles and injects the full email + mailto link at runtime
- HTML entity encoding provides fallback for no-JS browsers
- `_config.yml` `author.email` is left blank to keep sidebar clean

### Important Caveats

- **compress.html layout** minifies all HTML into one line — never use `//` comments in inline `<script>` blocks (they comment out the rest of the line). Use `/* */` or no comments.
- **main.min.js** (jQuery + greedy-nav + plugins) intercepts click events — any new interactive elements should register handlers BEFORE `main.min.js` loads (place `<script>` in `masthead.html` or before `scripts.html`), and use `e.stopPropagation()`.
- **Custom domain**: site is served at `jamydon.online`. The `url` in `_config.yml` must match. CSS/JS use root-relative paths (`/assets/...`) to avoid protocol issues.
- **Flex layout in `.archive`**: The `.archive a` rule forces `text-decoration: underline` on links. When placing inline elements (like title + badge) inside `.archive`, avoid using flex on a wrapping `<div>` — instead use a `<p>` with inline children for reliable same-line rendering.

## Deployment

Push to `master` → GitHub Pages auto-builds. The `github-pages` gem pins Jekyll/plugin versions to match the GH Pages environment.
