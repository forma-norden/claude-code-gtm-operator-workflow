# CLAUDE.md - claude-code-gtm-operator-workflow

This repo defines an operator workflow for running Claude Code safely and
reliably in GTM engineering environments.

## Skills in This Repo

| Skill | When to use it |
|-------|---------------|
| `remote-operator-setup` | establishing stable local and remote session operation |
| `parallel-session-orchestrator` | running many active Claude sessions without lane conflicts |
| `safe-permissions-policy` | setting permission policy by environment and command risk |
| `mcp-integration-patterns` | connecting CRM, enrichment, and signal systems through MCP safely |
| `verification-loop-enforcer` | validating output quality before handoff to sales or RevOps |
| `gtm-strategy-foundation-prompt` | producing execution-ready GTM strategy outputs from minimum required inputs |

## Output Rule

Outputs must be executable. No strategy-only summaries.

Every operational output should include:

- command or action sequence
- expected output shape
- failure conditions
- correction path

## Testing Rule

Run tests in `tests/` before production use.
