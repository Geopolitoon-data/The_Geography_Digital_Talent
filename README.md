# The Geography of Digital Talent

An interactive scrollytelling data story on where the world's digital talent actually
concentrates — read as **concentration, not raw counts**. Built for Emerging ·
Global Digital Leaders 2026.

The piece walks through the dataset, an interactive world map of every country's
specialisations, and a look at where young talent concentrates and what it does.

## View it

This is a static site with **no build step**. It loads two JSON files at runtime, so it
must be served over HTTP (opening `index.html` directly from disk will not load the map).

**Locally**

```bash
python -m http.server 8000
# then open http://localhost:8000
```

**On GitHub Pages**

Settings → Pages → *Deploy from a branch* → `main` / `root`. Your site appears at
`https://<user>.github.io/<repo>/`.

## What's inside

| Path | Purpose |
|------|---------|
| `index.html` | The entire article — HTML, CSS and JS in one file. |
| `cmap.json` | Per-country top-3 job concentrations (location quotients), keyed by ISO numeric code. |
| `countries-110m.json` | World topology (world-atlas / Natural Earth, 110m). |

External libraries (D3, TopoJSON) and the Montserrat font load from public CDNs, so no
dependencies are vendored.

## How to read the numbers

- **194,482** digital-leader profiles across **160** countries and **9** world regions.
- Collection volumes are **deliberate quotas** set from the National Readiness Index
  (which scores each country's digital readiness) — so a country's headcount reflects the
  quota design, not the size of its talent.
- Because of that, we **never rank places by profile count**. Every geographic figure is a
  **concentration** — a job's share *inside* a place versus the world average (a location
  quotient; `1.5×` = 50% more concentrated than average).
- Young-talent figures are shares *within* each region, never raw counts.

## Built with

Vanilla HTML / CSS / JavaScript · [D3](https://d3js.org/) + [TopoJSON](https://github.com/topojson/topojson) ·
Montserrat · the Emerging brand palette. Scroll interactions use `IntersectionObserver`;
the map is a D3 `geoNaturalEarth1` choropleth.

## Credits

© Emerging 2026. Underlying data: DL2026 / GEURS 2026. Country topology:
[world-atlas](https://github.com/topojson/world-atlas) (Natural Earth, public domain).
