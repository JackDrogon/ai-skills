# AI Skills

This repository is organized as a Claude-compatible skills marketplace, following the structure used by Anthropic's public `skills` repository.

## Structure

- `.claude-plugin/marketplace.json`: marketplace metadata that Claude uses to discover installable plugins.
- `skills/`: the directory that contains each installable skill.
- `skills/git-commit/SKILL.md`: the skill definition and operating instructions for commit message generation.

## Included Skills

### `git-commit`

Generates high-quality Conventional Commit messages, rewrites rough commit text into cleaner forms, and can drive a staged-only `git commit -s` workflow when the user explicitly asks to commit. If Claude invokes `/git-commit` directly with no extra arguments, that direct invocation is also treated as explicit authorization to commit.

## Install with Claude

From Claude Code, add this repository as a marketplace:

```bash
/plugin marketplace add JackDrogon/ai-skills
```

Then install the plugin collection defined in this repo:

```bash
/plugin install git-tools@ai-skills
```

Here `ai-skills` comes from the marketplace `name` field in `/.claude-plugin/marketplace.json`.

## Skill Authoring Notes

Each skill lives under `skills/<skill-name>/` and should include a `SKILL.md` file with YAML frontmatter. The `name` field should match the directory name, and the `description` should describe both what the skill does and when Claude should trigger it.
