# Plugins

All installed plugins from the official Claude Code marketplace (`anthropics/claude-plugins-official`).

Install any plugin from Claude Code with:
```
/plugins install <plugin-name>
```

---

## Workflow & Git

### `commit-commands`
Streamlines the git commit → push → PR workflow. Adds `/commit`, `/push`, and `/commit-push-pr` slash commands so you never have to remember the full git incantation.

**Why I use it:** Cuts the friction on the commit loop. Especially useful when working through a sequence of small changes.

**Commands:** `/commit`, `/commit-push-pr`, `/clean_gone`

---

### `pr-review-toolkit`
Multi-agent PR review — specialized agents for comments, tests, error handling, type design, code quality, and simplification. Each agent scores with confidence ratings.

**Why I use it:** Catches things a single review pass misses. The confidence scoring means you know which suggestions to prioritize.

---

### `code-review`
Automated code review for pull requests using multiple specialized agents. Focused on correctness and quality.

**Why I use it:** Fast first-pass review before a human looks at the PR.

---

### `code-simplifier`
Agent that reviews changed code for reuse, quality, and efficiency, then fixes issues found. Preserves functionality while improving clarity.

**Why I use it:** Keeps code lean. Particularly useful after rapid prototyping when you want to clean up before committing.

---

## Agent & Skill Development

### `skill-creator`
Create new skills from scratch, improve existing skills, run evals, and benchmark performance with variance analysis.

**Why I use it:** The core tool for extending Claude's capabilities. Used every time I build a new PMM or sales skill.

**Commands:** Exposes `/skill-creator` and evaluation workflows.

---

### `plugin-dev`
Full plugin development toolkit — create agents, commands, hooks, and MCP integrations. Comprehensive guidance on plugin structure.

**Why I use it:** When building beyond single skills into full plugins with multiple components.

---

### `agent-sdk-dev`
Skills and templates for building Claude agents with the Agent SDK. Covers both TypeScript and Python implementations.

**Why I use it:** For building standalone agent applications that go beyond Claude Code sessions.

---

### `mcp-server-dev`
Guides for designing and building MCP servers — remote HTTP, MCPB, and local deployment models. Covers tool design, auth, and interactive MCP apps.

**Why I use it:** Reference when extending Claude Code with new data sources via MCP.

---

### `claude-code-setup`
Analyzes your codebase and recommends tailored Claude Code automations — hooks, skills, MCP servers, and subagents.

**Why I use it:** Useful when onboarding a new project to figure out which automations make sense.

---

## Automation & Loops

### `ralph-loop`
Runs Claude in a continuous loop until a task is complete — the "Ralph Wiggum technique." Supports interactive iterative development.

**Why I use it:** For long-running tasks that need multiple passes (e.g. building a full deck, running a pipeline analysis, iterating on a competitive doc).

**Commands:** `/ralph-loop`, `/cancel-ralph`

---

### `hookify`
Creates hooks by analyzing conversation patterns. Prevents unwanted behaviors through pre/post tool use hooks and stop hooks.

**Why I use it:** Automates guardrails without having to write hook scripts manually. Used to block dangerous commands and enforce review steps.

**Commands:** `/hookify`, `/hookify list`, `/hookify configure`

---

## Code Quality & Security

### `security-guidance`
A hook that warns about potential security issues when editing files — command injection, XSS, unsafe code patterns, and OWASP top 10.

**Why I use it:** Passive safety net. Fires automatically when editing, no action needed.

---

### `explanatory-output-style`
Adds educational insights about implementation choices and codebase patterns at the end of responses.

**Why I use it:** Good for onboarding sessions or when exploring an unfamiliar codebase — Claude explains the "why" behind what it's doing.

---

### `learning-output-style`
Interactive learning mode — Claude requests meaningful code contributions at key decision points instead of doing everything itself.

**Why I use it:** Useful when I want to stay in the loop on a technical task rather than having Claude run fully autonomously.

---

## Feature Development

### `feature-dev`
Full feature development workflow with three specialized agents: code explorer, code architect, and code reviewer.

**Why I use it:** Structured approach for non-trivial features. The explorer → architect → reviewer sequence catches issues early.

**Commands:** `/feature-dev`

---

### `frontend-design`
Frontend design skill for UI/UX implementation — HTML, CSS, and component-level design work.

**Why I use it:** Quick prototyping of web artifacts and dashboards.

---

### `playground`
Creates interactive HTML playgrounds — self-contained single-file explorers with visual controls and live preview.

**Why I use it:** Fast way to build shareable demos or interactive outputs from analysis work.

---

## Project Memory & Documentation

### `claude-md-management`
Tools to maintain and improve `CLAUDE.md` files — audit quality, capture session learnings, and keep project memory current.

**Why I use it:** Keeps the CLAUDE.md files from going stale. Runs after major sessions to capture what was learned.

---

## Language Servers (LSP)

Language server protocol plugins give Claude accurate, real-time language intelligence for editing code.

| Plugin | Language |
|---|---|
| `typescript-lsp` | TypeScript / JavaScript |
| `pyright-lsp` | Python |
| `gopls-lsp` | Go |
| `rust-analyzer-lsp` | Rust |
| `swift-lsp` | Swift |
| `kotlin-lsp` | Kotlin |
| `clangd-lsp` | C / C++ |
| `csharp-lsp` | C# |
| `jdtls-lsp` | Java |
| `php-lsp` | PHP |
| `ruby-lsp` | Ruby |
| `lua-lsp` | Lua |

**Why I use them:** LSPs give Claude type information, go-to-definition, and real-time error detection. Without them, Claude edits code more like a text editor than an IDE.

---

## Math & Domain-Specific

### `math-olympiad`
Specialized problem-solving skill for competition mathematics.

**Why I use it:** Occasionally useful for analytical and quantitative reasoning tasks outside typical PMM work.

---

## Dev & Example

### `example-plugin`
Reference implementation for plugin structure. Not used in production — kept as a template reference.

---

## Full plugin list

```
agent-sdk-dev        clangd-lsp           claude-code-setup
claude-md-management code-review          code-simplifier
commit-commands      csharp-lsp           example-plugin
explanatory-output-style  feature-dev     frontend-design
gopls-lsp            hookify              jdtls-lsp
kotlin-lsp           learning-output-style  lua-lsp
math-olympiad        mcp-server-dev       php-lsp
playground           plugin-dev           pr-review-toolkit
pyright-lsp          ralph-loop           ruby-lsp
rust-analyzer-lsp    security-guidance    skill-creator
swift-lsp            typescript-lsp
```
