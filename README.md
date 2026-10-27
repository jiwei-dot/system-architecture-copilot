# System Architecture Copilot

A reusable skill for collaborative, incremental system architecture design.

It guides architecture work from business goals and domain semantics through lifecycle, invariants, workflows, logical responsibilities, and implementation trade-offs—without prematurely locking the design to specific technologies.

## Principles

- Clarify semantics before prescribing solutions.
- Separate confirmed facts, assumptions, proposals, and open questions.
- Model concepts and lifecycles before drawing detailed diagrams.
- Keep business meaning, logical architecture, and technical implementation distinct.
- Ask focused questions and iterate incrementally.
- Propagate model changes through workflows, responsibilities, constraints, and diagrams.

## Contents

- `SKILL.md` — main skill instructions
- `references/architecture-workflow.md` — staged workflow and review checklist
- `references/modeling-guide.md` — concepts, lifecycles, invariants, and terminology
- `references/decision-records.md` — architecture decision record template
- `examples/architecture-session.md` — illustrative example of incremental modeling

## Use

Load `SKILL.md` as the skill entry point in an environment that supports agent skills. The format uses YAML frontmatter with a `name` and `description`, followed by Markdown instructions.

## Scope

This skill is domain-agnostic. Any specific system—such as an agent execution platform—should be treated as a project example, not as a set of assumptions built into the skill.

## License

No license has been selected yet. Choose a license before encouraging reuse or contributions.
