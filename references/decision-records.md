# Architecture Decision Records

Use this template for decisions with meaningful long-term consequences. Keep minor reversible choices lightweight.

\`\`\`markdown
# ADR-NNN: <Decision title>

- Status: Proposed | Accepted | Rejected | Superseded
- Date: YYYY-MM-DD

## Context
What problem are we solving? Which requirements, constraints, and invariants matter?

## Decision
What are we choosing, and what does the decision explicitly not imply?

## Alternatives considered
1. Option A — benefits, costs, risks
2. Option B — benefits, costs, risks

## Consequences
- Positive consequences
- Negative consequences and operational costs
- Migration or compatibility implications

## Assumptions and open questions
What remains uncertain? What evidence could change the decision?

## Follow-up
Tests, metrics, rollout steps, or documentation to update.
\`\`\`

## Decision quality checklist

- Is the decision traceable to a confirmed requirement?
- Were plausible alternatives considered?
- Are failure and recovery implications understood?
- Is the choice reversible? If so, how?
- Does the decision accidentally encode an assumption as a permanent constraint?
