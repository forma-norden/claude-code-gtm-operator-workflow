# parallel-session-orchestrator

## Purpose

Run multiple Claude Code sessions at the same time without mixing concerns,
overwriting context, or losing ownership of outputs.

## Inputs Required

- task list with priorities
- maximum concurrent sessions
- owner for each lane
- output folder per lane

## Lane Model

Assign each active session to one lane only:

1. `lane-research`
2. `lane-build`
3. `lane-qa`
4. `lane-docs`
5. `lane-release`

Never run two different lanes in one session.

## Orchestration Rules

1. One task per lane, one owner per lane.
2. Every lane writes to a dedicated folder.
3. Every lane has a completion contract before start.
4. QA lane cannot be skipped for production-bound outputs.

## Queue Control

When new tasks arrive:

1. score by urgency and dependency
2. assign to empty lane
3. if all lanes busy, queue by priority
4. do not preempt active lane unless blocker severity is critical

## Handoff Protocol

Each lane output must include:

- what was done
- artifacts created
- unresolved risks
- next action owner

## GTM-Specific Lane Templates

`lane-research`:

- signal collection
- account context summary

`lane-build`:

- workflow rules
- routing and scoring logic

`lane-qa`:

- test prompts
- pass or fail results

`lane-docs`:

- operator notes
- runbook updates

`lane-release`:

- changelog update
- publish readiness checklist

## Output Format

Return:

1. lane assignment table
2. execution order
3. handoff checkpoints
4. blocker escalation map

## Fail Conditions

Stop and request correction if:

- lane owners are missing
- output folders are missing
- QA lane is excluded for production output

