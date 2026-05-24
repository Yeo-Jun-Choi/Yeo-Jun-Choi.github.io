# yeojun-site

Personal academic page for **Yeo Jun Choi** — PhD student in AI at Chung-Ang University.

Single-page static HTML, no build step. Inspired by [Jon Barron's site](https://jonbarron.info/).

## Local preview

Open `index.html` directly in a browser, or:

```powershell
# any static server works
python -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages

A GitHub user page lives at `https://<username>.github.io` and must be served from a repo named exactly `<username>.github.io`.

```powershell
# 1. create the repo on GitHub (manual or via gh CLI)
gh repo create Yeo-Jun-Choi.github.io --public --description "Personal page"

# 2. push this folder
cd e:\cluade\yeojun-site
git init
git add .
git commit -m "Initial personal page"
git branch -M main
git remote add origin https://github.com/Yeo-Jun-Choi/Yeo-Jun-Choi.github.io.git
git push -u origin main
```

GitHub Pages activates automatically for `<username>.github.io` repos on the `main` branch. The site appears at https://yeo-jun-choi.github.io within ~1 minute.

## What to customize before going live

| File / placeholder | What to do |
|---|---|
| `assets/profile.jpg` | Replace with a more formal photo when ready (current is the beach photo). |
| Bio paragraphs in `index.html` | Sanity-check the wording — written from inference, may need tweaks. |
| Publication abstracts | I drafted short summaries; replace with your own one-liners if preferred. |
| Email | Currently `csc950411 [at] gmail.com`. Swap for an academic email when you have one. |

## Structure

```
yeojun-site/
├── index.html        # the whole page
├── style.css         # styling (Jon Barron-inspired)
├── README.md         # this file
└── assets/
    └── profile.jpg   # 500×667, ~170KB
    └── cv.pdf        # (you add this)
```

## Adding a new publication

In `index.html`, copy any `<div class="pub"> ... </div>` block under the Publications section and edit. Thumbnail color picks from one of these classes (or add your own in `style.css`):

- `thumb-asc` (navy)
- `thumb-recsys` (red)
- `thumb-llm` (green)
- `thumb-eswa` (purple)

## Adding a news item

Append a `<tr>` to the `.news-table` in `index.html`. Newest goes on top.
