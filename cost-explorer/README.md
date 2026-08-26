# Cost Explorer — Datacor DataLab, Cost Analysis

Static demo dashboard. Reconstructed 2026-08-26 from a recovered JS bundle after the
original Netlify deploy and source files were lost.

## Deploy

Copy this folder into the `Demos` repository root, keeping the folder name:

```
Demos/
  index.html          <- existing Sales Analytics demo
  cost-explorer/      <- this folder
```

Published at `https://vnanev.github.io/Demos/cost-explorer/`.

No build step. GitHub Pages serves these files as-is.

## Run locally

Must be served over HTTP — `index-C4qMXC9I.js` is an ES module, so opening
`index.html` from the filesystem fails on CORS.

```
python -m http.server 8000
```

Then open <http://localhost:8000>.

## Routing

Hash-based, so deep links work on Pages with no rewrite rules:

```
#/dashboards/cost-analysis/overview
#/dashboards/cost-analysis/landed-cost
#/dashboards/cost-analysis/raw-material
#/dashboards/cost-analysis/cost-flow
#/dashboards/cost-analysis/fg-lot/L-260417
#/dashboards/cost-analysis/labor
```

## Files

| File | Notes |
| --- | --- |
| `index.html` | Rebuilt shell. The original was never cached; head reconstructed from a DOM capture. |
| `index-C4qMXC9I.js` | Recovered original bundle, with two internal-language strings edited out. |
| `index.css` | **Regenerated.** The original `index-CAi1DrZr.css` was not recoverable. |

### Regenerated stylesheet

Built with Tailwind v3 scanning the bundle for class names. Sources are in
`rebuild-src/` in the recovery folder (`tailwind.config.js`, `input.css`) — edit
those and re-run to change the theme:

```
npx tailwindcss -c tailwind.config.js -i input.css -o index.css --minify
```

Theme colors were sampled from a screenshot of the live site. Chart categories
(`--cat-1`..`--cat-7`), `--pos`, and the brand/surface/ink scales match the
original. Three values had no recoverable sample and are approximations:
`--cat-8`, `--neg`, and the `shadow-card` box-shadow.

## Data

Illustrative governed extract — not customer data. Landed components are
customer-configured (FR-23).
