# luisb-skills

Personal agent skills — portable across any harness (PI, Claude Code, Codex).

Built on the [Agent Skills standard](https://agentskills.io/specification).

## Install

### npx skills (Recommended)

Works with any agent harness. Copies editable skill files locally.

```bash
npx skills@latest add luiseduardobatista/skills
```

Install a single skill:

```bash
npx skills@latest add luiseduardobatista/skills --skill=git-workflow
```

Update:

```bash
npx skills update
```

### pi install

PI-native package management. Clones and manages the repo automatically.

```bash
pi install git:github.com/luiseduardobatista/skills
```

Update:

```bash
pi update git:github.com/luiseduardobatista/skills
```

### Direct path

Clone the repo and point your harness to it. Best for active development — edits take effect on restart.

```bash
git clone https://github.com/luiseduardobatista/skills ~/repos/skills
```

Then add to your settings:

```json
{
  "skills": ["~/repos/skills/skills"]
}
```

## Skills

| Skill | Description |
|---|---|
| [git-workflow](skills/git-workflow/SKILL.md) | Regras para commits atômicos, conventional commits, PRs e operações Git |
| [good-code](skills/good-code/SKILL.md) | Smallest stable change — KISS, YAGNI, código limpo |
| [pr-description](skills/pr-description/SKILL.md) | Gera e revisa descrições de PR/MR claras e verificáveis |
