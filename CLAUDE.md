# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal professional profile site for Bruce E. Wilson, built with Jekyll and deployed to GitHub Pages. Currently hosted at `usethedata.github.io`, with planned migration to `usethedata.me`. The blog/photos/experiments site will be a separate repo at `usethedata.net`.

The site is a single-page professional profile emphasizing Earth science data systems, cyberinfrastructure, FAIR data, and interdisciplinary science expertise. It targets an audience of scientific committee selectors and professional peers.

## Local Development with Docker (Preferred)

```bash
# Start the Jekyll server in Docker with LiveReload
docker-compose up

# Rebuild container after Gemfile changes
docker-compose up --build

# Stop the container
docker-compose down

# Access the site at http://localhost:4000
```

Docker is used for local development to provide a consistent environment and as a learning tool.

## Local Development without Docker

```bash
# Install dependencies
bundle install

# Serve locally with LiveReload
bundle exec jekyll serve --livereload

# Build the site
bundle exec jekyll build

# Clean generated files
bundle exec jekyll clean
```

## Deployment Strategy

GitHub Actions automatically builds and deploys the site:
- `main` branch → Production at https://usethedata.github.io
- `dev` branch → Development environment for testing GitHub rendering
- Feature branches → Local testing only (do not deploy)

Deployment workflow: `.github/workflows/deploy.yml`

## Project Structure

- `_layouts/` - HTML templates (`default.html` — the single layout)
- `assets/images/` - Hosted images (headshot, etc.)
- `_config.yml` - Site configuration
- `index.md` - Homepage / profile page (the main content page)
- `context/` - **Local only** - AI development context files (never committed)
- `my_context/` - **Local only** - AI development context files (never committed)
- `_site/` - Generated static site (git-ignored)

## Key Files

- `Gemfile` - Ruby dependencies (Jekyll and plugins)
- `_config.yml` - Jekyll configuration (title, description, URL, plugins)
- `Dockerfile` - Docker container definition for local development
- `docker-compose.yml` - Docker Compose configuration for easy container management
- `.github/workflows/deploy.yml` - GitHub Actions deployment workflow

## Configuration Notes

- The site uses Jekyll 4.3 with custom CSS (no framework)
- Plugins: `jekyll-feed` and `jekyll-seo-tag`
- Single-page profile site — all content is in `index.md`
- Future migration to `usethedata.me` will require updating `url` in `_config.yml`

## Design System

- **Styling:** Custom CSS (no framework)
- **Typography:** Roboto font family (Google Fonts)
- **Color scheme:** Navy blue (#1a365d primary, #2c5282 accent), light gray (#f7fafc) background
- **Layout:** Single-page responsive profile with hero, expertise grid, experience list, publications, education, and awards sections
- **Responsive:** Flexbox/Grid, mobile-friendly without a framework

## Context Folders (AI Development)

The `context/` and `my_context/` folders are for **local use only** and store temporary files used for AI-assisted development:

- Reference materials and notes
- Source documents (CV, bio sketches, etc.)
- Any files needed for AI context

**Protection:**
- Added to `.gitignore` (never tracked by git)
- Pre-commit hook blocks any attempt to commit files from `context/`
- Safe place to store sensitive or temporary development files

This ensures context files never accidentally end up in the repository or deployed site.
