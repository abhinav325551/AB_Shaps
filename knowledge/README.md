# Knowledge Folder

This folder holds product, market, and customer reference materials that ground Claude in real context before doing PMM work.

---

## What goes here

| Type | Examples |
|---|---|
| Product documentation | Architecture docs, feature overviews, release notes |
| Positioning & messaging | Brand decks, messaging frameworks, pitch materials |
| Competitive intelligence | Battle cards, competitive analysis docs, comparison guides |
| Customer materials | Case studies, testimonials, use-case playbooks |
| Sales enablement | Field guides, talk tracks, objection handling docs |
| Pricing materials | Pricing sheets, packaging tiers, value metric explainers |

---

## My knowledge folder structure

```
knowledge/
├── product/
│   ├── [product]-platform-overview.pdf
│   ├── [product]-apps-and-usecases.pdf
│   └── [product]-agent-studio.pdf
├── positioning/
│   ├── brand-and-product-positioning.pdf
│   └── [product]-narrative-deck.pdf
├── competitive/
│   ├── competitive-analysis-[product]-vs-[competitor].pdf
│   └── battlecard-[competitor].pdf
├── customers/
│   ├── case-study-[customer-a].pdf
│   ├── case-study-[customer-b].pdf
│   └── customer-quotes-compiled.pdf
├── sales-enablement/
│   ├── field-conversation-guide.pdf
│   ├── field-conversation-guide-sales.pdf
│   └── objection-handling.pdf
└── pricing/
    └── pricing-and-packaging.pdf
```

---

## How to use it with Claude

### Option A – Claude Code (local files)

Reference files directly in your `CLAUDE.md`:

```markdown
## Knowledge base
Product and customer reference materials are in `./knowledge/`.
Read the relevant files before doing positioning, competitive, or GTM work.
```

Or ask Claude to read a specific file at the start of a task:

```
Before we start, read knowledge/competitive/battlecard-zendesk.pdf
```

### Option B – Claude.ai Projects

Upload the PDFs directly to your Claude project. They'll be available in every conversation in that project.

### Option C – Memory distillation (recommended for frequently-used content)

For content you reference constantly (product architecture, key metrics, top quotes), distill it into a memory topic file rather than re-reading the PDF every session.

Example: The `entities/case-studies-headline-metrics.md` memory file is a distilled version of 30 case study PDFs — 40 bullet points instead of 300 pages.

---

## The distillation workflow

```
1. Drop raw document into knowledge/ (or archive/ if it's very large)
2. Ask Claude to distill it: "Read this PDF and create a memory file in entities/"
3. The memory file becomes the day-to-day reference
4. The original PDF stays as the source of truth
```

This keeps Claude's context window lean while preserving access to full detail when needed.

---

## What's not in this public repo

The actual knowledge files are company-specific and not included here. This folder documents the structure and workflow.

To populate your own knowledge folder:
1. Gather your product docs, competitive materials, and customer content
2. Organize into the folder structure above
3. Distill high-frequency content into memory topic files
4. Reference the raw files for deep dives
