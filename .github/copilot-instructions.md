<!-- Copilot instructions for contributors and AI coding agents -->
# Copilot instructions — Academic Jekyll site (concise)

Purpose: help an AI coding agent become productive quickly in this repository.

- Big picture:
  - This is a Jekyll site based on the Academic Pages template (see `README.md`).
  - Content is markdown-driven. Templates live in `_layouts/` and small reusable fragments are in `_includes/`.
  - Styles in `_sass/` (Sass partials); runtime assets in `assets/` (JS under `assets/js/`).
  - Collections: `talks`, `publications`, `teaching`, `portfolio` (configured in `_config.yml`).

- Key configuration files:
  - `_config.yml` — site defaults, collections, plugin list, `analytics` and `comments` settings.
  - `Gemfile` — Ruby/gems for local dev and GitHub Pages compatibility (`github-pages` gem).
  - `package.json` — JS tooling: `npm run build:js` and `npm run watch:js` (see `uglify` script).

- Local dev & build commands (explicit / reproducible):
  - Install Ruby gems: `bundle install` (use `Gemfile`).
  - Serve locally: `bundle exec jekyll serve -l -H localhost` (or `jekyll serve -l -H localhost` per README). Use `bundle exec` to honor `Gemfile`.
  - Build JS: `npm run build:js` -> produces `assets/js/main.min.js` via `uglifyjs`.
  - Watch JS: `npm run watch:js` to rebuild `main.min.js` on edits.

- Content authoring conventions (concrete examples):
  - Blog posts: file under `_posts/` named `YYYY-MM-DD-your-title.md` with YAML front matter. Example front matter:
    ```yaml
    ---
    title: "Blog Post number 1"
    date: 2012-08-14
    permalink: /posts/2012/08/blog-post-1/
    tags: [cool posts, category1]
    ---
    ```
  - Talks: generated into `_talks/` (see `markdown_generator/talks.py`). Each talk front matter commonly includes `collection: talks`, `type`, `venue`, `date`, `location`, and `permalink`.
    - To regenerate talks from TSV: run the script from `markdown_generator/` (e.g. `python3 talks.py`) after updating `talks.tsv`.

- Patterns & behaviors to preserve:
  - Default layouts are defined in `_config.yml` (e.g., posts use `layout: single`, talks use `layout: talk`). Avoid changing these without verifying templates in `_layouts/`.
  - Uploaded static files belong in `files/` and are served at `/files/<name>`.
  - SCSS partials are built by Jekyll from `_sass/`; keep visual changes there rather than editing compiled CSS directly.

- Integrations and extensibility:
  - Comments: configurable via `_config.yml` (`disqus`, `discourse`, `staticman`, etc.). Staticman-specific keys are present under `comments.staticman`.
  - Analytics: set `analytics.google.tracking_id` in `_config.yml`.
  - GitHub Pages: repository relies on `github-pages` gem — prefer `bundle exec` when running Jekyll locally.

- Helpful files to inspect when changing behavior:
  - `_includes/` — small HTML fragments used across templates (navigation, sidebar, social share)
  - `_layouts/` — main page templates (`default.html`, `single.html`, `talk.html`)
  - `assets/js/_main.js` and `package.json` scripts for JS processing
  - `markdown_generator/` for programmatic content creation (talks/publications)

- What not to assume / gotchas:
  - The site is configured to include and exclude specific files in `_config.yml` (e.g., `package.json` is excluded from site output). Don't rely on files existing in the published site without checking `_config.yml`.
  - Use the `github-pages` gem set in `Gemfile` for compatibility with GitHub Pages; using a different Jekyll version can change build-time behavior.

- If anything here is unclear or you want more detail (CI, deployment hooks, sensitive integrations), tell me which area to expand and I will iterate.
