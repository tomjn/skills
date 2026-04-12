# Skills Repo

## Structure

Each skill lives in `skills/<skill-name>/SKILL.md` following the `npx skills` convention.

## Skill File Format

YAML frontmatter with markdown body:

```yaml
---
name: skill-name
description: When to use this skill. Include trigger phrases.
version: "1.0.0"
---
```

- Directory name must match the `name` field
- `description` should list trigger phrases so agents know when to activate
- Use semantic versioning for `version`
- Keep skills scannable -- prefer code examples and tables over prose
- Keep `SKILL.md` under 500 lines; use `references/` for supporting docs
