# Architecture Workflow

## Stage 1 — Problem framing

Capture desired outcome, actors and entry points, scope and non-goals, known pain points, functional requirements, and non-functional constraints.

**Exit condition:** the goal and system boundary are understandable enough to identify the core domain concepts.

## Stage 2 — Domain model

For each concept, record:

| Field | Prompt |
|---|---|
| Name | What do we call it? |
| Meaning | What does it represent in the business? |
| Identity | How do we distinguish one instance from another? |
| Ownership | Which actor or logical boundary owns it? |
| Relationships | What does it reference or contain? |
| Lifetime | How long does it exist? |
| Mutability | What can change, and when? |
| Exclusions | What similar concept is it not? |

**Exit condition:** the team can explain key concepts and relationships without relying on implementation vocabulary.

## Stage 3 — Lifecycle and invariants

1. List states only when they have distinct semantic meaning.
2. Identify valid transitions and their triggers.
3. Clarify terminal, retryable, and recoverable outcomes.
4. Write invariants independently of their implementation.
5. Identify which logical responsibility guarantees each invariant.

**Exit condition:** important transitions and must-always-be-true rules are explicit.

## Stage 4 — Workflow modeling

For each primary workflow, record trigger, preconditions, steps and responsible actor/module, state changes, result visible to the caller, failure points, retry/cancellation/recovery behavior, and ordering/concurrency constraints.

Start with the happy path. Add exceptions based on risk and requirements, not completeness for its own sake.

## Stage 5 — Logical architecture

For each component, define responsibility, owned state, inputs/outputs, dependencies, invariants it enforces, failure boundary, and explicit non-responsibilities.

Validate that every important requirement maps to one or more responsibilities and ownership is not ambiguous.

## Stage 6 — Technology selection

Compare options against explicit requirements. Do not select a technology just because it is familiar or popular. Record assumptions and operational consequences.

## Review checklist

- [ ] Domain terms are defined consistently.
- [ ] Confirmed facts are separated from proposals.
- [ ] Lifecycle transitions are valid and understandable.
- [ ] Important invariants have a clear enforcement owner.
- [ ] Normal and failure paths are coherent.
- [ ] Concurrency and duplicate operations are considered where relevant.
- [ ] Recovery semantics are explicit.
- [ ] Logical responsibilities are distinct.
- [ ] Technology choices trace back to requirements.
- [ ] Diagrams agree with the written model.
