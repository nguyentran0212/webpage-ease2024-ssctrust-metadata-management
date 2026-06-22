# webpage-ease2024-ssctrust-metadata-management

Public landing page for the EASE 2024 paper "An Empirically Grounded Reference Architecture for Software Supply Chain Metadata Management" (Tran, Pallewatta & Babar, EASE 2024, pp. 38–47, DOI: [10.1145/3661167.3661212](https://doi.org/10.1145/3661167.3661212)).

Hosted via GitHub Pages at: `https://nguyentran0212.github.io/webpage-ease2024-ssctrust-metadata-management/`

## Layout

- `index.md` — page content (Markdown, processed by Jekyll)
- `_layouts/default.html` — base HTML template
- `assets/css/style.css` — single stylesheet
- `assets/pdf/main.pdf` — downloadable copy of the paper
- `assets/figures/*.png` — figures extracted from the paper
- `_config.yml` — site config (`baseurl` set to `/webpage-ease2024-ssctrust-metadata-management`)
- `Gemfile` — Jekyll dependency pinned to `~> 4.3`

## Local preview

Requires Ruby + Bundler.

```bash
bundle install
bundle exec jekyll serve --host 127.0.0.1 --port 4003
# → http://127.0.0.1:4003/webpage-ease2024-ssctrust-metadata-management/
```

## Editing content

The page is one Markdown file. Sections (in order):
Hero → TL;DR → Key numbers → Methodology → Domain model → SSC metadata life cycle → Architectural blueprint → What the evaluation reveals → Abstract → Cite this paper.

`baseurl` in `_config.yml` is set to `/webpage-ease2024-ssctrust-metadata-management`. If you ever move this to a custom domain or root, set `baseurl: ""` and `url: "https://yourdomain.com"`.
