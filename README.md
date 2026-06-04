# yeojun-site

Personal academic site for **Yeo Jun Choi** — PhD student in AI at Chung-Ang University.

Static HTML, no build step. Dark theme. Two pages:

- `index.html` — **about** (bio + news)
- `publications.html` — **publications** (year-grouped list, no thumbnails)

## Local preview

Open `index.html` in a browser, or serve the folder:

```powershell
python -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages

Already deployed at **https://yeo-jun-choi.github.io** from the repo
`Yeo-Jun-Choi/Yeo-Jun-Choi.github.io` (branch `main`, path `/`).

To publish updates:

```powershell
git -C e:\cluade\yeojun-site add .
git -C e:\cluade\yeojun-site commit -m "Update site"
git -C e:\cluade\yeojun-site push
```

Pages rebuilds automatically within ~1 minute.

## What to customize

| File / placeholder | What to do |
|---|---|
| KBS paper authors/order | `publications.html` — author list for *"Towards Refined Unlearning"* is a best guess (`Yeo Jun Choi, Woo-Seong Yun, Yoon-Sik Cho`). Confirm against the accepted manuscript. |
| KBS abstract | Inferred from the title only — replace with the real abstract once available. Swap the `journal` link for the DOI when issued. |
| `assets/profile.jpg` | Replace with a more formal photo when ready (current is the beach photo). |
| Email | Currently `csc950411 [at] gmail.com`. Swap for an academic email when you have one. |

## Structure

```
yeojun-site/
├── index.html          # about page (bio + news)
├── publications.html   # publications page (year-grouped)
├── style.css           # shared dark-theme styles
├── README.md           # this file
└── assets/
    └── profile.jpg     # 500×667, ~170KB
```

## Adding a new publication

In `publications.html`, copy a `<div class="pub-entry"> ... </div>` block into the
correct `<section class="pub-year">` (or add a new year section with an `<h2 class="year-head">`).
Each entry has: title, authors (wrap your name in `<span class="me">…</span>`),
venue, links (`paper` / `doi` / `code`), and a short abstract.
Use `<span class="pub-badge">Accepted</span>` after the title for in-press papers.

Then add a matching news row in `index.html`:

```html
<tr>
  <td class="date">2026</td>
  <td>Paper accepted at <strong>Venue</strong> &mdash; <em>&ldquo;Short Title&rdquo;</em>.</td>
</tr>
```

Newest goes on top.
