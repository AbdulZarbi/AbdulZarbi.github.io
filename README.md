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
| `.github/workflows/publish.yml` | On every push to `main`, GitHub Actions runs `quarto render` and publishes to the `gh-pages` branch, which serves the site. |

The build output (`_site/`) is never committed; GitHub Actions makes it.

## Common edits

**Add a book:** open `books.yml`, copy the commented template at the top, paste it at the bottom, fill it in. For the cover, use `https://covers.openlibrary.org/b/isbn/<ISBN>-L.jpg` with the book's 13-digit ISBN.

**Add a portfolio project:** in `index.html`, find `PROJECT SLOT 3`, copy one of the project cards above it, and paste it there.

**Preview locally:** in the RStudio Terminal run `quarto preview`, or just open `index.html` in a browser.

## Publish

Commit and push to `main` (RStudio Git tab: Pull → tick files → Commit → Push). Check the **Actions** tab on GitHub; when the run is green (2–4 minutes) the site is live.
