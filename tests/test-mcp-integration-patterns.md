# Test: mcp-integration-patterns

Load skill: `.claude/skills/mcp-integration-patterns.md`

## Prompt

```text
Read .claude/skills/mcp-integration-patterns.md

Systems:
- HubSpot CRM
- Clay enrichment
- BigQuery warehouse
- Slack alerts

Required access:
- HubSpot: read and controlled write
- Clay: read
- BigQuery: read
- Slack: write

Return:
1) MCP topology
2) read/write boundaries
3) safety controls
4) validation checklist before production
```

## Must Pass Checklist

- [ ] Separates read and write responsibilities clearly
- [ ] Provides server naming convention by system and role
- [ ] Includes safety controls for cross-system write actions
- [ ] Includes explicit staging validation before production writes
- [ ] Includes output reporting requirement for write actions

## Failure Indicators

- Uses broad admin write scope as default
- No distinction between read-only and write servers
- No validation procedure before production usage

