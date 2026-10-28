# Japan Oil Market Dashboard

An interactive dashboard on how Japan got through the 2026 Strait of Hormuz closure, and what the switch from Middle East to US crude means for refinery output and hedging.

**Live site:** `https://<your-username>.github.io/<repo-name>/` (after GitHub Pages is turned on, see below)

## What's inside

| Tab | Question it answers |
|---|---|
| Overview | How hard was the supply shock, and how did stockpiles, prices and product trade respond? |
| 2026 vs 2021–25 range | Which series are outside their normal range, month by month? |
| Crude sourcing & refinery fit | Who replaced the Gulf barrels, and can Japanese refineries run them? |
| US crude: products & hedging | Did refinery output change, and what new price risks do refiners carry? |

Every chart reads from the files in `data/`, and each source is listed at the bottom of the page with a download link.

## Data

- **PAJ** (Petroleum Association of Japan): refinery production, sales, imports, exports, inventories, stockpile days.
- **METI**: crude imports by country, as reported by Arab News Japan, Reuters/Baird Maritime, Investing.com and Zhitong; 2025 baseline from Platts.
- **Ministry of Finance**: CIF crude import prices.
- **Operators' websites**: refinery unit capacities (Idemitsu, Taiyo Oil).
- **Crude yield model**: indicative product yields built from published TotalEnergies and ExxonMobil assays. These are estimates, labelled as such on the page.

Data runs through August 2026. Volumes convert at 6.2898 barrels per kilolitre.

## Turn on GitHub Pages

1. Push this folder to a public GitHub repository, with `index.html` at the root.
2. On GitHub, open **Settings → Pages**.
3. Under **Build and deployment**, set the source to **Deploy from a branch**, branch `main`, folder `/ (root)`, then save.
4. After a minute or so the site is live at the address shown on that page.

The empty `.nojekyll` file tells GitHub Pages to serve the files as they are.

## Update the data

1. Replace or edit the CSV or JSON in `data/`, keeping the same column names.
2. If you add a new source, add an entry for it in `data/datasets.json`.
3. Run `python tools/build_data.py` to regenerate `data.js`.
4. Commit and push. GitHub Pages republishes automatically.

To preview locally, open `index.html` in a browser. No server or build step is needed.

## Built with

Plain HTML and JavaScript with [d3 v7](https://d3js.org) (bundled in `vendor/`). No frameworks, no tracking, works offline.
