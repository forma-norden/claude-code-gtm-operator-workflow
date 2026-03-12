# Test: remote-operator-setup

Load skill: `.claude/skills/remote-operator-setup.md`

## Prompt

```text
Read .claude/skills/remote-operator-setup.md

Context:
- project root: ./signal-pipeline-core
- environment: staging
- remote monitoring required: yes
- expected duration: 180 minutes

Return:
1) startup mode
2) exact command sequence
3) reliability controls
4) failure recovery path
```

## Must Pass Checklist

- [ ] Identifies remote mode as required from input
- [ ] Includes explicit command sequence for startup
- [ ] Includes reliability controls for terminal, machine uptime, and network
- [ ] Includes security guidance for session URL handling
- [ ] Includes clear recovery path for dropped session

## Failure Indicators

- Returns generic productivity advice instead of setup sequence
- Omits recovery path for disconnected remote session
- Uses commands with no relation to remote session operation

