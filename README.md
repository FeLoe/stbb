# Steve Taylor Blues Band — Website

Website for the Steve Taylor Blues Band, built with [Hugo](https://gohugo.io) and the [Congo](https://github.com/jpanther/congo) theme. Deployed on Netlify at [steve-taylor-blues.band](https://steve-taylor-blues.band).

## Stack

- Hugo v0.157.0 + Congo v2.13.0
- Decap CMS at `/admin` (Netlify Identity, git-gateway backend)
- Hosted on Netlify (auto-deploy on push to `main`)

## Local development

```bash
hugo server --port 1315
```

Requires Hugo Extended. The theme is vendored in `_vendor/` so no Go module download is needed.

## Content

Content is managed via the CMS or directly in these directories:

| Directory | Description |
|---|---|
| `content/event/` | Concert dates (leaf bundles) |
| `content/post/` | News and press articles |
| `content/gallery/` | Gallery photos |
| `content/songs/` | Songs page |
| `assets/media/` | Images uploaded via CMS |
| `static/files/` | MP3 files |

## Key configuration

- `config/_default/config.yaml` — Hugo config
- `config/_default/params.yaml` — Congo theme params
- `config/_default/menus.de.yaml` — Navigation and footer menus
- `static/admin/config.yml` — Decap CMS collections
- `netlify.toml` — Build config (Hugo version, build command)

## Build cache

`resources/` is committed to git so that Netlify can skip reprocessing images on most builds. After bulk image uploads via CMS, run `hugo` locally and commit the updated `resources/` directory.

## Custom layouts

All custom layouts are in `layouts/` and override Congo defaults. Custom SCSS is in `assets/scss/custom.scss`.
