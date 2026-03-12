# gtm-strategy-foundation-prompt

## Purpose

Generate a practical 90-day GTM foundation plan from a minimum input set.

## Inputs Required

- company description (product, pricing, target customer)
- geography
- current traction (revenue, users, pipeline, or none)
- primary GTM motion (`outbound`, `inbound`, `PLG`, `hybrid`)

## Workflow Rules

- ask for missing required inputs before planning
- prioritize speed-to-revenue over TAM storytelling
- avoid generic definitions and theory explanations
- return concrete execution outputs only

## Execution Sequence

1. Confirm the four required inputs are complete.
2. Build market intelligence and competitive framing.
3. Produce segment prioritization and ICP recommendation.
4. Generate persona pain map and sourcing logic.
5. Produce targeting rules and messaging angles.
6. Draft sample LinkedIn and email outreach for top angles.
7. Produce a 90-day execution priority list with tradeoffs.

## Output Contract

Return exactly these sections:

1. market intelligence
2. market sizing and prioritization
3. ICP definition (top 1-2 segments only)
4. persona-level pain mapping
5. account and data sourcing strategy
6. targeting logic and filters
7. messaging angles (3-5)
8. sample outreach copy (LinkedIn + email)
9. GTM execution priorities (90-day view)

## Fail Conditions

Stop and request correction if:

- one or more required inputs are missing
- output includes generic concepts with no execution detail
- no explicit "ignore early" segment decision is provided

