# safe-permissions-policy

## Purpose

Set and enforce Claude Code permission behavior by environment and risk level.

## Inputs Required

- environment (`sandbox`, `staging`, `production`)
- operation type (`read`, `edit`, `execute`, `network`)
- command class (safe, sensitive, destructive)

## Permission Policy Matrix

| Environment | Allowed default mode | Sensitive commands | Destructive commands |
|---|---|---|---|
| sandbox | `acceptEdits` or `bypassPermissions` allowed | operator confirmation | blocked unless explicit sandbox test |
| staging | `default` or `acceptEdits` | operator confirmation | blocked |
| production | `default` or `plan` | manual approval only | blocked |

## Command Class Rules

Safe examples:

- formatting
- linting
- test execution
- read-only search and listing

Sensitive examples:

- schema migration
- external API writes
- deployment commands

Destructive examples:

- hard reset
- force delete
- credential overwrite

## Hard Bans

Do not run these in normal workflows:

- `git reset --hard`
- recursive delete without explicit file scope
- secrets rotation from local shell without approved runbook

## Configuration Rules

1. Store shared permission defaults in `.claude/settings.json`.
2. Check in safe defaults to git.
3. Keep environment-specific overrides outside committed defaults.

## Exception Procedure

If a destructive command is required:

1. log reason and rollback plan
2. obtain named approver
3. run in sandbox first
4. execute once with full command capture

## Output Format

Return:

1. environment policy decision
2. command classification
3. permission mode selection
4. approval requirement
5. rollback requirement

## Fail Conditions

Stop and request correction if:

- environment is unknown
- command classification is missing
- destructive command requested without rollback plan

