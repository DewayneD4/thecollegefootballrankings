# CFB Rankings — static site

Publish-ready HTML for the FBS ranking model and 2016–2025 week-by-week AP comparisons.

## Contents

- `index.html` — current-season rankings board (latest year in `data/`)
- `method.html` — in-depth algorithm documentation
- `comparisons.html` — index of seasons
- `seasons/YYYY.html` — full weekly Model vs AP for that year
- `data/` — JSON/CSV exports (per week + summaries)
- `styles.css` — shared styles

## Host anywhere static

### GitHub Pages
1. Push this `site/` folder as the `gh-pages` branch root, or enable Pages on `/docs` after copying these files into `docs/`.
2. Or use Actions to deploy the `site/` directory.

### Netlify / Cloudflare Pages / Vercel
- Set publish directory to this folder (`site/`).
- No build command required.

### Amazon S3 + CloudFront
```bash
aws s3 sync . s3://YOUR_BUCKET/ --delete
# then invalidate CloudFront if used
```

### Local preview
```bash
cd site
python3 -m http.server 8080
# open http://localhost:8080
```

## Regenerating

From the project root (`/workspace/cfb-rankings`):

```bash
.venv/bin/python export_weekly_full.py   # full weekly Model vs AP → output/decade/weekly_full/
.venv/bin/python build_site.py           # rebuild site/ from exports + config.yaml
```

Config weights come from the repo’s current `config.yaml` (late-season tune).
