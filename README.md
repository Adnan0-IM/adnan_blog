# Adnan Blog

Personal blog built with [Hugo](https://gohugo.io/) using the [Congo](https://github.com/jpanther/congo) theme.

## Stack

- Hugo (extended)
- Congo theme (git submodule)
- GitHub Actions for build and deploy
- GitHub Pages (`gh-pages` branch)

## Local Development

### 1) Prerequisites

- Install Hugo extended (recommended: `0.155.3`)

Check version:

```bash
hugo version
```

### 2) Run locally

```bash
hugo server -D
```

Site will be available at `http://localhost:1313`.

### 3) Production build

```bash
hugo --minify
```

Generated output is written to `public/`.

## Writing Content

### New post

```bash
hugo new posts/my-new-post.md
```

### New page

```bash
hugo new my-page.md
```

Core content locations:

- `content/_index.md` - homepage content
- `content/about.md` - about page
- `content/posts/` - blog posts

## Configuration

Main config files:

- `config/_default/hugo.toml` - Hugo core settings
- `config/_default/params.toml` - Congo theme params
- `config/_default/languages.en.toml` - site title, author, language settings
- `config/_default/menus.en.toml` - top navigation

## Deployment

Deployment is handled by GitHub Actions:

- Workflow: `.github/workflows/gh-pages.yml`
- Trigger: push to `master`
- Build command: `hugo --minify`
- Publish branch: `gh-pages`

If deployment fails, check:

1. Hugo version compatibility with the theme
2. Menu/config TOML syntax
3. Theme submodule checkout in Actions

## Useful Commands

```bash
# Start dev server with drafts
hugo server -D

# Build production output
hugo --minify

# Clean build target manually (optional)
rm -rf public resources/_gen
```

## License

Content is owned by the site author unless stated otherwise.
Theme license is defined in `themes/congo/LICENSE`.
