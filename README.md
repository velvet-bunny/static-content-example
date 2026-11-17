# static-content-example

A minimal example of keeping Markdown content in a repo and publishing it as a static
website on GitHub Pages, using [Jekyll](https://jekyllrb.com/) (built into GitHub Pages).

Published at: <https://velvet-bunny.github.io/static-content-example/>

## Structure

```text
_config.yml              Site settings, section list and per-folder defaults
_layouts/
  default.html           Page shell (header, nav, CSS)
  section.html           Section landing page: renders its content + lists its guides
  guide.html             A single guide page (marked as searchable content for Pagefind)
_includes/
  search.html            Pagefind search box with a section filter (used on the home page)
assets/css/
  base.css               Shared styling
  micro.css              Micro-guides styling
  idle.css               Idle-guides styling
  cyberpunk.css          Cyberpunk-guides styling (animations, overlays, clip-paths; CSS only)
index.md                 Home page
micro-guides/            Micro-guides section (index.md + one .md per guide)
idle-guides/             Idle-guides section (index.md + one .md per guide)
cyberpunk-guides/        Cyberpunk-guides section (index.md + one .md per guide)
.github/workflows/pages.yml  Builds (Jekyll, then Pagefind) and deploys on every push to main
```

## Search

[Pagefind](https://pagefind.app/) runs after Jekyll in the publishing workflow. It indexes
every guide page (the `data-pagefind-body` element in `_layouts/guide.html`) and writes the
index and search UI into `_site/pagefind/`. Searching happens entirely in the browser.

## Adding a guide

Drop a Markdown file in a section folder with a `title` (and optional `summary`):

```markdown
---
title: My New Guide
summary: One line shown on the section page.
---

Content goes here.
```

The section's layout and styling are applied automatically via `defaults` in
`_config.yml`, and the guide appears in the section's list.

## Adding a section

1. Create a folder, e.g. `deep-guides/`, with an `index.md` using `layout: section`.
2. Add `assets/css/deep.css`.
3. In `_config.yml`, add an entry to `sections` (`id: deep`) and a `defaults` entry
   for `path: "deep-guides"` with `section: deep`.

## Publishing

In the repository settings under **Pages**, set **Source** to **GitHub Actions**. Every
push to `main` then deploys the site.

## Local preview

With Ruby installed:

```sh
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000/static-content-example/>.

Search only works after Pagefind has indexed a build. With Node.js installed:

```sh
bundle exec jekyll build --baseurl ""
npx pagefind --site _site --serve
```

Then open <http://localhost:1414/>.