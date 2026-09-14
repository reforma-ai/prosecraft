# UX writing

Words are UI. Same job as spacing: help someone finish the action.
These rules cover the words and their text alternatives, not visual design.

Match the neighboring string in the same panel first. Don’t restyle the
product’s voice in passing.

## Voice

Four checks. Fail any one → rewrite.

|                | Means                        | In practice                                           |
| -------------- | ---------------------------- | ----------------------------------------------------- |
| **Purposeful** | The string has a job         | Get them to the next action, or tell them what broke  |
| **Concise**    | Fewest words that still work | Prefer concrete nouns and verbs                       |
| **Clear**      | One reading                  | `Couldn't open report`, not `An error occurred`       |
| **Human**      | Spoken, not system           | `Save changes`, not `Persist` / `Submit` / `OK`       |

- **User’s words.** Use the vocabulary established in the product. Prefer the name people see over internal service, schema, or implementation terms.
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

| Kind           | Shape                        | Example                                                        |
| -------------- | ---------------------------- | -------------------------------------------------------------- |
| Field          | Immediate, under the control | `Email is required` / `Password must be at least 6 characters` |
| Toast / inline | Fact + object                | `Couldn't open report`                                         |
| Fallback       | Only when you have no fact   | `Something went wrong. Try again.`                             |

Prefer the specific fact you have over the fallback. Match the surrounding product voice; sensitive flows may need a more polite or explanatory clause than a dense editor interface.

Confirm: irreversible verb on the confirm button (`Delete project`), not `Yes` / `OK`. Cancel stays `Cancel`.

### Loading

Name the wait: `Saving…`, `Updating preview…`, `Loading pages`. Not `Please wait` / `Loading`.

## Before / after

| Weak                   | Better                               | Why                               |
| ---------------------- | ------------------------------------ | --------------------------------- |
| `An error occurred`    | `Couldn't open report`               | names the object                  |
| `No data`              | `No projects yet`                    | what this is + that it’s expected |
| `Submit`               | `Save changes`                       | outcome                           |
| `Click here`           | the action as the link text          | a11y + scan                       |
| `Invalid input`        | `Please enter a valid email address` | gives the corrective action       |
| `Remove` (destructive) | `Delete page`                        | permanent vs unbind               |
| `Webhook failed`       | `Couldn't send message`              | names the user's action           |

## A11y (copy only)

- Icon-only and spinners need a text name (`aria-label`), same words as the visible verb.
- Don’t use color alone to carry “error” / “success” — the string must still read.
- Link/button text is the destination or action, never `here` / `this`.
- Errors that appear after submit must be reachable as text, not only a red border.

## Don’t

| Don’t                                                       | Do                                           |
| ----------------------------------------------------------- | -------------------------------------------- |
| Internal system names in product chrome         | The object or action the person recognizes       |
| Clever or branded filler                        | The action                                       |
| Pin incidental wording in tests                 | Assert behavior; pin copy only when contractual  |
| Rewrite a panel’s voice while fixing one string | Read two neighboring strings, then match          |

## When touching strings

1. Read two neighboring strings in that surface and match their register.
2. Same word for the same action everywhere in the flow.
3. Surgical diff. Don’t “improve” unrelated copy.

Done when a teammate could find the control by the string alone, and an empty/error state still points at a next step.
