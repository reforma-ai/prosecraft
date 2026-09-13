---
name: ux-writing
description: >-
  Reforma UI copy — buttons, labels, empty states, errors, toasts. Use when
  writing or editing user-visible strings in apps/front, apps/in, or
  packages/components. Not marketing pages, not AGENTS.md.
---

# UX writing (Reforma)

Words are UI. Same job as spacing: help someone finish the action.
Visual craft is `ui-polish`. This skill is the string.

Match the neighboring string in the same panel first. Don’t restyle the
product’s voice in passing.

## Voice

Four checks. Fail any one → rewrite.

|                | Means                        | Reforma                                               |
| -------------- | ---------------------------- | ----------------------------------------------------- |
| **Purposeful** | The string has a job         | Get them to the next action, or tell them what broke  |
| **Concise**    | Fewest words that still work | Editor: nouns and verbs. Auth: one extra clause is ok |
| **Clear**      | One reading                  | `Couldn't open App.tsx`, not `An error occurred`      |
| **Human**      | Spoken, not system           | `Save changes`, not `Persist` / `Submit` / `OK`       |

- **User’s words.** Layers, not “layer tree.” Preview, not “dev server.” Environment, not “sandbox” (Version Control keeps Git: Checkout, Uncommitted).
- **Sentence case.** `Save changes`, not `Save Changes`.
- **The control names the outcome.** Button `Publish` → toast `Published`. One verb through the flow.
- **Unicode ellipsis** `…` in pending copy (`Updating preview…`), not `...`.
- **Never show raw API codes** (`invalid_grant`, camelCase keys) to the user.

## Patterns

Each pattern is title + body when the surface has both. Title states the fact. Body is the next move. Don’t make the title do both.

### Button / menu / tooltip

Active imperative on the control: `Save changes`, `Delete project`, `Open in code`.
Tooltip adds the why or the shortcut; the label stays the action.
Icon-only: the accessible name **is** that label (`aria-label="Loading pages"`).

### Empty

Empty is an invitation, not a mood.

| Situation            | Title               | Body                              |
| -------------------- | ------------------- | --------------------------------- |
| Nothing exists yet   | `No pages yet`      | how to add one, if there is a way |
| Nothing selected     | `No selection`      | `Choose a layer to edit`          |
| Search / filter miss | `No matches`        | don’t pretend the list is broken  |
| Can’t proceed        | `Multiple selected` | `Choose one layer to continue`    |

`No … yet` = this list can grow. `No matches` = the query is the problem. Don’t swap them.

### Error

Interface voice, not a person. What failed + how to fix. No `Oops`. No blame.

| Kind           | Shape                        | Example we already use                                         |
| -------------- | ---------------------------- | -------------------------------------------------------------- |
| Field          | Immediate, under the control | `Email is required` / `Password must be at least 6 characters` |
| Toast / inline | Fact + object                | `Couldn't open App.tsx`                                        |
| Fallback       | Only when you have no fact   | `Something went wrong. Try again.`                             |

Prefer the fact you have (`No source location for this layer`) over the fallback. Auth forms may keep `Please …` — match that file, don’t “fix” it to editor-dense in passing.

Confirm: irreversible verb on the confirm button (`Delete project`), not `Yes` / `OK`. Cancel stays `Cancel`.

### Loading

Name the wait: `Saving…`, `Updating preview…`, `Loading pages`. Not `Please wait` / `Loading`.

## Before / after

| Weak                   | Better                               | Why                               |
| ---------------------- | ------------------------------------ | --------------------------------- |
| `An error occurred`    | `Couldn't open App.tsx`              | names the object                  |
| `No data`              | `No pages yet`                       | what this is + that it’s expected |
| `Submit`               | `Save changes`                       | outcome                           |
| `Click here`           | the action as the link text          | a11y + scan                       |
| `Invalid input`        | `Please enter a valid email address` | how to fix (auth register)        |
| `Remove` (destructive) | `Delete page`                        | permanent vs unbind               |
| `Webhook failed`       | what the person was doing            | no system names in chrome         |

## A11y (copy only)

- Icon-only and spinners need a text name (`aria-label`), same words as the visible verb.
- Don’t use color alone to carry “error” / “success” — the string must still read.
- Link/button text is the destination or action, never `here` / `this`.
- Errors that appear after submit must be reachable as text, not only a red border.

## Don’t

| Don’t                                                       | Do                                           |
| ----------------------------------------------------------- | -------------------------------------------- |
| System names in chrome (`webhook`, `AST`, `HMR`, `sandbox`) | Preview, environment, the thing they clicked |
| Clever / branded filler                                     | The action                                   |
| Pin copy in tests                                           | Assert structure (AGENTS.md). Copy changes.  |
| Rewrite a panel’s voice while fixing one string             | Two neighbors, then match                    |

## When touching strings

1. Read two neighboring strings in that surface — match register (editor dense vs auth `Please`).
2. Same word for the same action everywhere in the flow.
3. Surgical diff. Don’t “improve” unrelated copy.

Done when a teammate could find the control by the string alone, and an empty/error state still points at a next step.
