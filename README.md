# skills

## Instalar

### npx skills (Recomendado)

```bash
npx skills@latest add luiseduardobatista/skills --all -g
```

Uma skill específica:

```bash
npx skills@latest add luiseduardobatista/skills --skill=git-workflow
# ou várias:
npx skills@latest add luiseduardobatista/skills
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
# ou atualiza todos os pacotes de uma vez
pi update --extensions
```

### Caminho direto

Clona o repo e aponta o agente para ele. Melhor para desenvolvimento — edições refletem no próximo restart.

```bash
git clone https://github.com/luiseduardobatista/skills ~/repos/skills
```

Adicionar no `settings.json` do pi:

```json
{
  "skills": ["~/repos/skills/skills"]
}
```

## Skills

| Skill | Descrição |
| --- | --- |
| [git-workflow](skills/git-workflow/SKILL.md) | Regras para commits atômicos, conventional commits, PRs e operações Git |
| [good-code](skills/good-code/SKILL.md) | Smallest stable change — KISS, YAGNI, código limpo |
| [grill-me](skills/grill-me/SKILL.md) | Entrevista intensa para aprimorar um plano ou design |
| [grill-with-docs](skills/grill-with-docs/SKILL.md) | Entrevista para aprimorar planos e criar documentação durante o processo |
| [handoff](skills/handoff/SKILL.md) | Gera um documento de handoff conciso para continuidade em outra sessão |
| [improve-codebase-architecture](skills/improve-codebase-architecture/SKILL.md) | Identifica oportunidades de aprofundamento na arquitetura do código |
| [pr-description](skills/pr-description/SKILL.md) | Gera e revisa descrições de PR/MR claras e verificáveis |
| [teach](skills/teach/SKILL.md) | Ensina um conceito ou habilidade em um workspace de aprendizado |
| [to-spec](skills/to-spec/SKILL.md) | Transforma a conversa atual em uma especificação publicável |
| [to-tickets](skills/to-tickets/SKILL.md) | Divide um plano ou especificação em tickets incrementais |
