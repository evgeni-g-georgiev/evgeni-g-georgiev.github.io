# Personal site

Jekyll site hosted on GitHub Pages. No build step to run yourself: push to
`main` and GitHub rebuilds it in about a minute.

## Where things live

| I want to change...        | Edit this                                   |
|----------------------------|---------------------------------------------|
| Name, email, links, URL    | `_config.yml`                               |
| The intro paragraph        | `index.md` (the `lede` block)               |
| Which projects are shown   | `_data/projects.yml`                        |
| The CV                     | `cv.md`                                     |
| Add a blog post            | New file in `_posts/`                       |
| Colours and fonts          | `assets/css/style.css` (tokens at the top)  |

## Adding a blog post

Create `_posts/YYYY-MM-DD-short-title.md`. The filename sets the date and URL,
and must follow that pattern exactly. Start the file with:

```
---
title: "Your title"
date: 2026-08-15
standfirst: One sentence summary shown in listings.
tags: [notes]
---
```

Then write in Markdown below it. Copy the existing post as a starting point. If a post has a PDF version,
put it in `assets/files/` and add `pdf: /assets/files/name.pdf` to the front
matter, and a download button appears automatically.

## Adding a project

Copy a block in `_data/projects.yml` and change the values. Order in the file
is the order on the page.

## Previewing locally (optional)

Not required, since you can edit directly on github.com. If you do want it:

```
gem install bundler jekyll
bundle init && bundle add jekyll jekyll-feed jekyll-seo-tag jekyll-sitemap
bundle exec jekyll serve
```

Then open http://localhost:4000.
