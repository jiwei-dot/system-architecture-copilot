# Modeling Guide

## Distinguish three levels

### Domain meaning
Describe what something means to a user or business process. Avoid choosing storage tables, classes, or infrastructure names too early.

### Logical responsibility
Describe which part of the system owns a decision, state transition, policy, or interaction. A logical responsibility may later map to a service, module, process, or library.

### Technical realization
Describe the concrete mechanism used to fulfill a logical responsibility: database, queue, distributed coordination, container, protocol, runtime, and so on.

A single concept can exist at all three levels, but the names and responsibilities should not be conflated.

## Questions for concepts

- Is this a business concept, a workflow event, a logical responsibility, or an implementation artifact?
- Does it have its own identity and lifecycle?
- Is it persistent, ephemeral, or reconstructible?
- Can it exist independently?
- What owns its state?
- What changes it?
- What happens if a process stops while it exists?
- What must remain true when two actors act concurrently?

## Lifecycles

A state should represent a meaningful condition, not merely a function call or internal implementation step.

For each transition, record source state, trigger, preconditions, resulting state, side effects, failure behavior, and whether the transition can be retried safely.

Avoid inventing detailed state machines before there is evidence that the distinctions matter.

## Invariants

An invariant is a rule that must remain true across valid system behavior. Examples include:
- At most one active operation may mutate a particular logical session.
- A configuration revision selected for an operation remains stable for that operation.
- A completed operation cannot silently return to a running state.

These are examples only, not defaults. Confirm the actual requirement with the user.

For each invariant, identify why it exists, its scope, what violates it, which logical boundary guarantees it, and how violation is detected or recovered from.

## Concurrency vocabulary

Be precise about:
- Parallelism: operations run at the same time
- Ordering: one operation must happen before another
- Mutual exclusion: conflicting operations must not overlap
- Idempotency: repeating an operation has a defined safe effect
- Durability: state survives specified failure conditions
- Isolation: one operation's effects are constrained from others
- Recovery: the system can re-establish an acceptable state after failure

Do not use these terms as interchangeable claims.

## Uncertainty labels

Use:
- **Confirmed:** explicitly stated or validated
- **Assumption:** temporarily treated as true to continue reasoning
- **Proposal:** a possible design, open to revision
- **Open question:** a missing decision that could change the model
- **Rejected:** considered and intentionally not selected

Update these labels when new information arrives.
