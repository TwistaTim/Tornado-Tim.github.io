# Diawatch – Jekyll version

This folder is a direct Hexo → Jekyll conversion of the `diawatch.org`
repository.

## Highlights

- Posts from `source/_posts` have been converted into Jekyll posts in `_posts/`
  with filenames like `YYYY-MM-DD-title.md`.
- Front matter has been normalised to proper YAML with `layout: post`.
- A custom Jekyll theme is included (no external gem theme), styled to be
  visually similar to the old Hexo "ayer" theme:
  - Dark background
  - Hero cover using `/images/cover1.jpg`
  - Simple header navigation: Home, Archive, About

## How to use in your repo

1. Back up your current `diawatch.org` repo.
2. Remove Hexo-specific directories: `scaffolds`, `themes`, `source`, `node_modules`,
   and Hexo config files (`package.json`, `package-lock.json`, old `_config.yml`).
3. Copy all contents of this folder into the root of your repo.
4. Commit and push. GitHub Pages will build it as a Jekyll site.

You can further tweak:

- `_config.yml` for pagination, plugins, etc.
- `_layouts/*.html` and `assets/css/main.css` to refine the design.
