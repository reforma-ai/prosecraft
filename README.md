# Prosecraft

Practical writing skills for AI agents — humanize prose, draft documentation, and turn rough ideas into clear, useful text.

[![skills.sh](https://skills.sh/b/reforma-ai/prosecraft)](https://skills.sh/reforma-ai/prosecraft)

Prosecraft is a small collection of focused writing and editing skills. Each skill handles a different kind of text instead of applying one generic style to everything.

## Skills

| Skill | What it does |
| --- | --- |
| [`humanize`](skills/humanize) | A shared editorial layer for any human-facing draft or substantial rewrite. Keeps prose specific, natural, and recognizable without changing its meaning; also supports explicit humanization and audit-only requests. |
| [`documentation`](skills/documentation) | Writes and edits human-facing technical documentation: READMEs, API references, runbooks, architecture pages, onboarding, tutorials, and how-to guides. Combines Diátaxis and public guidance from Microsoft, Google, Apple, GitLab, and Red Hat with `humanize` as its editorial layer. |
| [`writing-skills`](skills/writing-skills) | Creates, reviews, and packages reusable agent skills with precise activation, progressive disclosure, portable instructions, and meaningful validation. |
| [`ux-writing`](skills/ux-writing) | Writes clear, concise interface copy for buttons, labels, menus, empty states, errors, loading states, confirmations, and toasts. |

## Install

### Ask your agent

Paste this into Codex, Claude Code, Cursor, or another coding agent:

```text
Install the Prosecraft skills I choose globally from https://github.com/reforma-ai/prosecraft using the skills CLI.
```

### Use the skills CLI

Choose skills and an installation target interactively:

```bash
npx skills add reforma-ai/prosecraft
```

Install one skill globally:

```bash
npx skills add reforma-ai/prosecraft --skill humanize --global --yes
```

Install the full collection globally:

```bash
npx skills add reforma-ai/prosecraft --skill '*' --global --yes
```

Target a particular agent with `--agent`, for example:

```bash
npx skills add reforma-ai/prosecraft --skill humanize --global --agent codex --yes
```

List the available skills without installing them:

```bash
npx skills add reforma-ai/prosecraft --list
```

Without `--global`, the CLI installs skills into the current project. With `--global`, they are available across projects for the selected agent.

## Use

`humanize` is designed to activate automatically whenever an agent drafts or substantially rewrites human-facing prose. It works alongside the more specific skills: for example, `documentation` decides the shape of a README while `humanize` keeps the prose natural and deliberate.

You can also invoke a skill by name. Clients with slash commands use names such as `/humanize`; Codex accepts explicit invocations such as `$humanize`.

```text
/humanize Rewrite this announcement without flattening my voice: ...

/documentation Write a how-to for rotating this API key.

/writing-skills Review this skill for weak activation, hidden assumptions, and unnecessary context.

/ux-writing Rewrite the empty and error states in this panel.
```

`humanize` also supports audit-only requests:

```text
/humanize Audit this draft for recognizable AI-writing patterns without rewriting it: ...
```

## Repository layout

```text
skills/
├── humanize/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/
├── documentation/
│   └── SKILL.md
├── writing-skills/
│   ├── SKILL.md
│   └── references/
└── ux-writing/
    └── SKILL.md
```

Every skill is self-contained and can be installed independently through the [skills CLI](https://skills.sh).

## License

Prosecraft is available under the [MIT License](LICENSE).

## Maintainer

Maintained by [@kachurun](https://github.com/kachurun).
