# Test: parallel-session-orchestrator

Load skill: `.claude/skills/parallel-session-orchestrator.md`

## Prompt

```text
Read .claude/skills/parallel-session-orchestrator.md

Task queue:
1. Build ICP scoring logic update
2. Run regression checks on outbound routing
3. Draft handoff docs for RevOps
4. Prepare release checklist

Constraints:
- max concurrent sessions: 4
- output folders exist
- lane owners:
  - research: ana
  - build: joel
  - qa: celine
  - docs: maya

Return lane assignment, execution order, and handoff checkpoints.
```

## Must Pass Checklist

- [ ] Produces a lane assignment table, not only prose
- [ ] Keeps one task per lane and one owner per lane
- [ ] Preserves QA as mandatory before release
- [ ] Includes queue control for overflow tasks
- [ ] Includes handoff fields: what changed, risks, next owner

## Failure Indicators

- Mixes multiple lane responsibilities in one session
- Skips QA lane or treats it as optional
- No explicit handoff structure

