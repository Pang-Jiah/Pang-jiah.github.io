# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

Personal academic homepage deployable to GitHub Pages. It serves as a resume
(name, email, education, publications, research interests) and is intended to
grow into a personal blog. Style target is minimalist, referencing:

- https://teorth.github.io/tao-web/index.html (Terence Tao's site)
- https://sites.gc.sjtu.edu.cn/wwanglab/... (Wendong Wang CV PDF)

All user-facing content is written in English only.

## Current state

The Jekyll site is scaffolded. `Homepage requirement.md` is the source of truth
for content requirements. Fields the user fills manually are marked with
`[placeholder]` placeholders and `TODO` comments.

## Tech stack

- **Jekyll** — static site generator, runs natively on GitHub Pages (no local
  build required to deploy). Content is Markdown; templates use Liquid.

## Common commands

```bash
bundle install            # install dependencies (first run only)
bundle exec jekyll serve  # local dev server at http://localhost:4000
bundle exec jekyll build  # build the static site into _site/
```

Jekyll has no built-in test/lint step; validate by serving locally and
inspecting the rendered pages.

## Local environment (this machine)

- Ruby 4.0 is installed at a non-standard path:
  `C:\JiahuanPang\software\Ruby\Ruby40-x64\bin`. Add it to `PATH` before running
  `bundle`/`jekyll`:
  `export PATH="/c/JiahuanPang/software/Ruby/Ruby40-x64/bin:$PATH"`
- `rubygems.org` and `gems.ruby-china.com` are slow or blocked on this network.
  Bundler uses the TUNA mirror, configured in `.bundle/config`
  (`mirror.https://rubygems.org` → `https://mirrors.tuna.tsinghua.edu.cn/rubygems`).
  Keep that config; `.bundle/` is gitignored.

## Architecture (intended Jekyll layout)

- `_config.yml` — site-wide config (title, email, baseurl, etc.)
- `index.md` / `index.html` — homepage with the resume sections
- `_layouts/` — page templates (e.g. `default`, `post`)
- `_includes/` — reusable partials (header/footer)
- `_posts/` — blog posts, filenames `YYYY-MM-DD-title.md`, with YAML front matter
- `assets/` — CSS, JS, images
- `_site/` — generated output; never edit by hand

## Content conventions

- All user-facing content is written in English only.
- Fields the user fills manually (name, email, education, publications, research
  interests) get obvious placeholders, e.g. `<!-- TODO: your name -->` or `[Your Name]`.
- Blog posts are Markdown in `_posts/` with front matter (`title`, `date`, `lang: en`).
- Add `hide_nav: true` to a page's front matter to hide the header/nav on that
  page (used by the homepage).
