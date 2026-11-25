# Bento — Paul Guttin

A one-page, Linktree/Bento.me style site presenting Paul Guttin, a freelance art director based in Caen, France. Built with plain HTML/CSS and a little JavaScript, with no framework or build step.

<p align="center">
  <img src="assets/mascotte.png" width="120" alt="Paul Guttin's mascot">
</p>

## Overview

The page follows the art direction of Paul's business card:

- **Palette**: blue `#2e4ea8`, black `#231f1e`, white `#ececec`
- **Typefaces**: Montserrat (headings) / BC Novatica CYR (body, with a system fallback)
- **Layout**: a minimalist single column with the intro and freelance status, a list of links (LinkedIn, Behance, GitHub, email), a scrolling "Work(ed) with" client strip and a map of Caen, over the business card's blue grid

## Project structure

```
Bento/
├── index.html        # Page markup and scripts
├── styles.css        # Layout, colours, typography
├── assets/
│   ├── logos/        # Client logos (SVG)
│   ├── mascotte.png  # Paul's mascot
│   └── favicon*      # Favicons and touch icon
└── README.md
```

## Run locally

There is nothing to install. Serve the folder statically, for example:

```bash
python3 -m http.server 8080
```

Then open [http://localhost:8080](http://localhost:8080).

## Customise

| Element | Where to edit |
|---|---|
| Name, role, avatar, freelance status | `.intro` in `index.html` |
| Links (LinkedIn, Behance, GitHub, email) | `.links` list in `index.html` |
| Clients and roles | `.work-list` in `index.html`, one `<li>` per client with its project link, logo in `assets/logos/` |
| Scrolling speed | `SPEED` in the marquee script in `index.html` |
| Map location and zoom | `CAEN_CASTLE` and `zoom` in the map script in `index.html` |
| Colours | the custom properties in `:root` at the top of `styles.css` |
| Fonts | the `@font-face` rule and `font-family` declarations in `styles.css` |

### About BC Novatica CYR

This is a commercial typeface that isn't available on Google Fonts. The CSS uses it if it is installed locally (`local('BC Novatica CYR')`), otherwise the page falls back to a system font. For a consistent result in every browser, add the font's `.woff2` files and point the `@font-face` rule in `styles.css` to them.

## Deploy

The site is fully static, so it can be published as is on GitHub Pages, Netlify, Vercel or any static host.

## Credits

- Map data: [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors
- Map style and tiles: [VersaTiles](https://versatiles.org) (Shortbread schema), rendered with [MapLibre GL JS](https://maplibre.org)
