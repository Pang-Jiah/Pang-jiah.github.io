# Personal Homepage

A minimalist Jekyll-based personal homepage and blog, deployable to GitHub Pages.

## Preview locally

Requires Ruby and Bundler. After installing:

```bash
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000.

## Fill in your information

- Open `_config.yml` to set the site title and email.
- Open `index.md` to fill in your name, education, research interests, and publications.
- Every field to fill is marked with a `[placeholder]` or a `TODO` comment — search for `TODO` to find them.

## Write a blog post

Create a new file in `_posts/` named `YYYY-MM-DD-title.md`, starting with:

```yaml
---
layout: post
title: "Title"
date: 2026-01-01
lang: en
---
```

Write the body in Markdown.

## Deploy to GitHub Pages

1. Create a repository on GitHub (for `https://<username>.github.io`, name the repo `<username>.github.io`).
2. Push this directory to the repository.
3. In the repo's **Settings → Pages**, set the Source to the `main` branch root (or GitHub Actions).
4. After a few minutes, visit `https://<username>.github.io`.
