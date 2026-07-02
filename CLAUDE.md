# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**visual-builder** is the **Zapier Platform Docs** website — the documentation site for building Zapier integrations (Platform UI and Platform CLI). It is a static site built with **Jekyll** (Ruby) and served as GitHub Pages / a static host. Content is Markdown/HTML; there is no application backend.

## Tech Stack

- **Static site generator**: Jekyll 3.7+ (Ruby 2.2.5+)
- **Dependency management**: Bundler (`Gemfile` / `Gemfile.lock`)
- **Templating**: Liquid (`_layouts/`, `_includes/`)
- **Content**: Markdown + HTML pages
- **Config**: `_config.yml`

## Repository Structure

```
_config.yml          # Jekyll site configuration
_layouts/            # Page templates: default, post, post-toc, search
_includes/           # Partials: head, header, side-nav, toc, search, prev-next, javascript, events-toolkit
docs/                # Documentation content (the bulk of the site)
index.md             # Home page
search/ , search.md  # On-site search
404.html
assets/              # fonts, images, stylesheets, JS
Gemfile / Gemfile.lock
CONTRIBUTING.md      # contribution guidelines
LICENSE.md
```

## Commands

```bash
bundle install               # install Ruby gem dependencies
bundle exec jekyll serve     # local dev server → http://localhost:4000 (live reload)
bundle exec jekyll build     # build the static site → _site/
```

Prerequisites: Ruby 2.2.5+, Bundler, Jekyll 3.7+ (rvm recommended for Ruby version management).

## Working On This Repo

- **This is documentation.** Most changes are content edits under `docs/` and `index.md`, or template/style tweaks in `_layouts/`, `_includes/`, and `assets/`.
- Front matter matters: Jekyll pages need YAML front matter; follow the pattern in neighboring files so layout/nav/TOC render correctly.
- Preview locally with `bundle exec jekyll serve` before committing — Liquid errors surface at build time.
- Follow `CONTRIBUTING.md` for content/style conventions.
- Don't hand-edit `Gemfile.lock`; change `Gemfile` and re-run `bundle install`.
- Generated output (`_site/`) is not committed.
