# Example: Incremental Architecture Session

This is an illustrative pattern, not a prescribed architecture.

## User goal

“I need a platform that runs user-configured agents for multiple business workflows.”

## First response: clarify scope

**Confirmed**
- The platform executes agent work.
- Multiple business workflows are involved.
- Users configure agents.

**Open question**
- Does a user-created agent represent a reusable configuration, a live runtime session, or both?

Ask one focused question before drawing the architecture.

## After clarification

Suppose the user confirms that an agent definition is reusable and each task selects a version of that definition.

**Working domain model**
- \`AgentDefinition\`: reusable configuration managed by a user.
- \`Task\`: a durable unit of work associated with a selected configuration.
- \`Execution\`: one attempt to perform work for a task.

**Still unresolved**
- Whether executions need to continue conversation context
- What state must survive an execution
- Whether multiple executions for the same task may overlap

Do not assume a database schema, queue, container strategy, or lock mechanism yet.

## Derive an invariant

If the user confirms that executions for one task must be serialized:

**Confirmed invariant**
- At most one execution for a given task may be active at a time.

**Logical responsibility**
- Some coordination boundary must enforce this invariant.

**Implementation options to compare later**
- Database-backed claim
- Lease-based coordination
- Partitioned single-owner processing

The options are not equivalent and should be compared against failure recovery, ownership changes, and operational constraints.

## Update discipline

If the user later clarifies that a task contains multiple conversational turns, update:
- The glossary and relationships
- The lifecycle of the task and turn
- The execution workflow
- The serialization invariant's scope
- The logical responsibility that enforces it
- Relevant diagrams and decision records

Do not merely patch one diagram while leaving conflicting prose elsewhere.
