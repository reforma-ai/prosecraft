# Prosecraft

Writing guidance for AI agents that need to sound like someone meant what they wrote.

Prosecraft is one skill with several writing disciplines behind it. Tell it what you
need—a README, an error message, an agent skill, a rewrite—and it loads only the rules
for that kind of work. Human-facing text also gets an editorial pass for specificity,
natural rhythm, and a recognizable voice.

## What it handles

| Work | What Prosecraft pays attention to |
| --- | --- |
| General prose | Meaning, voice, rhythm, specificity, and recognizable AI-writing patterns |
| Technical documentation | Reader goals, information architecture, accuracy, examples, and established documentation standards |
| Interface copy | Actions, product terminology, brevity, accessibility, and consistency across a flow |
| Agent skills | Activation, behavioral instructions, progressive disclosure, packaging, and portability |
| Narrative writing | Character, causality, chronology, revelation, scene structure, and endings |

The humanizing rules are a shared editorial layer, not a separate command. They apply
by default to prose written for people. Machine-facing instructions keep precision and
unambiguous behavior ahead of stylistic polish.

## Install

### Skills CLI

Install Prosecraft interactively:

```bash
npx skills add reforma-ai/prosecraft
```

Install it globally without prompts:

```bash
npx skills add reforma-ai/prosecraft --skill prosecraft --global --yes
```

Target a specific client with `--agent`:

```bash
npx skills add reforma-ai/prosecraft --skill prosecraft --global --agent codex --yes
```

Inspect the repository without installing anything:

```bash
npx skills add reforma-ai/prosecraft --list
```

Without `--global`, the CLI installs into the current project. With `--global`, the
selected agent can use Prosecraft across projects.

You can also ask an agent to install it:

```text
Install Prosecraft globally from https://github.com/reforma-ai/prosecraft using the skills CLI.
```

### Agent plugin

The same repository is also an Agent Plugin. Its root [`plugin.json`](plugin.json)
follows the portable [Agent Plugins](https://agent-plugins.org/) format and loads the
skill from `skills/` directly.

Claude Code uses its own marketplace metadata:

```bash
claude plugin marketplace add reforma-ai/prosecraft
claude plugin install prosecraft@prosecraft
```

For Codex and ChatGPT, add the repository as a marketplace source:

```bash
codex plugin marketplace add reforma-ai/prosecraft
```

Then install **Prosecraft** from the Plugins Directory. If your Codex CLI does not
recognize `codex plugin`, update Codex or use the skills CLI.

Cursor reads the portable root manifest without a separate Cursor-specific copy. Until
Prosecraft is listed in a Cursor marketplace, install it with the skills CLI or load the
repository as a local Agent Plugin.

No build step is required. The plugin manifests package the same source files that the
skills CLI installs.

## Use

Agents can activate Prosecraft from an ordinary writing request; naming a mode is not
required. You can invoke it explicitly as `/prosecraft` after a standalone installation,
`/prosecraft:prosecraft` through the Claude Code plugin, or `$prosecraft` in Codex.

```text
/prosecraft Rewrite this announcement without flattening my voice: ...

/prosecraft Write a how-to for rotating this API key.

/prosecraft Rewrite the empty and error states in this panel.

/prosecraft Review this agent skill for weak activation and unnecessary context.
```

To inspect a draft without changing it:

```text
/prosecraft Audit this draft for recognizable AI-writing patterns without rewriting it: ...
```

## How it is organized

```text
plugin.json                         # portable Agent Plugin manifest
.agents/plugins/marketplace.json   # Codex and ChatGPT catalog
.claude-plugin/                    # Claude Code compatibility metadata
skills/
└── prosecraft/
    ├── SKILL.md                   # routing and shared priorities
    ├── agents/openai.yaml         # Codex display metadata
    └── references/                # writing rules loaded on demand
```

There is one installable skill. The detailed writing guides remain separate references,
so an interface-copy request does not load documentation or agent-skill guidance.

## Related project

Building software with agents, not just writing with them? [AgentFlow](https://github.com/reforma-ai/agentflow)
provides a practical loop for research, decisions, PR-sized planning, implementation,
and review.

## License

Prosecraft is available under the [MIT License](LICENSE).

## Maintainer

Maintained by [@kachurun](https://github.com/kachurun).
