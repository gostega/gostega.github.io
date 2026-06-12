# gostega.github.io

Personal website, live at [www.tuson.me](https://www.tuson.me). Jekyll site using the
[Neumorphism theme](https://github.com/longpdo/neumorphism), deployed automatically by
GitHub Pages (legacy build) on every push to `master` — no CI setup or local build needed.

## How to update content

Edit the YAML files, push to `master`, done. The site rebuilds itself in a minute or two.

| What | Where |
|---|---|
| Job history / education timeline | `_data/timeline.yml` |
| Skills bars | `_data/skills-languages.yml`, `skills-technologies.yml`, `skills-tools.yml` |
| Personal projects | `_data/projects.yml` |
| Name, tagline, about-me text, contact links | `_config.yml` (top section) |

The "Open Source Projects" section is populated automatically from public GitHub repos
(via `jekyll-github-metadata`, configured by `repository:` in `_config.yml`).

## Local preview (optional)

Pushing is enough — GitHub Pages builds the site. To preview locally first:

```sh
mise install            # installs the pinned Ruby (mise.toml)
bundle install
bundle exec jekyll serve # http://localhost:4000
```

## Notes

- **Styling**: edit `assets/css/main.min.scss` (colours/fonts are variables near the top) and
  push — GitHub Pages compiles it to `main.min.css` via Jekyll's built-in Sass. No local build.
- `assets/js` is still pre-built and committed. The gulp/npm toolchain (`package.json`,
  `gulpfile.js`, `_js/`) is only needed to rebuild the JS bundles after theme changes — not for
  content or styling updates. It uses deprecated `node-sass`; avoid touching it.
- The `Gemfile` / `Gemfile.lock` / `mise.toml` are only for local preview; GitHub Pages uses
  its own pinned Jekyll version regardless.
- Custom domain is set via `CNAME` (www.tuson.me).
