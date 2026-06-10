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

## Notes

- `assets/css` and `assets/js` are pre-built and committed. The gulp/npm toolchain
  (`package.json`, `gulpfile.js`, `_sass/`, `_js/`) is only needed to rebuild them after
  theme changes — not for content updates. It uses deprecated `node-sass` and won't build
  on modern Node without effort; avoid touching it.
- The `Gemfile` is only for local preview (`bundle exec jekyll serve`); GitHub Pages uses
  its own pinned Jekyll version regardless.
- Custom domain is set via `CNAME` (www.tuson.me).
