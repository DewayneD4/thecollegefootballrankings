# Defoor Ratings — static site

Domain: **thecollegefootballrankings.com**

Home (`index.html`) shows the **current 2026** model Top 25.

Nav brand: **Defoor Ratings**.

## Deploy

Publish this folder to GitHub Pages / Netlify / S3 / Squarespace file host.
Zip handoff: `../output/cfb-rankings-site.zip`.

## Refresh current week

```bash
cd /workspace/cfb-rankings
.venv/bin/python update_2026_site.py
```
