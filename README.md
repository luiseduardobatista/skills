# Skills

My agent skills — portable across any harness (PI, Claude Code, Codex).

Built on the [Agent Skills standard](https://agentskills.io/specification).

## Skills

| Skill | Description |
|---|---|
| [git-workflow](git-workflow/SKILL.md) | Regras para commits atômicos, conventional commits, PRs e operações Git |
| [good-code](good-code/SKILL.md) | Smallest stable change — KISS, YAGNI, código limpo |
| [pr-description](pr-description/SKILL.md) | Gera e revisa descrições de PR/MR claras e verificáveis |

## Installation

### PI

```bash
# Via settings.json
echo '{ "skills": ["~/repos/skills"] }' >> ~/.pi/agent/settings.json

# Ou via symlink
ln -s ~/repos/skills ~/.pi/agent/skills
```

### Claude Code

```bash
ln -s ~/repos/skills ~/.claude/skills
```

### Codex

```bash
ln -s ~/repos/skills ~/.codex/skills
```
