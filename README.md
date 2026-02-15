# UseTheData

A personal site for sharing photos, writing, and data experiments.

## Local Development with Docker

```bash
# Build and start the Docker container
docker-compose up

# Or rebuild if you've changed the Gemfile
docker-compose up --build

# Stop the container
docker-compose down
```

The site will be available at:
- Site: http://localhost:4000
- LiveReload will automatically refresh your browser on changes

## Local Development without Docker

```bash
# Install dependencies
bundle install

# Serve the site locally
bundle exec jekyll serve --livereload
```

## Deployment

The site automatically deploys to GitHub Pages when changes are pushed to:
- `main` branch → Production site at https://usethedata.github.io
- `dev` branch → Development site for testing GitHub rendering

Feature branches only render locally.

## Future Domain

This site will eventually be hosted at usethedata.net.
