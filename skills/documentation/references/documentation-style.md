# Documentation style

Read this reference for a new documentation page or a substantial rewrite. Project-specific
style, vocabulary, templates, and publishing constraints take precedence. Apply these rules
when the target project does not already make a different choice.

This guidance synthesizes the public documentation practices of Microsoft, Google, Apple,
GitLab, Red Hat, and Diátaxis. The source guides are linked at the end for detailed questions.

## Establish the reader contract

Before writing, determine privately:

- who needs the page and what they already know;
- the single job the page must help them complete;
- the starting state, required access, supported versions, and expected result;
- which terms, commands, interfaces, and claims must remain exact;
- whether the page is a tutorial, how-to, reference, explanation, or README landing page.

Write from the reader's point of view. Lead with the goal or answer, not the history of the
feature or the author's process. Add background only when it changes a decision or prevents
a mistake.

## Voice and language

- Address the reader as `you` when a person performs the action. Use an imperative verb for
  instructions. Name the system when the system performs the action.
- Prefer active voice when it makes the actor clear. Use passive voice when the actor is
  unknown, irrelevant, or less important than the result.
- Use familiar, precise words. Keep necessary technical terms and define unfamiliar ones at
  first use. Do not replace an established term merely for variety.
- Put conditions before the instruction: `If the deployment is running, stop it.`
- Distinguish obligation from possibility. Use an imperative or `must` for requirements,
  `can` for available choices, and `might` for possible outcomes. State recommendations as
  recommendations instead of hiding them behind ambiguous `should`.
- Keep paragraphs focused and front-load the distinguishing information. Vary sentence
  length for meaning, but untangle sentences that make the reader retain several conditions
  before reaching the action.
- Avoid claims that a task is easy, simple, obvious, or quick. Those words do not help the
  reader recover when their result differs.

## Structure for scanning

- Give the page one descriptive title and use headings that reveal the reader's path or the
  subject being described. Use sentence case unless the project specifies otherwise.
- Preserve a logical heading hierarchy and never skip a level merely for visual styling.
- Put the most useful information early. A reader scanning only headings and first sentences
  should still understand the page's shape.
- Use numbered lists for sequences, bullets for unordered sets, and tables only for genuine
  comparisons or repeated fields. Avoid putting a complex table inside a numbered procedure.
- Use descriptive link text that still makes sense out of context. Link to an existing source
  of truth instead of duplicating material that can drift.
- Use notes and warnings only when the information interrupts the normal flow for a reason.
  State the consequence and the action, not merely `Note` or `Important`.

## Procedures and tutorials

- State prerequisites and the observable end state before the steps when the reader needs
  them to decide whether to proceed.
- Choose one recommended path for the main procedure. Put materially different alternatives
  in separate sections, tabs, or pages.
- Use one numbered step per action. A short sequence in the same interface location can remain
  one step when splitting it would slow the reader down.
- Start each step with the context when needed, then an imperative verb. Keep optional steps
  visibly optional.
- Include the action that completes or applies the task. Do not stop immediately before
  **Save**, **Apply**, a restart, a migration, or another required completion action.
- After a consequential command or step, show the output, state change, or verification the
  reader should observe. Explain how to recover from common failures when the page is a
  runbook or the operation is risky.
- Refer to UI elements by their visible or accessible label. Prefer input-neutral verbs such
  as `select`, `open`, and `go to` unless the input method itself matters.

## Commands, code, and reference material

- Make examples minimal, plausible, and internally consistent. Use safe placeholder values;
  never expose real credentials, personal data, hosts, or account identifiers.
- Keep copyable commands executable. Clearly mark placeholders and optional arguments so the
  copied command cannot silently do the wrong thing.
- Separate commands from their output. Explain what a command changes before a destructive or
  difficult-to-reverse operation.
- Test commands and code samples when the environment permits it. If a sample is illustrative
  or untested, say so without implying verification.
- In reference pages, use the same field order and shape for every entry. Document inputs,
  outputs, defaults, errors, limits, side effects, and version constraints when they exist.
- Match identifiers, capitalization, flags, UI labels, and API names exactly. Do not translate
  or humanize literal machine-facing text.

## Accessibility and global use

- Do not rely on color, position, sound, animation, or an image as the only carrier of
  information. Provide equivalent text and useful alt text.
- Use meaningful headings and links. A screen-reader user scanning either list should know
  where a heading or link leads.
- Avoid directional references such as `above`, `on the right`, or `the green button` when a
  stable label or structural reference is available.
- Keep list items parallel and introduce tables before they appear. Prefer prose or a list
  when a table would be difficult to navigate.
- Expand uncommon abbreviations on first use. Avoid culture-specific jokes, metaphors, idioms,
  seasons, and ambiguous date formats when the audience is global.
- Use consistent terminology and ordinary sentence structure so the page remains clear to
  readers using translation tools or reading in a second language.

## Verification pass

Check the page as a reader, an operator, and a maintainer:

- **Reader:** Can the intended audience find the answer or finish the task without guessing?
- **Operator:** Do commands, prerequisites, expected results, failure modes, and rollback
  guidance match the real system?
- **Maintainer:** Are claims tied to durable sources, links valid, terminology consistent,
  and version-sensitive facts labeled?
- **Accessibility:** Does the page retain its meaning without images, color, sound, spatial
  cues, or mouse-specific instructions?
- **Editorial:** After applying `humanize`, is the prose direct and natural without changing
  a single technical fact or literal?

Fix substantive failures before polishing. Stop when the page completes its declared job;
do not append a generic recap.

## Source guides

- [Microsoft Writing Style Guide](https://learn.microsoft.com/en-us/style-guide/welcome/)
  — concise voice, global communication, terminology, procedures, and accessibility.
- [Microsoft: Writing step-by-step instructions](https://learn.microsoft.com/en-us/style-guide/procedures-instructions/writing-step-by-step-instructions)
  — scannable procedures, imperative steps, context, and completion actions.
- [Google developer documentation style guide](https://developers.google.com/style)
  — technical editorial guidance, reference hierarchy, voice, formatting, and terminology.
- [Google: Style guide highlights](https://developers.google.com/style/highlights)
  — second person, active voice, conditions before instructions, lists, links, and images.
- [Google: Write accessible documentation](https://developers.google.com/style/accessibility)
  — headings, links, alternatives to visual cues, tables, media, and UI navigation.
- [Apple Style Guide](https://support.apple.com/guide/applestyleguide/welcome/web)
  — consistent language for instructional materials, technical reference, training, and UI.
- [GitLab documentation style guide](https://docs.gitlab.com/development/documentation/styleguide/)
  — docs-as-code conventions, topic types, customer perspective, Markdown, and validation.
- [Red Hat supplementary style guide](https://redhat-documentation.github.io/supplementary-style-guide/)
  — product-documentation language, minimalism, conscious language, and formatting.
- [Diátaxis](https://diataxis.fr/) — separation of tutorials, how-to guides, reference, and
  explanation by reader need.
