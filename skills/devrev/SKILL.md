---
name: devrev
description: Interact with DevRev MCP to manage issues, tickets, incidents, and enhancements. Use when the user asks about DevRev objects, wants to create/update/list issues or tickets, or needs information from their DevRev workspace.
---

## DevRev MCP Skill

### Key Rules

1. **Always call `get_self` first** to get the current user's ID (`don:identity:...`) before any user-specific queries.
2. **Use an Agent** to call `list_issues`, `list_enhancements`, or any tool requiring array/number parameters — the MCP interface converts these to strings otherwise, causing errors. Pass the `owned_by`, `created_by`, `limit` etc. as proper native JSON types via the Agent subagent.
3. **Use `hybrid_search`** to resolve names → IDs before update/create operations.
4. **Always use `don:...` IDs** (not display IDs like ISS-123) in update/create operations.
5. **Use ISO 8601 dates**: `2026-04-04T23:59:59Z`

### Common Workflows

#### List issues assigned to me
1. Call `get_self` → extract user ID
2. Use Agent to call `list_issues` with `owned_by: [user_id]` and `limit: 20`

#### Find an issue/ticket by keyword
- Use `hybrid_search(namespace="issue", query="<keyword>", limit=10)`

#### Create a ticket
- Use `create_ticket(title, body, severity)`

#### Update an issue
1. `hybrid_search` to find the issue ID
2. `update_issue(id, <fields to update>)`

### Parameter Type Workaround
`list_issues` and similar tools require native array/number types. Always delegate these calls to an Agent subagent with explicit instructions to pass proper JSON types, not strings.
