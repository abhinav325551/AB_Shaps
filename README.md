# AB_Shaps – My Claude Code Setup

A public reference for how I've set up Claude Code as a product marketing toolkit — including custom PMM skills, a 3-layer memory architecture, and the plugins that power the workflow.

---

## What's in this repo

| Folder | What it contains |
|---|---|
| [`/skills`](./skills/) | 7 custom skills for product marketing work (messaging, competitive intel, GTM, pricing, etc.) |
| [`/memory`](./memory/) | 3-layer memory architecture: index → topic files → archive |
| [`/plugins`](./plugins/) | All installed Claude Code plugins with descriptions and use cases |
| [`/knowledge`](./knowledge/) | How I structure a knowledge folder for grounding Claude in product context |

---

## How it all fits together

```
Claude Code
├── Skills          → Tell Claude HOW to do specific PMM tasks
├── Memory          → Tell Claude WHO you are and WHAT context to carry across sessions
├── Plugins         → Extend Claude Code with tools, agents, hooks, and commands
└── Knowledge       → Feed Claude the raw product/market/customer data it needs
```

### The workflow

1. **Memory** loads first — Claude knows your role, product, brand voice, and current projects without you repeating yourself.
2. **Skills** handle the actual PMM work — positioning frameworks, battle cards, GTM plans, pricing strategy, customer research.
3. **Plugins** automate the meta-work — committing code, reviewing PRs, looping on tasks, managing hooks.
4. **Knowledge** grounds everything in real data — product docs, case studies, competitive materials.

---

## Skills overview

Seven packaged skills for core PMM work:

| Skill | Purpose |
|---|---|
| `product-marketing-context` | Creates and maintains the shared PMM context file — run this first |
| `messaging-positioning` | Positioning statements, value props, message houses, April Dunford framework |
| `competitive-intelligence` | Competitor analysis, battle cards, comparison pages, RFP support |
| `customer-research` | ICP, personas, JTBD, VoC, win/loss analysis |
| `go-to-market` | Launch plans, campaign briefs, timelines, cross-functional GTM |
| `pricing-packaging` | Pricing models, tier design, value metrics, pricing page guidance |
| `devrev` | DevRev MCP integration — manage tickets, issues, and opportunities via Claude |

→ Full details in [`/skills`](./skills/)

---

## Memory architecture

A redesigned 3-layer system (rebuilt April 1, 2026):

- **Layer 1 – Index** (`index.json`): Ultra-lean pointer file. 18 topic entries + 2 archive refs. Fast lookups without reading every file.
- **Layer 2 – Topic files**: Organized by type — `entities/`, `preferences/`, `environment/`. Bullet points over paragraphs. Large blobs split into focused files.
- **Layer 3 – Archive** (`archive/`): Raw source data from crawls/imports. Topic files are distilled from these.

Plus `me.md` (your profile) and `top-of-my-mind.md` (intentionally minimal) at the root.

→ Full details in [`/memory`](./memory/)

---

## Plugins installed

32 plugins from the official Claude marketplace, covering:
- Git workflow automation (`commit-commands`, `pr-review-toolkit`)
- Code quality (`code-review`, `code-simplifier`, `security-guidance`)
- Agent/skill development (`skill-creator`, `plugin-dev`, `agent-sdk-dev`)
- Loop and automation (`ralph-loop`, `hookify`)
- Language servers (TypeScript, Python, Go, Rust, Swift, Kotlin, etc.)

→ Full details in [`/plugins`](./plugins/)

---

## Getting started

### 1. Install the PMM skills

Copy the skill folders to your Claude skills directory:

```bash
cp -r skills/* ~/.claude/skills/
```

Or point your `CLAUDE.md` at this repo's skills folder.

### 2. Set up the memory structure

```bash
mkdir -p ~/.devrev-computer/memory/{entities,preferences,environment,archive}
# Then copy and customize the files in /memory
```

Replace all `[Your Name]`, `[YourCompany]`, etc. placeholders with your actual details.

### 3. Install plugins

From Claude Code, install via the plugin marketplace:

```
/plugins install commit-commands
/plugins install skill-creator
/plugins install ralph-loop
# etc.
```

### 4. Populate your knowledge folder

See [`/knowledge`](./knowledge/) for how to structure your product/market context files.

---

## Notes

- Skills use `.agents/product-marketing-context.md` as shared context — run `product-marketing-context` skill first before the others.
- Memory files use bullet points, not paragraphs — keeps files small and retrieval fast.
- The `devrev` skill requires the DevRev MCP server to be configured in your Claude settings.
