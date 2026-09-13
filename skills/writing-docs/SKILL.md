---
name: documentation
description: >-
  Use when writing or editing human-facing technical docs: README, API
  reference, runbook, architecture, onboarding, tutorial, or how-to.
  Not UI copy (ux-writing) and not agent docs (writing-for-agents).
---

# Documentation

Write the human page. UI strings are `ux-writing`. Skills and `AGENTS.md`
are `writing-for-agents`.

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
2. Product guide → `apps/docs` (Fumadocs — that folder's `AGENTS.md`). Package
   intro → that package's `README.md`. Don't add a repo-root `docs/` or ADR
   tree.
3. Ground claims in files you read. A path you cite exists, or you mark it
   planned.
4. Write the page. Don't wait for outline approval unless the user asked for a
   structure, or the work is a multi-page set.
5. Lead with the thing the reader came for. Show commands, requests, and paths.

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
