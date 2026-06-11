# CLAUDE.md

Personal academic website for Chenming Tang at jamydon.online. Jekyll + AcademicPages (Minimal Mistakes fork), GitHub Pages. Pages: Home, CV, Publications, Musings, Contact.

## Build

Requires **Ruby 3.x** (not 4.x). Changes to `_config.yml` require server restart.

```bash
export PATH="/usr/local/opt/ruby@3.3/bin:/usr/local/lib/ruby/gems/3.3.0/bin:$PATH"
bundle exec jekyll serve -l -H localhost   # http://127.0.0.1:4000/
```

## Content Structure

- `_pages/` — `about.md`, `cv.md`, `publications.md`, `musings.md`, `contact.md`
- `_data/publications.yml` — All publications (title, authors, venue, venue_full, date, links)
- `_data/navigation.yml` — Top nav menu
- `_musings/YYYY-MM-DD-slug.md` — Blog-like posts (Jekyll collection, has individual pages)
- `_includes/publication-data-single.html` — Renders one publication from data file
- `_includes/musing-single.html` — Renders one musing in compact list

## Publications Schema (`_data/publications.yml`)

```yaml
- title: "Paper Title"
  authors: "**Chenming Tang**, Coauthor"  # markdown bold for self
  venue: "ACL 2026"                       # badge text
  venue_full: "Proceedings of the 64th..."
  date: YYYY-MM-DD
  cv_group: refereed | preprint           # which CV section
  cv_order: 1                             # sort order within CV group
  home_selected: true                     # (optional) show on home page
  home_order: 1                           # (optional) sort order on home page
  links:
    - { label: Publication, url: "..." }  # first link = title href
    - { label: Preprint, url: "..." }
    - { label: Code, url: "..." }
```

## Musings Front Matter

```yaml
---
title: "Post Title"
collection: musings
permalink: /musings/slug
date: YYYY-MM-DD
excerpt: "Preview text."
---
```

## Styling Notes

- SCSS in `_sass/`, variables in `_variables.scss`, theme colors in `_theme.scss`
- `.pub-link` (in `_archive.scss`) — pill-button base; variants: `--publication`, `--preprint`, `--code`, `--scholar`, `--cv`, `--contact`
- `.musing-item` — compact list row; `.musing-item__date-badge` — inline badge
- Use `var(--...)` from `_theme.scss` for dark-mode-safe colors
- Dark-mode overrides for pub-link variants live in `_archive.scss`

## Important Caveats

- **compress.html** minifies HTML to one line — use `/* */` not `//` in inline scripts.
- **main.min.js** intercepts clicks — register handlers BEFORE it loads, use `e.stopPropagation()`.
- **Flex inside `.archive`** doesn't work reliably — use `<p>` with inline children instead.
- **Email protection**: contact page uses `data-u`/`data-d` + JS assembly; no plain email in HTML. `_config.yml` `author.email` is blank.

## Deployment

Push to `master` → GitHub Pages auto-builds.
