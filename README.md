# Prosecraft

Writing skills for AI agents that need to sound like someone meant what they wrote.

[![skills.sh](https://skills.sh/b/reforma-ai/prosecraft)](https://skills.sh/reforma-ai/prosecraft)

Generic "write better" prompts tend to blur different editorial jobs together. Prosecraft keeps them separate: humanizing a draft, structuring technical documentation, writing interface copy, and building skills for other agents.

## Skills

| Skill | What it does |
| --- | --- |
| [`humanize`](skills/humanize) | Edits human-facing prose for specificity, natural rhythm, and a recognizable voice without changing the meaning. It can also audit a draft without rewriting it. |
| [`documentation`](skills/documentation) | Writes READMEs, API references, runbooks, architecture pages, onboarding, tutorials, and how-to guides. It uses Diátaxis and public guidance from Microsoft, Google, Apple, GitLab, and Red Hat, then applies `humanize` as the editorial pass. |
| [`writing-skills`](skills/writing-skills) | Creates and reviews reusable agent skills: activation descriptions, instructions, references, scripts, packaging, and cross-agent portability. |
| [`ux-writing`](skills/ux-writing) | Writes interface copy for buttons, labels, menus, tooltips, empty states, errors, loading states, confirmations, and toasts. |

## Install

### Skills CLI

Choose the skills, target agents, and install scope interactively:

```bash
npx skills add reforma-ai/prosecraft
```

Install only `humanize`, globally and without prompts:

```bash
npx skills add reforma-ai/prosecraft --skill humanize --global --yes
```

Install the full collection globally:

```bash
npx skills add reforma-ai/prosecraft --skill '*' --global --yes
```

Use `--agent` to target one client:

```bash
npx skills add reforma-ai/prosecraft --skill humanize --global --agent codex --yes
```

See what the repository contains without installing anything:

```bash
npx skills add reforma-ai/prosecraft --list
```

Without `--global`, the CLI installs into the current project. With `--global`, the selected agent can use the skills across projects.

You can also ask an agent to handle the installation:

```text
Install the Prosecraft skills I choose globally from https://github.com/reforma-ai/prosecraft using the skills CLI.
```

### Agent plugin

The plugin installs all four skills as one package. Its root [`plugin.json`](plugin.json) follows the portable [Agent Plugins](https://agent-plugins.org/) format and loads the existing `skills/` directory directly.

Claude Code needs its own marketplace metadata:

```bash
claude plugin marketplace add reforma-ai/prosecraft
claude plugin install prosecraft@prosecraft
```

For Codex and ChatGPT, add the repository as a marketplace source:

```bash
codex plugin marketplace add reforma-ai/prosecraft
```

Then install **Prosecraft** from the Plugins Directory. If your Codex CLI does not recognize `codex plugin`, update Codex or use the skills CLI.

Cursor reads the portable root manifest without a separate Cursor-specific copy. Until Prosecraft is listed in a Cursor marketplace, install it with the skills CLI or load the repository as a local Agent Plugin.

No build step is required. The plugin manifests package the same files that the skills CLI installs.

## Use

Agents normally activate a skill from its description. `humanize` is deliberately broad: it should join any task that drafts or substantially rewrites text for people, while a more specific skill controls the format. For example, `documentation` structures a README and `humanize` keeps the prose from turning stiff or generic.

You can invoke skills directly too. A standalone installation uses names such as `/humanize`; Claude Code namespaces plugin skills as `/prosecraft:humanize`; Codex accepts `$humanize`.

```text
/humanize Rewrite this announcement without flattening my voice: ...

/documentation Write a how-to for rotating this API key.

/writing-skills Review this skill for weak activation, hidden assumptions, and unnecessary context.

/ux-writing Rewrite the empty and error states in this panel.
```

To inspect a draft without changing it:

```text
/humanize Audit this draft for recognizable AI-writing patterns without rewriting it: ...
```

## Repository layout

```text
plugin.json                         # portable Agent Plugin manifest
.agents/plugins/marketplace.json   # Codex and ChatGPT catalog
.claude-plugin/                    # Claude Code compatibility metadata
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

Each skill is self-contained and can be installed on its own. The manifests contain only packaging metadata, so there is no generated skill copy to keep in sync. For a plugin release, update the version in the portable and Claude manifests.

## License

Prosecraft is available under the [MIT License](LICENSE).

## Maintainer

Maintained by [@kachurun](https://github.com/kachurun).
