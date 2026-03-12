# remote-operator-setup

## Purpose

Set up Claude Code sessions for reliable local execution with optional remote
monitoring.

Use this skill before any long-running GTM workflow where operators need to
check progress away from their desk.

## Inputs Required

- project root path
- environment (`sandbox`, `staging`, `production`)
- remote monitoring required (`yes` or `no`)
- expected session duration in minutes

## Startup Modes

### Mode A: Local only

1. Open terminal in project root.
2. Run `claude`.
3. Confirm workspace trust and project context.
4. Load the next operational skill.

### Mode B: Local plus remote monitoring

Use when the session will run unattended or requires delayed approvals.

1. Open terminal in project root.
2. Start with `claude --remote` for a new remote-capable session.
3. If already in an active session, run `/remote`.
4. Store session URL in a secure operator note, never in shared chat channels.

## Session Reliability Rules

- One remote connection per session.
- Keep terminal process alive, closing terminal ends the session.
- Keep machine awake for long tasks.
- If network drops for an extended period, restart with `claude --remote`.

## Security Rules

- Treat remote session URLs and QR codes as secrets.
- Do not post session URLs in tickets or screenshots.
- Use dedicated operator accounts on shared machines.

## Output Format

Return:

1. selected startup mode and why
2. exact command sequence
3. reliability checks
4. failure and recovery path

## Fail Conditions

Stop and request correction if:

- project root is unknown
- environment is unspecified
- remote monitoring is required but machine uptime constraints are unknown

