# Nunez Lab Website — Claude Code Guide

## What this is

Hugo static site (v0.88.1) using the **Wowchemy Academic v5** theme for the Nunez Lab at UBC. Deployed via GitHub Pages from the `docs/` folder.

**Do not upgrade Hugo** — v0.88.1 is pinned because Wowchemy v5 is incompatible with newer Hugo versions.

## Build & Deploy

```bash
hugo server -D          # Local preview at http://localhost:1313 (live reload)
hugo --gc --minify      # Build production output into docs/
```

After building, commit and push `docs/` to main. GitHub Pages publishes automatically.

## Key Directories

| Path | Purpose |
|---|---|
| `content/` | All editable content — this is where almost all changes happen |
| `content/authors/` | Team member profiles (38+ members) |
| `content/publication/` | Research publications |
| `content/project/` | Research projects |
| `content/post/` | Blog posts |
| `content/home/` | Homepage widget sections |
| `config/_default/` | Site config (config.yaml, params.yaml, menus.yaml) |
| `assets/media/` | Images and media assets |
| `static/uploads/` | User-uploaded files |
| `docs/` | **Generated output — do not edit directly** |
| `layouts/` | Custom template overrides |

## Content Patterns

All content files use Markdown with YAML front matter. The pattern is always: create a folder, add `index.md` (or `_index.md` for authors).

### Adding/Editing a Team Member

Path: `content/authors/<slug>/_index.md` + `avatar.jpg`

```yaml
---
title: Full Name
superuser: false
role: PhD Student
organizations:
  - name: University of British Columbia
    url: https://www.ubc.ca
bio: One-sentence bio.
interests:
  - Natural Language Processing
  - Mental Health Informatics
education:
  courses:
    - course: MSc Computer Science
      institution: Some University
      year: 2022
social:
  - icon: envelope
    icon_pack: fas
    link: mailto:email@ubc.ca
  - icon: github
    icon_pack: fab
    link: https://github.com/username
  - icon: google-scholar
    icon_pack: ai
    link: https://scholar.google.com/citations?user=XXXXX
user_groups:
  - Grad Students   # see valid groups below
weight: 50          # lower = displayed earlier
highlight_name: false
---
```

**Valid `user_groups` values:**
- `Lab Leadership`
- `Researchers`
- `Grad Students`
- `Undergrad Students`
- `Research Software Developer`
- `Team Members (Technical)`
- `Team Members (Medical)`
- `Visitors`
- `Alumni`

### Adding a Publication

Path: `content/publication/<slug>/index.md`

```yaml
---
title: "Publication Title"
authors:
  - First Author
  - admin        # use "admin" for Dr. Nunez, or author slug for lab members
  - Other Author
date: "2024-01-01"
doi: "10.1234/example"
publication_types: ["2"]   # 2=Journal article, 1=Conference, 3=Preprint
publication: "*Journal Name*, vol. X"
abstract: "Abstract text here."
featured: false             # true = appears in Featured section on homepage
tags:
  - NLP
  - Mental Health
url_pdf: ""
url_code: ""
url_dataset: ""
projects: []               # link to project slugs
---
```

**`publication_types` values:** 0=Uncategorized, 1=Conference paper, 2=Journal article, 3=Preprint, 4=Report, 5=Book, 6=Book chapter, 7=Thesis, 8=Patent

Add `featured.jpg` or `featured.png` for a thumbnail. Optionally add `cite.bib` for BibTeX.

### Adding a Project

Path: `content/project/<slug>/index.md`

```yaml
---
title: Project Name
summary: One-paragraph summary shown in listings.
date: "2023-01-01"
tags:
  - NLP
  - Clinical Decision Support
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""
---

Full project description in markdown here.
```

Add `featured.jpg` or `featured.png` for the project card image.

### Adding a Blog Post

Path: `content/post/<slug>/index.md`

```yaml
---
title: Post Title
date: "2024-01-01"
subtitle: ""
summary: Short description.
authors:
  - admin
tags:
  - Lab News
featured: false
draft: false
projects: []
---

Post content in markdown.
```

### Editing Homepage Sections

Files in `content/home/` control homepage layout. Key fields:
- `active: true/false` — show or hide the section
- `weight: N` — display order (lower = higher on page)

The homepage sections are: about, featured, projects, people, posts, blogs, contact, experience, accomplishments, skills, talks, tags.

## Navigation Menu

Edit `config/_default/menus.yaml` to add/remove/reorder nav links.

## Common Tasks

**Moving someone to Alumni:** Change their `user_groups` in `content/authors/<slug>/_index.md` to `- Alumni`.

**Featuring a publication on homepage:** Set `featured: true` in the publication's `index.md`.

**Hiding a homepage section:** Set `active: false` in the relevant `content/home/*.md` file.

**Reordering team members:** Adjust `weight:` — lower numbers appear first.

**Reordering homepage sections:** Adjust `weight:` in `content/home/*.md` files.

## Notes

- The `admin` author slug refers to Dr. Nunez (the lab director, `superuser: true`)
- `docs/` is the publish directory (not the default `public/`) — this is set in `config.yaml` for GitHub Pages
- Images should be placed in the same folder as the content file, or in `assets/media/`
- The `pics_to_sort/` folder in the repo root holds unsorted team member photos waiting to be placed
