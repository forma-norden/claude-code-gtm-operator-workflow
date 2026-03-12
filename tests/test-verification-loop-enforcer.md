# Test: verification-loop-enforcer

Load skill: `.claude/skills/verification-loop-enforcer.md`

## Prompt

```text
Read .claude/skills/verification-loop-enforcer.md

Task:
Generate a routed outbound CSV from input accounts.

Acceptance criteria:
- required columns: account_name, icp_score, route, owner, first_move
- no empty route values
- score must be integer from 0 to 100
- disqualified accounts cannot route to outbound
- final report must list pass/fail checks

Return verification process and final handoff contract.
```

## Must Pass Checklist

- [ ] Defines full verification loop: pre-check, build, validate, repair, finalize
- [ ] Includes structural and logic checks from acceptance criteria
- [ ] Includes stop condition for repeated critical failures
- [ ] Includes final handoff contract fields
- [ ] Includes explicit pass/fail reporting output

## Failure Indicators

- Returns output without a check sequence
- Does not enforce disqualifier logic checks
- Does not include pass/fail report in final response

