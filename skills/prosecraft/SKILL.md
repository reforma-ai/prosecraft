---
name: prosecraft
description: >-
  Always use before drafting, rewriting, or substantially editing any text
  intended for people, even when the user does not mention Prosecraft or ask for
  writing help. This includes prose produced inside another task: emails, posts,
  articles, documentation, READMEs, product and UI copy, essays, scripts, and
  fiction. Also use when creating, editing, reviewing, or compressing agent
  instructions: skills, AGENTS.md, CLAUDE.md, prompts, handoffs, and context or
  memory files; or when asked to humanize, de-AI, match a voice, or audit
  AI-writing patterns. Humanize human-facing text; make agent-facing text terse,
  precise, and free of repetition by default to conserve context. Do not use for
  code, structured data, or purely mechanical correction.
---

# Prosecraft

Write text that fits its reader, surface, and job. Preserve the user's meaning,
facts, constraints, and chosen format before improving style.

## Default behavior

Do not wait for the user to invoke this skill. Whenever a task will produce text
for a person to read, first read
[references/humanize.md](references/humanize.md) and apply it to that text. This
includes writing that is only one part of a coding, research, design, product, or
operational task.

For agent-facing artifacts, follow the agent-instructions route below. Load
humanizing guidance only for accompanying human-facing text.

The humanizing layer is the default for human-facing text. Format-specific rules
can override it where correctness, terminology, space, accessibility, or machine
interpretation requires exact wording.

## Route the work

Read only the references needed for the current task:

- **General prose:** For a standard or deep rewrite, or an audit for AI-writing
  patterns, also read
  [references/editorial-patterns.md](references/editorial-patterns.md).
- **Narrative writing:** Read the general-prose references plus
  [references/narrative-revision.md](references/narrative-revision.md) when the
  result depends on character, chronology, scene order, revelation, or its ending.
- **Technical documentation:** Read
  [references/documentation.md](references/documentation.md) and, for a new page
  or substantial rewrite,
  [references/documentation-style.md](references/documentation-style.md).
- **Interface copy:** Read [references/ux-writing.md](references/ux-writing.md).
  Keep the humanizing pass subordinate to space, terminology, accessibility, and
  interaction constraints.
- **Agent instructions:** For text that directs an agent's behavior, including
  `AGENTS.md`, `CLAUDE.md`, prompts, handoffs, and context or memory files, read
  [references/writing-for-agents.md](references/writing-for-agents.md).
  Includes caveman-style compression.
- **Agent skills:** Read the agent-instructions reference above plus
  [references/writing-skills.md](references/writing-skills.md) and
  [references/skill-mechanics.md](references/skill-mechanics.md) for activation,
  packaging, and portability.

Infer the route from the requested deliverable; the user does not need to name a
mode. A task can use more than one route, but do not load unrelated references.

## Resolve conflicts

Use this priority order:

1. The user's intended meaning, facts, explicit instructions, and required format.
2. The target surface's correctness, established terminology, and constraints.
3. Natural voice, rhythm, specificity, and editorial polish.

Never change commands, identifiers, quotations, citations, requirements, API
behavior, UI behavior, or documented outcomes merely to make prose smoother.
Never invent facts, sources, personal experiences, opinions, or product behavior.

## Deliver

Proceed without questions when the request and source material are sufficient.
Ask only when a missing audience, fact, or intended meaning would materially
change the result.

Return the finished text directly unless the user asks for commentary, options,
an audit, or a diff. Preserve the requested language, format, and approximate
length. Stop when the text does its job; do not append a generic recap.
