---
name: git-workflow
description: "Regras base para commits atômicos, conventional commits e análise de diff. Use quando a tarefa envolver Git ou histórico de mudanças: analisar git diff, preparar/stagear alterações, criar commits, branches, push, PRs, resolver conflitos ou revisar histórico."
---

# Git Workflow

Regras obrigatórias. Siga antes de qualquer operação no repositório.

## Segurança e contexto

### 1. Verifique o estado inicial

Execute `git status` e identifique alterações, commits ou branches já existentes.
Não descarte, sobrescreva, faça `reset`, `rebase`, `clean` ou `push --force`
sem confirmação explícita do usuário.

### 2. Preserve o trabalho do usuário

Não inclua alterações pré-existentes do usuário em commits sem confirmar que
elas pertencem à tarefa. Antes de criar um commit, revise também
`git diff --cached`.

### 3. Confirme que há commits para push

Antes de fazer push, verifique se existem commits locais não enviados. Se houver alterações não commitadas, aplique as regras de Commits primeiro.

## Commits

### 1. Analise o diff primeiro

Leia o diff completo antes de qualquer mensagem. Se contiver múltiplas mudanças não relacionadas, separe em commits distintos.

**Critério:** cada commit cobre uma única preocupação lógica.

### 2. Commits atômicos

Cada commit é uma unidade coesa de mudança:

- O título descreve o **resultado**, não o processo
- Não misture mudanças independentes no mesmo commit
- Mantenha juntas mudanças tecnicamente necessárias para a mesma preocupação,
  como uma pequena refatoração exigida por uma feature

**Critério:** `git log --oneline` mostra cada commit com um propósito claro.

### 3. Conventional Commits

Primeiro, respeite convenções definidas pelo repositório, como
`CONTRIBUTING.md`, commitlint ou histórico recente. Na ausência delas, use:
`<tipo>(escopo): descrição` — tipos comuns: `feat`, `fix`, `refactor`, `docs`, `chore`.

### 4. Sem coautoria

Commits e PRs são de autoria exclusiva do usuário. Sem `Co-authored-by`, sem menções a agente ou IA.

## PRs

### 1. Nunca da main/master

Se o branch atual for `main` ou `master`, não crie PR. Avise que não faz sentido criar PR da branch principal.

### 2. Operações remotas exigem pedido explícito

Não crie branches remotas, faça push ou abra PRs sem solicitação explícita do
usuário.

### 3. Push antes de criar

Faça push do branch para o remoto antes de executar `gh pr create`. O branch precisa existir no remoto.

### 4. Descrição via pr-description

Use a skill `pr-description` para gerar o corpo do PR. Nunca escreva a descrição manualmente — a skill já cobre descoberta de regras do projeto, escopo real e auditoria silenciosa.

### 5. Use gh CLI

Crie PRs com `gh pr create`. Não use a web UI nem outras ferramentas.
