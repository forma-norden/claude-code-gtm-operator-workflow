# verification-loop-enforcer

## Purpose

Enforce deterministic verification before operational outputs are handed to sales,
marketing, or RevOps teams.

## Inputs Required

- target output type (`csv`, `markdown`, `yaml`, `json`, `code`)
- acceptance criteria
- data source constraints
- failure tolerance level

## Verification Loop

Use this sequence for every deliverable:

1. Pre-check: confirm input completeness and schema.
2. Build: generate output artifact.
3. Validate: run checks against acceptance criteria.
4. Repair: fix failures and rerun validation.
5. Finalize: publish only if all critical checks pass.

## Check Classes

Structural checks:

- required columns or keys present
- field naming standard respected
- no malformed records

Logic checks:

- scoring thresholds correctly applied
- routing rules correctly applied
- disqualifier logic correctly applied

Safety checks:

- no secrets in output
- no PII spill outside allowed columns
- no destructive instruction in automation outputs

## Handoff Contract

Every final output must include:

- artifact path
- pass and fail summary
- unresolved non-critical risks
- next owner and next action

## Mandatory Prompt Tail

Append this instruction to production tasks:

`Verify your own output against the acceptance criteria. List failed checks, fix them, and return only after all critical checks pass.`

## Output Format

Return:

1. verification report
2. corrected artifact location
3. pass and fail checklist
4. final handoff summary

## Fail Conditions

Stop and request correction if:

- acceptance criteria are missing
- critical checks fail after two repair loops
- output owner is unspecified

