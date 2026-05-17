# Memory Architecture

A 3-layer memory system for Claude Code, redesigned April 1, 2026. The goal: fast lookups, actionable topic files, and preserved raw data — without bloating Claude's context window.

---

## Structure

```
memory/
├── index.json                          # Layer 1 – ultra-lean pointer index
├── me.md                               # Your profile and work context
├── top-of-my-mind.md                   # Minimal session context (intentionally sparse)
├── entities/                           # Layer 2 – topic files: products, people, projects
│   ├── product-platform.md
│   ├── product-apps.md
│   ├── product-positioning.md
│   ├── product-pricing.md
│   ├── case-studies-headline-metrics.md
│   ├── case-studies-by-industry.md
│   ├── case-studies-quotes.md
│   ├── case-studies-migrations.md
│   ├── person-[manager].md
│   ├── project-[product].md
│   ├── project-pipeline-analysis.md
│   └── project-performance-review.md
├── preferences/                        # Layer 2 – topic files: working style, brand, tools
│   ├── working-style.md
│   ├── skills-folder.md
│   ├── brand-voice-guidelines.md
│   └── brand-visual-guidelines.md
├── environment/                        # Layer 2 – topic files: machine and tools
│   └── machine.md
└── archive/                            # Layer 3 – raw source data
    └── [your-product-raw-crawl].md     # populated when you run your first crawl
```

---

## The 3 layers

### Layer 1 – Index (`index.json`)

The first thing Claude scans. An ultra-lean pointer file with:
- `id` — short identifier
- `file` — path to the topic file
- `tags` — for filtering (e.g. `["product", "technical"]`)
- `summary` — under 150 characters, enough to decide relevance without opening the file

Tombstone entries point to superseded files so nothing breaks if something references an old path.

```json
{
  "id": "product-platform",
  "file": "entities/product-platform.md",
  "tags": ["product", "technical"],
  "summary": "[YourProduct] technical architecture – core platform, integrations, key features."
}
```

**Why an index?** With 18+ topic files, reading every file on each session start is wasteful. The index lets Claude decide which files are relevant before loading them.

---

### Layer 2 – Topic files

Organized into three folders:

| Folder | Contains |
|---|---|
| `entities/` | Products, people, projects, case studies — anything with a name |
| `preferences/` | Working style, brand guidelines, tools and skills setup |
| `environment/` | Machine setup, OS, dev tools |

**Conventions:**
- Bullet points, not paragraphs — faster to scan
- Each file covers one topic only
- Large knowledge blobs (e.g. full case study database, product portfolio) are split into 4 focused files for faster retrieval

**Example split:** A large product portfolio file can be split into focused sub-files:
- `product-platform.md` — technical architecture
- `product-apps.md` — apps and use cases
- `product-positioning.md` — messaging and positioning
- `product-pricing.md` — pricing tiers

The original file becomes a tombstone pointing to the new files.

---

### Layer 3 – Archive (`archive/`)

Raw, unprocessed source data — typically from web crawls or large document imports. These are the originals that the topic files were distilled from.

- Never edit archive files directly
- When you re-crawl or import fresh data, drop it in `archive/` first, then update the topic files
- Topic files that were replaced get tombstoned in `index.json` with a pointer to the archive

---

## Root files

### `me.md`
Your profile and work context. Contains:
- Name, role, company, location
- Background and responsibilities
- Work style summary

Replace all `[placeholder]` values with your own details before use.

### `top-of-my-mind.md`
Intentionally minimal. Does **not** contain session-specific context, in-progress tasks, or temporary notes. Last restructure date only.

The discipline here is important: keeping this file lean means it doesn't pollute Claude's context with stale session data.

---

## Design principles

1. **Index first** — Claude should never need to open every file to find what's relevant.
2. **Bullet points over paragraphs** — Memory files are for lookup, not reading.
3. **One topic per file** — Makes individual files replaceable without affecting others.
4. **Split large blobs** — A 400-line file is 4 useless files for most queries. Split by sub-topic.
5. **Archive is immutable** — Topic files are distilled from archive. Archive is never edited.
6. **Tombstone, don't delete** — When replacing a file, mark it as superseded in the index so old references don't break silently.

---

## How to adapt this for your setup

1. Replace `me.md` with your own profile.
2. Replace the `entities/product-*.md` and `entities/case-studies-*.md` files with your product's equivalent.
3. Replace `preferences/brand-*.md` with your company's brand guidelines.
4. Update `preferences/skills-folder.md` with your skills directory path.
5. Update `environment/machine.md` with your machine specs.
6. Re-index everything in `index.json`.

The `archive/` folder ships empty — populate it when you do your first product/content crawl.
