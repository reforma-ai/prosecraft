# Writing for agents

Default: the shortest instructions that preserve the intended behavior. Apply to
agent rules, prompts, handoffs, and memory without waiting for a brevity request.
Writing about agents for people follows the human-facing routes.

## Spend context on decisions

- State actions directly. Cut introductions, acknowledgments, recaps, filler,
  repeated rules, and explanations the receiving agent can infer.
- Keep only information that changes an action, decision, or completion check.
  Include rationale only when it prevents a likely mistake.
- Give each rule one authoritative home. Link to it instead of restating it.
  Omit context already available to the receiver; include what a new agent lacks.
- Use compact bullets or fragments where clear. Preserve words that express
  conditions, order, negation, uncertainty, ownership, or exceptions.
- Use stable terms. Avoid invented abbreviations, forced shorthand, and fixed
  word limits that remove needed meaning.

## Preserve behavior

Keep the applicable scope, required inputs, actions, permissions, exceptions, and
completion criteria. Include only what the task needs; no mandatory template.
Keep required distinct from preferred, verified from assumed, and preparation
from publication. Resolve conflicts from authoritative context or flag them.

Put each condition beside its action and exception. Number steps only when order
matters. Specify observable completion and a stopping condition for retry loops.
Prefer the wanted action; retain explicit prohibitions for necessary boundaries.

During prose compression, preserve code, commands, identifiers, paths, URLs,
literal errors, schemas, numbers, and units exactly unless substantive revision
is requested. Preserve meaningful nesting and order. Report token savings only
when measured with a named tokenizer.

## Place and load selectively

- Repository instructions: durable project conventions.
- Prompts and handoffs: task objective and current state.
- Skills and references: reusable conditional procedures.
- Memory: observations distinguished from standing rules.

Keep shared essentials inline. Link conditional detail with its read trigger and
purpose: "For migrations, read `docs/migrations.md` for rollback requirements."
Check that the receiver can access the target. Prefer current configuration or
tool help over duplicating easily discovered facts.

For skill design, read [writing-skills.md](writing-skills.md); for packaging or
validation, read [skill-mechanics.md](skill-mechanics.md).

## Handoffs

Include the objective, artifact locations, relevant state, remaining action, and
completion check. Add assumptions, failed attempts, or existing authorization
only when they affect continuation. Preserve permission boundaries. Replace
"the earlier fix" with its file, symbol, or finding. Omit conversation history
that does not affect the next decision.

## Final pass

Delete each sentence whose removal leaves the agent's decisions unchanged.
Check the normal path and material exceptions against the original intent.
For handoffs, assume no prior conversation. Return the artifact without a
preamble or change recap unless requested.

Keep: "Delete export only after backup restoration succeeds. If it fails, stop."
Reject: "Check backup; delete export." It loses the success gate and failure path.

## Sources

- [Writing for Agents](https://github.com/mattpocock/skills/blob/main/skills/productivity/writing-for-agents/SKILL.md)
- [Caveman](https://github.com/Karnonson/caveman/blob/main/skills/caveman/SKILL.md)
- [Caveman Compress](https://github.com/Karnonson/caveman/blob/main/skills/caveman-compress/SKILL.md)
