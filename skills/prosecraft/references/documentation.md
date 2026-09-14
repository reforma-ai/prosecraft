# Documentation

Write the human page. Route UI strings through `ux-writing.md` and reusable agent
skills through `writing-skills.md`; always-on repository instructions follow the
target agent's conventions.

For a new page or substantial rewrite, read
[documentation-style.md](documentation-style.md). For a small,
mechanical correction, preserve the surrounding page's established style.

## Apply the humanizing layer

Use `humanize.md` alongside this reference. Documentation rules own the reader's task,
information architecture, technical accuracy, terminology, code, and document shape.
The humanizing layer owns natural rhythm, concrete language, restraint, and removal of
generic framing. If they conflict, correctness and the established documentation
contract win. Humanization must never alter commands, identifiers, requirements,
warnings, API behavior, or documented outcomes.

[Diátaxis](https://diataxis.fr/): one page, one job. A how-to that lectures, or
a reference that walks a tutorial, is the wrong page — split and link.

## Pick the job

Infer from the request. Name the pick in one line. Don't interview when the
goal is already in the prompt.

| Reader wants        | Quadrant        | Typical artifact          |
| ------------------- | --------------- | ------------------------- |
| to learn by doing   | **Tutorial**    | onboarding, first success |
| to get a thing done | **How-to**      | runbook, "how do I"       |
| to look up a fact   | **Reference**   | API, CLI, config, flags   |
| to understand why   | **Explanation** | architecture, design      |

"Document this" with no type: a procedure → how-to; a surface → reference; a
system → explanation.

README is a landing page, not a fifth quadrant. What + why, a short path to
first success, then links to the other three.

## Write

1. Read neighboring docs in the same tree for tone, terms, and what already
   exists. Link instead of rewriting.
2. Follow the target repository's existing documentation layout and nearest
   agent instructions. Put a package introduction in that package's `README.md`.
   Don't invent a new root docs tree or ADR structure without a project reason.
3. Ground claims in files, interfaces, and executable behavior you inspect. A
   path, command, option, or API you cite exists, or you label it as planned.
4. Write the page. Don't wait for outline approval unless the user asked for a
   structure, or the work is a multi-page set. Lead with the thing the reader
   came for; show commands, requests, and paths.
5. Validate the result in proportion to the change: run commands or examples
   when safe, check links and identifiers, and render the documentation when
   layout or site-specific syntax matters.
6. Apply the humanizing pass without changing technical semantics.

Done when a reader with that goal can finish without another page of the same
type.

## Shapes

Use the sections that serve the job. Cut the rest.

### Tutorial

Author owns success. One path, no choices, no theory.

- Start state and what "done" looks like
- Numbered steps; each one has something the reader can see
- Known-good end state in under five minutes when that's the brief

### How-to

Assumes they already know the product. A recipe.

- When to use this / the problem
- Prerequisites and access
- Steps to the outcome
- What to do if it fails (runbook: rollback + who to escalate)

### Reference

Describes the machine. Structure follows the product, not a task.

- Accurate, complete, same shape on every entry
- Request/response, flags, errors, limits — examples of the shape
- No "first install X" lesson; link to a tutorial or how-to

### Explanation

A discussion. Context, design, trade-offs, how pieces connect.
Not steps. Not an API list.

### README

- What this is and why it exists
- Quick start (tutorial fragment)
- Links: how-to, reference, contributing — don't inline them

## Split, then link

| Failure                             | Do                       |
| ----------------------------------- | ------------------------ |
| how-to opens with "what is X"       | link an explanation      |
| tutorial offers three install paths | pick one                 |
| reference walks a use case          | that's a how-to; link it |
| architecture has kubectl steps      | that's a runbook         |
