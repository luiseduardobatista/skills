# skills

## Instalar

### npx skills (Recomendado)

Funciona com qualquer agente. Copia os arquivos localmente e são editáveis.

```bash
npx skills@latest add luiseduardobatista/skills
```

Uma skill específica:

```bash
npx skills@latest add luiseduardobatista/skills --skill=git-workflow
```

Atualizar:

```bash
npx skills update
```

### pi install

Gerenciado nativamente pelo PI. Clona e atualiza o repositório automaticamente.

```bash
pi install git:github.com/luiseduardobatista/skills
```

Atualizar:

```bash
pi update git:github.com/luiseduardobatista/skills
```

### Caminho direto

Clona o repo e aponta o agente para ele. Melhor para desenvolvimento — edições refletem no próximo restart.

```bash
git clone https://github.com/luiseduardobatista/skills ~/repos/skills
```

Adicionar nas configurações:

```json
{
  "skills": ["~/repos/skills/skills"]
}
```

## Skills

| Skill | Descrição |
|---|---|
| [git-workflow](skills/git-workflow/SKILL.md) | Regras para commits atômicos, conventional commits, PRs e operações Git |
| [good-code](skills/good-code/SKILL.md) | Smallest stable change — KISS, YAGNI, código limpo |
| [pr-description](skills/pr-description/SKILL.md) | Gera e revisa descrições de PR/MR claras e verificáveis |
