# abdulzarbi.com

Personal portfolio site of Abdul Zarbi, Senior Data Analyst (Austin, Texas). Live at <https://abdulzarbi.com>.

## How the site is built

| File | What it is |
|---|---|
| `index.html` | The homepage: hand-written HTML with its own styles and scripts. Quarto copies it as is. |
| `books.qmd` + `books.yml` | The Bookshelf page. Quarto builds the book cards from `books.yml`. |
| `styles.css` | Styles for Quarto pages (Bookshelf), matched to the homepage colors and fonts. |
| `_quarto.yml` | Site settings: navbar, footer, which files get published. |
| `_includes/analytics.html` | Cookie banner + Google Analytics for Quarto pages (only runs after consent). |
| `images/` | Profile photo and favicon. |
| `.github/workflows/publish.yml` | On every push to `main`, GitHub Actions runs `quarto render` and publishes to the `gh-pages` branch, which serves the site. Only Quarto is installed: the site has no R code. |
| `AbdulZarbi.github.io.Rproj` | Opens the repo as an RStudio project (for the Git tab). Not part of the website. |

The build output (`_site/`) is never committed; GitHub Actions makes it.

## Common edits

**Add a book:** open `books.yml`, copy the commented template at the top, paste it at the bottom, fill it in. For the cover, use `https://covers.openlibrary.org/b/isbn/<ISBN>-L.jpg` with the book's 13-digit ISBN.

**Add a portfolio project:** in `index.html`, find `PROJECT SLOT 3`, copy one of the project cards above it, and paste it there. Put a ~1000px-wide JPG in `images/projects/` and point the card's `--photo` at it.

## Photo credits

All card photos are free to use with no attribution required (CC0 or public domain). Listed here so their source is on record.

| File | Source | License |
|---|---|---|
| `images/projects/texas-air-quality.jpg` | "Crane on the edge of the Houston Ship Channel cuts across skyline dimmed by smog", EPA DOCUMERICA, U.S. National Archives 550907 (Wikimedia Commons) | Public domain (U.S. government work) |
| `images/projects/austin-traffic.jpg` | "Highway Road", Negative Space, StockSnap | CC0 |
| `images/expertise/statistical-analysis.jpg` | "Google Analytics", Negative Space, StockSnap | CC0 |
| `images/expertise/dashboards.jpg` | "Business Working", Marc Chouinard, StockSnap | CC0 |
| `images/expertise/data-preparation.jpg` | "Code Technology", Markus Spiske, StockSnap | CC0 |
| `images/expertise/survey-design.jpg` | "Clipboard Desk", Design by Matt, StockSnap | CC0 |
| `images/expertise/research.jpg` | "Magnifying glass newspaper", rawpixel | CC0 |
| `images/expertise/stakeholders.jpg` | "Business People", Direct Media, StockSnap | CC0 |

Map: © OpenStreetMap contributors (shown on the map).

**Preview locally:** in the RStudio Terminal run `quarto preview`, or just open `index.html` in a browser.

## Publish

Commit and push to `main` (RStudio Git tab: Pull → tick files → Commit → Push). Check the **Actions** tab on GitHub; when the run is green (2–4 minutes) the site is live.
