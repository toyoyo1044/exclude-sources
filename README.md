# ban-sources

`ban-sources` is a Codex skill for enforcing configurable source restrictions and source-priority policies during technical research, debugging, implementation, design, review, and explanation.

The included policy currently excludes Qiita and Zenn. You can extend or replace the policy without changing the skill's generic trigger metadata.

## Repository Structure

```text
ban-sources/
├── README.md
├── LICENSE
└── skills/
    └── ban-sources/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

## Installation

Copy the skill directory into your user-level skills directory:

```bash
mkdir -p ~/.agents/skills
cp -R skills/ban-sources ~/.agents/skills/
```

Codex detects skill changes automatically. Restart Codex if the skill does not appear.

For repository-scoped use, copy the same directory to `<repository>/.agents/skills/ban-sources` instead.

## Usage

Invoke the skill explicitly:

```text
Use $ban-sources for this technical investigation.
```

Codex may also invoke it automatically when a request matches the description in `SKILL.md`.

## Customization

Edit `skills/ban-sources/SKILL.md`. For each policy entry, keep these fields synchronized:

- `Targets`
- `Forbidden domains`
- `Search exclusions`

Change `Required behavior` only when the rule itself changes. Keep the frontmatter and `agents/openai.yaml` generic so adding a target does not require renaming or repackaging the skill.

## License

MIT
