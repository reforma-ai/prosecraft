# Skill mechanics

Read this reference when creating or changing skill files, packaging a public skill, choosing
invocation behavior, or validating compatibility.

## Portable format

A skill is a directory containing `SKILL.md`. The file starts with YAML frontmatter and
continues with Markdown instructions.

```text
skill-name/
├── SKILL.md
├── references/   # optional, read on demand
├── scripts/      # optional, executed when needed
├── assets/       # optional, copied or adapted into output
└── agents/       # optional, client-specific metadata
```

The Agent Skills specification requires:

- `name`: 1–64 lowercase letters, digits, and hyphens; no leading, trailing, or consecutive
  hyphens; match the parent directory name;
- `description`: 1–1024 characters; explain what the skill does and when to use it.

Optional portable fields include `license`, `compatibility`, and string-valued `metadata`.
`allowed-tools` is experimental and client support varies. Add `compatibility` only for real
environment requirements such as a specific product, system package, or network access.

Use relative paths from the skill root. Keep references shallow and focused; avoid chains in
which one reference points to another reference before the useful instructions appear.

## Invocation and client metadata

Automatic invocation is the portable default. Explicit-only policies and UI metadata are
client-specific and belong outside the portable instructions when possible.

For Codex, `agents/openai.yaml` can provide UI metadata and invocation policy:

```yaml
interface:
  display_name: "Skill name"
  short_description: "A concise UI description"
  default_prompt: "Use $skill-name to complete this task."

policy:
  allow_implicit_invocation: false
```

Use `allow_implicit_invocation: false` only when the user explicitly wants an explicit-only
skill. Quote string values and mention `$skill-name` in `default_prompt`. Do not put a
client-specific sidecar in a public skill unless it provides value for that client.

Other clients may use different fields or ignore the sidecar. Keep the actual workflow in
`SKILL.md` so unsupported metadata does not remove the capability.

## Validation

Use the strongest available checks without adding a permanent dependency solely for
validation:

```bash
skills-ref validate ./path/to/skill
npx skills add ./path/to/repository --list
```

The first command validates the Agent Skills format when `skills-ref` is available. The
second checks repository discovery through the skills CLI. For a collection, confirm that the
reported skill names exactly match the intended public set.

Also verify manually:

- directory name and frontmatter `name` match;
- every relative link resolves inside the installed skill;
- references and assets appear in a clean test installation;
- scripts have documented dependencies, useful errors, and successful representative runs;
- scaffold placeholders and internal-only paths are absent;
- no secret, credential, personal data, or private source is packaged;
- the license permits distribution of every bundled file.

Syntax validation proves package shape, not behavioral quality. Test observable decisions,
side effects, or generated artifacts for complex skills.

## Publishing with skills.sh

The skills CLI discovers valid `SKILL.md` directories in supported repository layouts,
including `skills/<name>/SKILL.md`. List a local collection before publishing:

```bash
npx skills add . --list
```

After the repository is available from GitHub, users can install the collection or one named
skill:

```bash
npx skills add owner/repository
npx skills add owner/repository --skill skill-name
```

Installation does not make unsafe instructions trustworthy. Keep scripts reviewable, declare
requirements, avoid hidden network or mutation behavior, and preserve the user's approval
boundary at runtime.

## Sources

- [Agent Skills specification](https://agentskills.io/specification)
- [skills CLI documentation](https://github.com/isiahhill/skills.sh#readme)
