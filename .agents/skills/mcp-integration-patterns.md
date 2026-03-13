# mcp-integration-patterns

## Purpose

Connect Claude Code to GTM systems through MCP with strict boundaries for read,
write, and auditability.

## Inputs Required

- MCP server list
- data systems in scope (CRM, enrichment, warehouse, messaging)
- access level needed per system (`read`, `write`, `admin`)
- output artifact path

## Integration Principles

1. Start read-only, escalate to write only when needed.
2. Separate operational servers from experimental servers.
3. Use explicit server names that map to one system each.
4. Log all write actions in an execution report.

## Server Role Model

`mcp-crm-read`:

- account and contact retrieval
- pipeline status reads

`mcp-crm-write`:

- controlled updates to route fields
- controlled task creation

`mcp-enrichment-read`:

- profile and firmographic retrieval

`mcp-warehouse-read`:

- performance query execution

`mcp-messaging-write`:

- outbound message scheduling actions

## Safety Controls

- No broad write privileges on first connection.
- No cross-system write chains without explicit operator approval.
- No secret exposure in output reports.

## Validation Checklist

Before production use:

1. validate every server can connect
2. validate read queries on sample entities
3. validate one controlled write in staging
4. verify rollback path for write failure
5. capture all checks in run log

## Output Format

Return:

1. MCP topology table
2. read and write boundary map
3. validation results
4. approved actions and blocked actions

## Fail Conditions

Stop and request correction if:

- server ownership is unknown
- write scope is requested without rollback path
- credentials are present in plain text artifacts

