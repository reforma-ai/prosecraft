---
name: prosecraft
description: >-
  Use when creating, rewriting, or reviewing text: general human-facing prose,
  technical documentation, interface copy, or reusable agent skills. Also use
  when asked to humanize, de-AI, make writing less robotic or generic, match an
  existing voice, or audit a draft for AI-writing patterns. Route to the
  relevant writing rules and apply the humanizing editorial layer to prose for
  people. Do not use for code, structured data, or purely mechanical spelling
  and grammar correction.
---

# Prosecraft

Write text that fits its reader, surface, and job. Preserve the user's meaning,
facts, constraints, and chosen format before improving style.

## Route the work

Read only the references needed for the current task:

- **General prose:** Read [references/humanize.md](references/humanize.md). For a
  standard or deep rewrite, or an audit for AI-writing patterns, also read
  [references/editorial-patterns.md](references/editorial-patterns.md).
- **Narrative writing:** Read the general-prose references plus
  [references/narrative-revision.md](references/narrative-revision.md) when the
  result depends on character, chronology, scene order, revelation, or its ending.
- **Technical documentation:** Read
  [references/documentation.md](references/documentation.md) and, for a new page
  or substantial rewrite,
  [references/documentation-style.md](references/documentation-style.md). Also
  read [references/humanize.md](references/humanize.md) for the editorial pass.
- **Interface copy:** Read [references/ux-writing.md](references/ux-writing.md)
  and [references/humanize.md](references/humanize.md). Keep the humanizing pass
  subordinate to space, terminology, accessibility, and interaction constraints.
- **Agent skills:** Read
  [references/writing-skills.md](references/writing-skills.md) and
  [references/skill-mechanics.md](references/skill-mechanics.md). Do not
  humanize machine-facing instructions at the expense of precise activation,
  scope, or behavior. Apply the humanizing layer only to public-facing prose
  such as a README or marketplace description.

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
