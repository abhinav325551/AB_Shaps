---
name: product-marketing-context
description: "Establishes foundational product marketing context that other skills reference. Use this when starting a new product, planning a launch, onboarding to a new role, or when other PMM skills need context. Triggers: 'set up product context,' 'new product,' 'create PMM context,' 'initialize product marketing,' 'I'm new to this product,' 'help me understand our product positioning.' This skill creates `.agents/product-marketing-context.md` that other skills read to avoid repetitive questioning."
metadata:
  version: 1.0.0
  skill_type: meta
---

# Product Marketing Context

You are setting up the foundational context for product marketing work. This context will be referenced by all other PMM skills (messaging, competitive intelligence, GTM planning, pricing, customer research) to avoid asking the same questions repeatedly.

Your goal is to create a comprehensive `.agents/product-marketing-context.md` file that captures the essential information about the product, market, customers, and strategy.

---

## What This Skill Does

This is a **meta-skill** that:
- Gathers core product marketing context once
- Creates a shared reference file for other skills
- Prevents repetitive questions across different PMM tasks
- Establishes a single source of truth for your product's positioning

**When to use this:**
- Starting work on a new product
- Onboarding to a new PMM role
- Before running other PMM skills for the first time
- When your product strategy has significantly changed

**What it creates:**
- `.agents/product-marketing-context.md` file with structured context
- A living document you can update as your product evolves

---

## Context Gathering Framework

Ask questions in this order, building a complete picture:

### 1. Product Fundamentals

**Ask:**
- What is the product name and how would you describe it in one sentence?
- What category does it belong to? (Existing category or new category you're creating?)
- What stage is the product at? (Pre-launch, early adoption, growth, mature)
- What type of product is it? (SaaS, platform, API, hardware, service)

**Capture:**
- Product name
- One-line description
- Category positioning
- Product stage
- Product type

### 2. Customer & Market

**Ask:**
- Who is your ideal customer? (Company size, industry, role)
- What are the key buyer personas? (Decision-maker, influencer, end user)
- What market are you competing in? (Market size, growth rate if known)
- Are you in an existing market or creating a new one?

**Capture:**
- Ideal customer profile (ICP)
- Primary buyer personas with roles and priorities
- Market definition
- Market maturity

### 3. Value Proposition & Differentiation

**Ask:**
- What problem does your product solve?
- What makes you different from alternatives? (Top 3 differentiators)
- What's your current positioning statement, if you have one?
- What outcomes can you prove? (Metrics, case study data)

**Capture:**
- Core problem solved
- Key differentiators
- Positioning statement (if exists)
- Proof points and metrics

### 4. Competitive Landscape

**Ask:**
- Who are your top 3 competitors?
- For each competitor, what's their main strength vs. you?
- What's the status quo alternative to your product? (Spreadsheets, manual process, legacy tool)
- How do customers currently solve this problem without you?

**Capture:**
- Primary competitors (3-5)
- Competitor strengths/weaknesses
- Status quo alternative
- Alternative solutions

### 5. Go-to-Market Motion

**Ask:**
- How do you sell? (Product-led, sales-led, hybrid)
- What's your typical deal size? (ACV or price range)
- How long is your sales cycle?
- What channels do you use to reach customers? (Inbound, outbound, partners, community)

**Capture:**
- Sales motion
- Average deal size
- Sales cycle length
- Primary channels

### 6. Messaging & Proof

**Ask:**
- What's your main tagline or positioning statement?
- What are your 3 core messages? (If established)
- What customer stories or case studies can you reference?
- What are the most common objections you hear?

**Capture:**
- Tagline/positioning
- Core messages (if established)
- Case study highlights
- Common objections

---

## Creating the Context File

### File Structure

Create `.agents/product-marketing-context.md` with this structure:

```markdown
# Product Marketing Context

Last updated: [Date]

---

## Product Fundamentals

**Product Name:** [Name]

**One-Line Description:** [Description]

**Category:** [Category positioning]

**Stage:** [Pre-launch / Early adoption / Growth / Mature]

**Type:** [SaaS / Platform / API / Hardware / Service]

---

## Ideal Customer Profile (ICP)

**Company Size:** [SMB / Mid-market / Enterprise / All]

**Industries:** [Primary industries]

**Geography:** [Primary markets]

**Company Characteristics:** [What makes them a great fit?]

---

## Buyer Personas

### [Persona 1 Name/Role]
- **Role:** [Title and department]
- **Goals:** [What they're trying to achieve]
- **Pains:** [Top 3 frustrations]
- **Priorities:** [What matters most in evaluation]

### [Persona 2 Name/Role]
- **Role:** [Title and department]
- **Goals:** [What they're trying to achieve]
- **Pains:** [Top 3 frustrations]
- **Priorities:** [What matters most in evaluation]

[Add additional personas as needed]

---

## Value Proposition

**Problem We Solve:** [Core problem statement]

**Our Solution:** [How we solve it]

**Key Differentiators:**
1. [Differentiator 1]
2. [Differentiator 2]
3. [Differentiator 3]

**Positioning Statement:**
[Full positioning statement if established, or note "TBD - use messaging-positioning skill"]

---

## Proof Points

**Metrics:**
- [Metric 1]: [Value]
- [Metric 2]: [Value]
- [Metric 3]: [Value]

**Case Study Highlights:**
- [Customer 1]: [Industry, use case, key result]
- [Customer 2]: [Industry, use case, key result]

---

## Competitive Landscape

**Primary Competitors:**

1. **[Competitor 1]**
   - Strength: [What they do well]
   - Weakness: [Where we win]

2. **[Competitor 2]**
   - Strength: [What they do well]
   - Weakness: [Where we win]

3. **[Competitor 3]**
   - Strength: [What they do well]
   - Weakness: [Where we win]

**Status Quo Alternative:** [What customers use today without any solution]

---

## Go-to-Market Motion

**Sales Model:** [Product-led / Sales-led / Hybrid]

**Average Deal Size:** [ACV or price range]

**Sales Cycle:** [Length in days/weeks]

**Primary Channels:**
- [Channel 1]
- [Channel 2]
- [Channel 3]

**Partner Ecosystem:** [Yes/No - brief description if yes]

---

## Current Messaging

**Tagline:** [Main positioning statement or tagline]

**Core Messages:**
1. [Message 1]
2. [Message 2]
3. [Message 3]

**Common Objections:**
- [Objection 1]
- [Objection 2]
- [Objection 3]

---

## Notes

[Any additional context, recent changes, upcoming initiatives, or important background]
```

---

## Workflow

1. **Check if context already exists**
   - Look for `.agents/product-marketing-context.md`
   - If it exists, ask: "I found existing context. Do you want to update it or create fresh?"

2. **Gather information systematically**
   - Go through each section above
   - Ask focused questions
   - Don't ask for information you can infer from previous answers

3. **Create the file**
   - Use the exact structure above
   - Fill in all sections with gathered information
   - Use "TBD" or "To be determined" for sections where information isn't available yet

4. **Confirm completion**
   - Show the user what was created
   - Note which sections are complete vs. TBD
   - Explain how other skills will use this context

5. **Remind about updates**
   - "This context should evolve as your product does. Update this file when your positioning changes, you enter new markets, or launch major features."

---

## How Other Skills Use This

When a user runs another PMM skill (messaging, competitive, GTM, pricing, customer research), that skill should:

1. **Check for context file**
   ```
   Look for `.agents/product-marketing-context.md`
   ```

2. **Read it if it exists**
   ```
   Read the entire context file before asking questions
   ```

3. **Only ask for what's missing**
   ```
   Don't re-ask questions already answered in the context file
   Focus on task-specific details only
   ```

4. **Suggest running this skill if context doesn't exist**
   ```
   "I don't see a product marketing context file. Would you like me to create one first? 
   It will save time by avoiding repetitive questions across different PMM tasks."
   ```

---

## Common Scenarios

### Scenario 1: Brand New Product
- Most sections will be "TBD" or tentative
- Focus on gathering what's known
- Mark strategic decisions as "To be determined with [skill name]"
- Example: "Positioning statement: TBD - use messaging-positioning skill to develop"

### Scenario 2: Established Product
- Most sections should be filled in
- Capture current state even if you plan to change it
- Note what's working vs. what needs refinement

### Scenario 3: New PMM Joining
- Context file becomes their onboarding doc
- Fill in what the company knows
- Identify gaps to address with other skills

### Scenario 4: Major Product Pivot
- Update existing context file
- Note what changed and why
- Keep old context in a "Previous" section for reference

---

## Questions to Skip

Don't ask these (they're handled by specialized skills):

- **Detailed messaging frameworks** → messaging-positioning skill
- **Full competitive battle cards** → competitive-intelligence skill
- **Launch plan details** → go-to-market skill
- **Pricing strategy** → pricing-packaging skill
- **Detailed persona research** → customer-research skill

Keep this focused on **foundational context** that all other skills need.

---

## Output Format

1. **Create the file**
   - Save to `.agents/product-marketing-context.md`
   - Use the exact markdown structure shown above

2. **Summary for user**
   - "✓ Created product marketing context file"
   - "✓ Captured [X] buyer personas, [Y] competitors, [Z] differentiators"
   - "→ Other PMM skills will now reference this context automatically"

3. **Next steps suggestion**
   - Based on what's TBD, suggest which skill to run next
   - Example: "Your positioning is TBD - want to run the messaging-positioning skill next?"

---

## Maintenance

**When to update this file:**
- New product launch or major feature release
- Shift in target customer or market
- New competitive threats emerge
- Messaging or positioning changes
- Pricing or packaging updates
- Quarterly strategy reviews

**How to update:**
- User can edit the file directly
- Or re-run this skill and select "Update existing context"
- Keep a changelog in the Notes section

---

## Success Criteria

This skill succeeds when:
- ✓ The context file is comprehensive enough that other skills don't need to re-ask basic questions
- ✓ A new PMM could read this file and understand the product, market, and strategy
- ✓ The file accurately reflects current strategy (not aspirational, not outdated)
- ✓ Other skills can build on this foundation without gaps

This skill fails when:
- ✗ Other skills still need to ask about basics (product category, ICP, competitors)
- ✗ Information is too vague to be actionable ("we target businesses")
- ✗ Context is outdated and no longer reflects reality
- ✗ File is missing critical sections entirely
