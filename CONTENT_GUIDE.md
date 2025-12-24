# How to Modify Content in Your Hugo Website

## Content Structure Overview

All editable content is located in the `content/` directory. Here's where to find and edit different types of content:

## 1. Homepage Sections (`content/home/`)

The homepage is built from multiple widget files. Each file controls a different section:

- **`index.md`** - Main homepage configuration
- **`about.md`** - Biography/About section (shows author profile)
- **`publications.md`** - Recent publications widget
- **`projects.md`** - Projects section
- **`people.md`** - Team/people section
- **`contact.md`** - Contact information
- **`experience.md`** - Experience/timeline
- **`accomplishments.md`** - Accomplishments/awards
- **`skills.md`** - Skills section
- **`talks.md`** - Talks/presentations
- **`posts.md`** - Blog posts section
- **`featured.md`** - Featured content

**To edit:** Open any `.md` file in `content/home/` and modify the YAML front matter (the section between `---` lines) and/or the markdown content below.

## 2. Author Profiles (`content/authors/`)

Each author has their own folder with:
- **`_index.md`** - Author information (name, bio, social links, etc.)
- **`avatar.jpg` or `avatar.png`** - Profile picture

**To edit an author:**
1. Navigate to `content/authors/[author-name]/_index.md`
2. Edit fields like:
   - `title` - Display name
   - `role` - Position/title
   - `bio` - Short biography
   - `organizations` - Affiliations
   - `interests` - Research interests
   - `social` - Social media links
   - `email` - Email address
   - Content below the front matter is the full biography

**To add a new author:**
1. Create a new folder: `content/authors/[new-author-name]/`
2. Copy `_index.md` from an existing author
3. Add an `avatar.jpg` or `avatar.png` image
4. Edit the content

## 3. Publications (`content/publication/`)

Each publication has its own folder with:
- **`index.md`** - Publication details (title, authors, date, etc.)
- **`featured.jpg`** - Featured image
- **`cite.bib`** - BibTeX citation (optional)
- **PDF files** - Publication PDFs

**To edit a publication:**
1. Navigate to `content/publication/[publication-name]/index.md`
2. Edit the YAML front matter with publication details

**To add a new publication:**
1. Create a new folder: `content/publication/[publication-name]/`
2. Copy `index.md` from an existing publication
3. Add a `featured.jpg` image
4. Add PDF files if needed
5. Edit the content

## 4. Projects (`content/project/`)

Similar structure to publications:
- **`index.md`** - Project description
- **`featured.jpg`** - Project image

## 5. Blog Posts (`content/post/`)

Each blog post has its own folder:
- **`index.md`** - Post content
- **`featured.jpg`** - Featured image

## 6. Site Configuration (`config/_default/`)

Main site settings:
- **`config.yaml`** - Site title, URL, language, etc.
- **`params.yaml`** - Theme settings, colors, fonts
- **`menus.yaml`** - Navigation menu structure
- **`languages.yaml`** - Language settings

**Important settings in `config.yaml`:**
- `title` - Website name
- `baseurl` - Website URL (change from 'https://example.com/')
- `copyright` - Footer copyright text

## 7. Events (`content/event/`)

Similar to posts - each event has a folder with `index.md` and images.

## Workflow: Edit → Generate → View

1. **Edit content files** in `content/` directory
2. **Regenerate the site:**
   ```bash
   cd template
   export PATH="$HOME/go/bin:$HOME/bin:$PATH"
   hugo --gc --minify
   ```
3. **View locally (optional):**
   ```bash
   hugo server
   ```
   Then open http://localhost:1313 in your browser

4. **Deploy:** The generated files in `public/` can be uploaded to any web server

## File Format

Most content files use **Markdown** with **YAML front matter**:

```markdown
---
# YAML front matter (metadata)
title: Your Title
author: author-name
date: 2024-01-01
---

# Markdown content goes here

This is regular markdown content that appears on the page.
```

## Tips

- **Images:** Place images in the same folder as the content file, or in `static/uploads/`
- **Markdown:** Use standard Markdown syntax for formatting
- **Preview:** Use `hugo server` to see changes before deploying
- **Backup:** Always backup your `content/` directory before making major changes

