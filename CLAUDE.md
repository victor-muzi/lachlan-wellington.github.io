# CLAUDE.md

## What this site is

The personal portfolio of Lachlan Wellington, cyber security student at Macquarie University (graduating November 2026). It's a Jekyll site built on the Chirpy theme, hosted free on GitHub Pages at https://lachlan-wellington.github.io. Its purpose is professional: showcasing projects, CTF writeups, and learning notes to support job applications in cyber security. Keep that audience in mind - recruiters and hiring managers may read anything published here.

## How deployment works

- The GitHub repo must be named exactly `lachlan-wellington.github.io`.
- Pushing to `main` (or `master`) triggers GitHub Actions (`.github/workflows/pages-deploy.yml`), which builds and publishes the site automatically. One-time setup on GitHub: Settings -> Pages -> Source: GitHub Actions.
- No local build is required to publish. To preview locally instead: install Ruby + Bundler, run `bundle install` once, then `bash tools/run.sh` and open the printed localhost URL.

## Where content lives (the files to edit)

| Path | What it is |
| --- | --- |
| `index.md` | The homepage bio |
| `_posts/` | Blog posts (filename must be `YYYY-MM-DD-short-title.md`) |
| `_projects/` | Project cards shown on the Projects page |
| `_tabs/` | The nav pages (Blog, Projects, Categories) - rarely need editing |
| `_config.yml` | Site-wide settings: name, tagline, email, social links, avatar |
| `_data/contact.yml` | Which contact icons appear in the sidebar |
| `assets/img/` | Images (avatar, project images, post images) |

## Theme internals (don't edit casually)

`_layouts/`, `_includes/`, `_sass/`, `_javascript/`, and `assets/js/dist/` are Chirpy theme code, already customised with a projects gallery and a static homepage. Only touch these for deliberate design changes, and expect to test locally first.

## Adding a blog post

Create `_posts/YYYY-MM-DD-short-title.md` with this frontmatter:

```yaml
---
title: "Post Title"
date: 2026-06-12 14:00:00 +1000
categories: [CTF, Writeups]
tags: [networking, linux]
description: "One-line summary shown in previews and search."
---
```

Then write the body in Markdown. Good post material: CTF writeups, Security+ study notes, home lab build logs. Categories take at most two levels; tags are free-form lowercase.

## Adding a project

Copy `_projects/sample-project.md`, rename it, and fill it in. The `order` field controls position on the Projects page (lower = earlier). The `image` block is optional - add the image file to `assets/img/` first.

## Adding an avatar

Add a square photo to `assets/img/` (e.g. `avatar.jpg`) and set `avatar: /assets/img/avatar.jpg` in `_config.yml`.

## Conventions and cautions

- This repo is public. Never commit secrets, API keys, passwords, or private documents.
- Keep personal details minimal: email, GitHub, and LinkedIn are enough. No phone number or street address.
- Don't change the `permalink` settings in `_config.yml` - it breaks existing links.
- Australian English spelling throughout.
- Write for a professional audience: clear, concrete, and honest about what you built and learned.
