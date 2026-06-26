# Himanshu Bundel — Portfolio

A static, self-contained portfolio website. Analytics & Data Science work, with
twelve project case studies that link to the full rendered notebooks.

## Structure

```
index.html        Home page (experience, skills, projects, academic, creative, about, contact)
projects.html     Full projects gallery — 4 featured case studies + the full catalogue
work/             Rendered Jupyter notebooks for the projects that link to "View full analysis"
README.md
```

Everything the two pages need (fonts as base64, all images, the render runtime) is
inlined directly into `index.html` and `projects.html`, so there is **no build step**.
The only external requests are Google Fonts and the GSAP animation library, both loaded
from a CDN — so the site needs an internet connection (always true when hosted online).

## Deploy

### Vercel
1. Push this folder to a GitHub repository.
2. In Vercel, **Add New… → Project**, import the repo.
3. Framework preset: **Other**. Leave Build Command empty and Output Directory as the
   repository root (`./`). Vercel serves `index.html` at `/` automatically.
4. Deploy. That's it — it's a static site.

### GitHub Pages (alternative)
Settings → Pages → Source: *Deploy from a branch* → `main` / root. The site appears at
`https://<username>.github.io/<repo>/`.

## Editing
The pages are plain HTML. To change copy, colours, or projects, edit `index.html` /
`projects.html`. The project data lives in the `<script>` block near the bottom of each
file (the `featured` / `more` arrays in `projects.html`, the `projects` array in `index.html`).
