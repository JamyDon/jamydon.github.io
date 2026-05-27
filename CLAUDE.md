# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based academic personal website built on the [AcademicPages](https://github.com/academicpages/academicpages.github.io) theme (forked from Minimal Mistakes). It showcases academic research, publications, CV, and contact information for Chenming Tang, a Master's student in Computer Science at Peking University specializing in NLP and Computational Linguistics.

**Repository:** `JamyDon/jamydon.github.io` (GitHub Pages site)  
**Live Site:** `jamydon.github.io`

## Build & Development Commands

### Setup
```bash
# Install dependencies (Ruby 2.7+, bundler required)
bundle install

# If you encounter errors, try clean reinstall:
rm Gemfile.lock
bundle install
```

### Local Development
```bash
# Serve locally with live reload (rebuilds on file changes)
bundle exec jekyll serve -l -H localhost

# Access at http://localhost:4000
```

### Build
```bash
# Generate production-ready static site (outputs to _site/)
bundle exec jekyll build
```

### Note on Configuration Changes
If you modify `_config.yml`, you **must restart** the Jekyll server for changes to take effect (live reload does not watch this file).

## Architecture & Structure

### Core Configuration
- **`_config.yml`** - Primary site configuration
  - Site metadata (title, author info, URLs)
  - Collection definitions (publications)
  - Plugin configuration (jekyll-feed, jekyll-sitemap, etc.)
  - Sass/markdown processing settings
  - Default layouts and frontmatter for pages/publications

- **`_data/`** - YAML data files
  - `navigation.yml` - Main navigation menu links (CV, Publications, Contact)
  - `ui-text.yml` - Localized strings for UI labels

### Content Structure

#### Pages (`_pages/`)
Static pages using Jekyll's pages collection:
- `about.md` - Homepage/landing page (permalink: `/`)
- `cv.md` - Curriculum vitae
- `publications.md` - Publications archive page
- `contact.md` - Contact/contact form
- `404.md` - 404 error page

**Default layout:** All pages use `single.html` with sidebar author profile enabled.

#### Publications (`_publications/`)
Academic publications as a custom collection (Jekyll collection).

**File naming pattern:** `YYYY-VENUE-Title.md` (e.g., `2023-ACL-Are.md`)

**Common frontmatter fields:**
```yaml
---
title: "Paper Title"
collection: publications
permalink: /publication/[unique-slug]
date: YYYY-MM-DD
venue: "Conference/Journal Name"
citation: "Author et al. ..."
paperurl: "https://..."  # Link to PDF
---
```

Publication content supports inline links to code, preprints, and supplementary materials.

### Template Hierarchy

```
default.html (page base template)
  ↓
single.html (page content template)
  ├── page__hero.html (optional header overlay)
  ├── breadcrumbs.html
  ├── sidebar.html → author-profile.html (left sidebar)
  ├── page__content (main content area)
  └── social-share.html (share buttons)
```

**Key templates:**
- `default.html` - Wraps content with base HTML, head, masthead, footer
- `single.html` - Single-page/post layout with sidebar and metadata
- `archive.html` - Used for publication listing (archive view)
- `compress.html` - HTML compression layout (parent of default.html)

### Includes (`_includes/`)

**Page Structure:**
- `head.html` - Head tag with CSS, SEO, meta tags
- `masthead.html` - Top navigation bar (reads from `navigation.yml`)
- `footer.html` - Site footer with social icons
- `sidebar.html` → `author-profile.html` - Left sidebar with author bio and social links

**Utilities:**
- `base_path` - Base path variable (set once per template)
- `seo.html` - SEO metadata (Open Graph, Twitter cards, structured data)
- `author-profile.html` - Renders author info with icon links to social profiles, academic sites
- `read-time.html` - Estimated reading time
- `social-share.html` - Social sharing buttons

### Styling (`_sass/`)

SCSS modules organized by component:
- `_variables.scss` - Colors, fonts, breakpoints, spacing
- `_base.scss` - Element resets, typography
- `_mixins.scss` - Reusable SCSS mixins (media queries, etc.)
- `_masthead.scss` - Top navigation styling
- `_navigation.scss` - Navigation menu styles (responsive greedy nav)
- `_page.scss` - Page and article layouts
- `_sidebar.scss` - Sidebar and author profile styling
- `_archive.scss` - Archive/list page layouts
- `_footer.scss` - Footer styling
- `_utilities.scss` - Helper classes
- `vendor/` - Third-party libraries (Breakpoint, Susy, Font Awesome, Magnific Popup)

**Compiled output:** `assets/css/main.css` (generated from `assets/css/main.scss`)

### Assets (`assets/`)

- `css/main.scss` - SCSS entry point (compiles to main.css)
- `css/academicons.css` - Academic icons font
- `js/main.min.js` - Minified JavaScript bundle (jQuery, plugins)
- `js/_main.js` - Unminified source
- `js/plugins/` - jQuery plugins (fitvids, etc.)
- `webfonts/` - Font Awesome icon fonts (TTF, WOFF2)
- `fonts/` - Academicons font files

### Special Directories

- `images/` - User-uploaded images (avatar, etc.)
- `files/` - Downloadable files (PDFs, etc.) - accessible at `/files/[filename]`
- `_site/` - Build output (generated, ignore in development)

## Key Configuration Details

### Collections
Publications are configured as a custom collection in `_config.yml`:
```yaml
collections:
  publications:
    output: true
    permalink: /:collection/:path/
```
This generates publication pages at `/publications/[slug]/`.

### Defaults (Frontmatter)
- **Pages:** `layout: single`, `author_profile: true`
- **Publications:** `layout: single`, `author_profile: true`, `share: true`

### Author Profile
The author sidebar is controlled by the `author` section in `_config.yml`:
- Basic info: name, bio, location, employer, email
- Academic links: Google Scholar, ORCID, arXiv, etc.
- Social profiles: GitHub, Twitter, LinkedIn, etc.

The `author-profile.html` include dynamically renders icons based on which fields are populated.

### Plugins
- `jekyll-feed` - RSS feed generation
- `jekyll-sitemap` - Sitemap generation
- `jekyll-paginate` - Pagination support
- `jekyll-redirect-from` - Redirect support
- `jekyll-gist` - Embed GitHub gists
- `hawkins` - Live reload (development)

### Markdown Processing
- **Markdown engine:** Kramdown
- **Syntax highlighting:** Rouge
- **Input format:** GFM (GitHub Flavored Markdown)
- **Table of contents:** Auto-generated for h1-h6

## Common Development Tasks

### Adding a Publication
1. Create `_publications/YYYY-VENUE-Title.md`
2. Add frontmatter (title, date, venue, citation, paperurl, etc.)
3. Write brief description or abstract in body
4. Restart Jekyll or wait for auto-rebuild
5. Verify at `/publications/[slug]/`

### Updating the Navigation Menu
1. Edit `_data/navigation.yml`
2. Add/modify entries under `main:` list
3. Restart Jekyll (changes to `_config.yml` and `_data/` require restart)

### Modifying Author Profile
1. Edit `_config.yml` in the `author:` section
2. Add/remove social links (they only render if field is populated)
3. Restart Jekyll

### Styling Changes
1. Edit corresponding SCSS file in `_sass/`
2. Changes to `assets/css/main.scss` or `_sass/` files auto-rebuild on save
3. Refresh browser to see changes

### Custom CSS
Add custom styles in `_sass/_custom.scss` (if it exists) or directly in `_sass/_page.scss` for page-specific overrides.

## Important Patterns & Conventions

### Liquid Templating
- `{% include base_path %}` must be called once per template to set the `base_path` variable
- Links use `{{ base_path }}{{ link.url }}` to respect GitHub Pages subpath deployments
- Conditional rendering: `{% if page.field %}...{% endif %}` prevents empty HTML when field is missing

### Font Awesome Icons
- Solid icons: `<i class="fa-solid fa-icon-name"></i>` (e.g., `fa-location-dot`)
- Brand icons: `<i class="fab fa-github"></i>`
- Academicons (academic): `<i class="ai ai-google-scholar"></i>`

### Publication Metadata Display
The `single.html` layout automatically renders:
- Paper title and publication date
- Citation info
- Links to paper PDF and slides (if `paperurl` and `slidesurl` frontmatter provided)
- Social share buttons (if `share: true`)

### Author Profile Sidebar
Dynamically renders based on populated fields in `_config.yml`:
- Empty fields don't generate icons (cleaner sidebar)
- Icon selection uses Font Awesome and Academicons libraries
- Follows schema.org Person microdata format

## GitHub Pages Deployment

This repository is set up as a GitHub Pages site (`[username].github.io`).

- **Branch:** Uses `master` (or `main`) branch for source
- **Build:** GitHub Pages auto-builds with Jekyll
- **CNAME file:** Custom domain configuration (if applicable)
- **Deployment:** Changes pushed to branch automatically deploy

Local builds (`bundle exec jekyll build`) generate the same output as GitHub Pages.

## Troubleshooting

### Common Issues

**"Jekyll command not found"**
- Ensure bundler is installed: `gem install bundler`
- Use `bundle exec jekyll` instead of `jekyll` directly

**Port 4000 already in use**
```bash
bundle exec jekyll serve -p 4001 -l -H localhost
```

**Changes not appearing**
- If you modified `_config.yml` or `_data/`, restart Jekyll (Ctrl+C, then re-run)
- Browser cache: do a hard refresh (Cmd+Shift+R / Ctrl+Shift+R)

**Build errors with gems**
```bash
rm Gemfile.lock
bundle install
```

## Additional Resources

- [Jekyll Documentation](https://jekyllrb.com/)
- [AcademicPages Documentation](https://academicpages.github.io/)
- [Minimal Mistakes Theme](https://mademistakes.com/work/minimal-mistakes-jekyll-theme/)
- [Kramdown Markdown Reference](https://kramdown.gettalong.org/quickref.html)
