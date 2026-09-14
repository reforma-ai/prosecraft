# Writing skills

Create reusable instructions that reliably change an agent's behavior without consuming
more context or authority than the task requires.

For exact file-format, portability, invocation, and validation details, read
[skill-mechanics.md](skill-mechanics.md).

## Start from behavior

Before writing files, determine:

- the realistic requests that should activate the skill;
- the behavior that must differ from a capable agent's default;
- nearby requests that should not activate it;
- the user's intent, constraints, and authorization boundaries;
- whether the skill is public and portable or tied to a specific project, product, or tool.

Use three to five representative requests as design cases. Include at least one boundary
case. A skill without a clear behavioral difference is documentation, not a skill.

## Design discovery

The `name` and `description` are loaded before the body and determine whether the body is
ever read.

- Name the skill with a short, action-oriented identifier. Match the directory name.
- Describe both what the skill handles and when it should activate. Include the words users
  are likely to use, plus a boundary when a neighboring skill could be confused with it.
- Make automatic invocation the default. Use explicit-only invocation only when the user
  requests it or unsolicited activation would create recurring noise.
- Keep the description focused on discovery. Put workflow, rationale, and examples in the
  body or a referenced file.
- Avoid catch-all descriptions. Broad activation makes every unrelated task pay the context
  cost and increases instruction conflicts.

## Shape the context

Use progressive disclosure deliberately:

| Layer | Contains | Loaded |
| --- | --- | --- |
| Frontmatter | Name and activation description | Before activation |
| `SKILL.md` | Shared workflow, decisions, invariants, and routing | On activation |
| Resources | Branch-specific reference, deterministic scripts, output assets | Only when needed |

Keep instructions needed by every activation in `SKILL.md`. Move substantial detail behind
a direct link when only one branch needs it. State the condition for reading each reference.

Use scripts when deterministic execution is safer or the same transformation would otherwise
be rewritten repeatedly. Use assets only for material copied or adapted into the output. Do
not create empty folders or placeholder files.

## Write instructions that steer

- Lead with the outcome and the decisions the agent must make.
- Preserve user intent. A skill guides the requested work; it does not expand the task or
  grant permission for unrelated external actions.
- Prefer decision rules over rigid sequences when several approaches can succeed. Use fixed
  steps for fragile workflows, safety boundaries, or formats that must be exact.
- State true invariants directly. Phrase preferences as criteria, not universal laws.
- Give each ordered step an observable completion condition. Define when to stop retrying or
  polishing when unnecessary repetition is a realistic failure mode.
- Co-locate a concept's rule, rationale, and exception. Do not scatter duplicates across the
  body and references.
- Use positive targets that describe the wanted result. Keep prohibitions for real failure or
  safety boundaries.
- Remove generic advice a capable agent already follows. Keep domain knowledge, unwritten
  conventions, non-obvious tradeoffs, and failure-specific guidance.
- Make priorities explicit where instructions can conflict. The user's explicit request and
  the target project's applicable instructions remain authoritative.

For a public skill, replace internal paths, team names, private tools, and assumed repository
structure with discovery rules. Declare a real environment dependency instead of hiding it in
the body.

## Create or update

1. Inspect the target skill, its neighboring skills, applicable agent instructions, and the
   current format documentation. Done when existing intent and compatibility constraints are
   accounted for.
2. Write the activation cases and boundaries. Done when each representative request has an
   unambiguous activate-or-skip decision.
3. Choose the smallest useful file structure. Done when every file has a task-driven reason
   to exist and every conditional resource has a pointer.
4. Write or revise the instructions. Done when another agent can complete the target requests
   without depending on the author's unstated context.
5. Validate frontmatter, names, relative links, and package discovery. Run any new or changed
   scripts. Done when the skill installs or validates with the intended tooling.
6. Forward-test a realistic request when the skill is complex, risky, or behaviorally subtle.
   Inspect the decisions and produced artifacts, then make only evidence-backed corrections.

Do not initialize over an existing skill. Preserve unrelated metadata, resources, and user
changes during an update.

## Review an existing skill

Review the highest-impact failure first:

- **Discovery:** Does the description activate on the right requests and stay out of adjacent
  work?
- **Behavior:** Do the instructions change decisions, or merely restate good intentions?
- **Scope:** Does the skill preserve the user's task and authorization boundaries?
- **Context:** Is shared guidance concise, with conditional detail disclosed on demand?
- **Portability:** Are product-specific assumptions explicit and justified?
- **Integrity:** Do names, links, scripts, references, and packaged files resolve correctly?
- **Evidence:** Has meaningful behavior been tested instead of checking only headings or
  generated wording?

Prefer a narrow correction to accumulating a new universal rule for every observed failure.

## Done

A skill is ready when the intended clients discover it, representative requests activate it,
boundary requests do not, its resources are reachable, its instructions preserve user intent,
and validation exercises the behavior or artifact that matters.
