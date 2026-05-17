# Archive

Raw, unprocessed source data from crawls or large document imports.

## What belongs here

- Raw web crawl output (e.g. scraped product pages, customer pages)
- Large imported documents before distillation
- Previous versions of topic files that were split or replaced

## What does NOT belong here

- Distilled topic files — those go in `entities/`, `preferences/`, or `environment/`
- Session notes or in-progress work
- Anything that should be actively referenced by Claude

## How to use

1. Drop raw imported data here first.
2. Distill it into focused topic files in the appropriate folder.
3. Add the raw file to the `archive` array in `index.json`.
4. Tombstone any old topic file that was replaced.

## Files in this archive

| File | Source | Date | Superseded by |
|---|---|---|---|
| `[your-product]-raw.md` | [your-product-url] crawl | [date] | `entities/product-platform.md`, `product-apps.md`, `product-positioning.md`, `product-pricing.md` |
| `[your-customers]-raw.md` | [your-product-url/customers] crawl | [date] | `entities/case-studies-*.md` (4 files) |

> The raw archive files are not included in this public repo. Add your own when you run your first product crawl.
