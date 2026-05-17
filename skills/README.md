# Skills

Six custom Claude skills for product marketing work. These live in `.claude/skills` and share a common context file at `.agents/product-marketing-context.md`.

---

## Included skills

| Skill | File | Purpose |
|---|---|---|
| `product-marketing-context` | [`product-marketing-context/SKILL.md`](./product-marketing-context/SKILL.md) | Establishes shared product, market, customer, and GTM context — **run this first** |
| `messaging-positioning` | [`messaging-positioning/SKILL.md`](./messaging-positioning/SKILL.md) | Positioning statements, value props, message houses, April Dunford framework |
| `competitive-intelligence` | [`competitive-intelligence/SKILL.md`](./competitive-intelligence/SKILL.md) | Competitor research, battle cards, comparison pages, RFP support |
| `customer-research` | [`customer-research/SKILL.md`](./customer-research/SKILL.md) | ICP, personas, JTBD, VoC, win/loss analysis |
| `go-to-market` | [`go-to-market/SKILL.md`](./go-to-market/SKILL.md) | Launch plans, campaign briefs, timelines, cross-functional GTM |
| `pricing-packaging` | [`pricing-packaging/SKILL.md`](./pricing-packaging/SKILL.md) | Pricing models, packaging tiers, value metrics, pricing page guidance |

---

## How skills work

Each skill is a `SKILL.md` file with YAML frontmatter and a detailed instruction body:

```yaml
---
name: skill-name
description: "When to trigger this skill. Includes trigger phrases."
metadata:
  version: 1.0.0
---

# Skill instructions...
```

Claude reads the `description` to decide when to invoke a skill automatically. The body contains the full methodology, frameworks, and output templates.

---

## Recommended workflow order

```
1. product-marketing-context   → Build the shared foundation
2. messaging-positioning       → Define positioning & message house
3. customer-research           → Validate with ICP & persona work
4. competitive-intelligence    → Build battle cards & differentiation
5. pricing-packaging           → Set pricing strategy & tiers
6. go-to-market                → Turn everything into a launch plan
```

The sequence is flexible — each skill reads `.agents/product-marketing-context.md` first and only asks for information not already captured there.

---

## Installing

### Option A – Copy to Claude skills directory

```bash
cp -r skills/* ~/.claude/skills/
```

### Option B – Reference from your working directory

Add to your `CLAUDE.md`:

```markdown
Skills for this project live in `./skills/`. Use them for all PMM work.
```

### Option C – Claude.ai Projects

Upload the `SKILL.md` files directly to your Claude project as context files.

---

## Shared context file

All skills read `.agents/product-marketing-context.md` before asking questions. This file is created by the `product-marketing-context` skill and contains:

- Product description, category, and target market
- ICP and buyer personas
- Competitive landscape
- Current positioning and messaging
- GTM motion and key metrics

**Run `product-marketing-context` first.** Every other skill will be faster and more accurate because of it.
