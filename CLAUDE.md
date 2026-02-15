# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal Jekyll-based static site that deploys to GitHub Pages. Currently hosted at `usethedata.github.io`, but will eventually move to the custom domain `usethedata.net`.

**Content Types:**
- Blog posts (`_posts/`) - Essays, thoughts, and observations
- Photos (`_photos/`) - Photography with links to Flickr/Glass or hosted images
- Experiments (`_experiments/`) - Data projects and creative explorations

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

## Content Structure

**Creating Content:**

Blog posts (in `_posts/`):
```bash
# Filename format: YYYY-MM-DD-title.md
_posts/2024-01-15-my-post-title.md
```

Photos (in `_photos/`):
```bash
# Any filename.md
_photos/sunset-beach.md
```

Experiments (in `_experiments/`):
```bash
# Any filename.md
_experiments/data-visualization.md
```

**Front Matter Examples:**

Blog post:
```yaml
---
layout: post
title: "Post Title"
date: 2024-01-15 12:00:00 -0500
tags: [tag1, tag2]
---
```

Photo:
```yaml
---
layout: photo
title: "Photo Title"
date: 2024-01-15
location: "City, Country"
flickr_url: https://www.flickr.com/photos/user/id
glass_url: https://glass.photo/user/id
thumbnail: /assets/images/thumb.jpg
---
```

Experiment:
```yaml
---
layout: default
title: "Experiment Title"
description: "Brief description"
tags: [data, visualization]
---
```

## Project Structure

- `_posts/` - Blog posts (YYYY-MM-DD-title.md format)
- `_photos/` - Photo collection (Jekyll collection)
- `_experiments/` - Experimental content (Jekyll collection)
- `_layouts/` - HTML templates (default, post, photo)
- `_includes/` - Reusable HTML snippets
- `assets/images/` - Hosted images
- `_config.yml` - Site configuration
- `index.md` - Homepage
- `blog.md`, `photos.md`, `experiments.md` - Section index pages
- `context/` - **Local only** - AI development context files (never committed)\n- `_site/` - Generated static site (git-ignored)

## Key Files

- `Gemfile` - Ruby dependencies (Jekyll and plugins)
- `_config.yml` - Jekyll configuration (title, description, URL, plugins)
- `Dockerfile` - Docker container definition for local development
- `docker-compose.yml` - Docker Compose configuration for easy container management
- `.github/workflows/deploy.yml` - GitHub Actions deployment workflow

## Configuration Notes

- The site uses Jekyll 4.3 with Materialize CSS framework for Material Design styling
- Materialize CSS is loaded from CDN in `_layouts/default.html`
- Plugins: `jekyll-feed`, `jekyll-seo-tag`, and `jekyll-paginate`
- Collections: `photos` and `experiments` for flexible content organization
- LiveReload is enabled for automatic browser refresh during development
- Photos can be hosted locally in `assets/images/` or linked to Flickr/Glass
- Future migration to `usethedata.net` will require updating `url` in `_config.yml`

## Design System

- **Framework:** Materialize CSS 1.0.0 (Material Design)
- **Icons:** Material Icons
- **Typography:** Roboto font family
- **Color scheme:** Blue (#1565c0 primary, #0d47a1 dark)
- **Layout:** Responsive grid system with cards and hover effects
- **Navigation:** Responsive navbar with mobile sidenav

## Adding Images

**Host locally:**
1. Add images to `assets/images/` directory
2. Reference in markdown: `![Alt text](/assets/images/filename.jpg)`

**Link to Flickr/Glass:**
1. Add `flickr_url` or `glass_url` to front matter
2. Embed using standard markdown or HTML img tags
## Context Folder (AI Development)

The `context/` folder is for **local use only** and stores temporary files used for AI-assisted development:

- Draft content before publishing
- Reference materials and notes
- Sample data or API responses
- Any files needed for AI context

**Protection:**
- Added to `.gitignore` (never tracked by git)
- Pre-commit hook blocks any attempt to commit files from this folder
- Safe place to store sensitive or temporary development files

This ensures context files never accidentally end up in the repository or deployed site.
