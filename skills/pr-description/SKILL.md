---
name: pr-description
description: "Gera e revisa descrições de PR/MR claras, verificáveis e compatíveis com as regras do repositório. Use quando o usuário pede para escrever, melhorar, revisar ou preparar título, corpo, resumo ou template de PR/MR, inclusive em projetos com mantenedores rigorosos. Use também quando o agente vai criar um pull request e precisar gerar a descrição automaticamente."
---

# PR Description

Produza uma descrição que permita ao mantenedor entender por que a mudança existe, conferir o que ela faz e decidir se está pronta para revisão.

## Processo

### 1. Descubra as regras do projeto

Antes de escrever, procure na raiz e nos diretórios afetados:

- `CONTRIBUTING*`, `DEVELOPMENT*` e documentação equivalente;
- templates de PR/MR em `.github/`, `.gitlab/` ou diretório indicado pelo projeto;
- regras sobre testes, documentação, issues, changelog, release notes, DCO ou CLA.

As regras e o template do projeto prevalecem sobre o formato padrão desta skill. Se o projeto exigir outro fluxo, como patches por e-mail, informe que uma descrição genérica de PR não é suficiente e siga a documentação encontrada.

### 2. Determine o escopo real

Use o intervalo informado pelo usuário. Em um repositório Git, se ele não for informado:

1. identifique a branch remota padrão;
2. encontre o merge-base entre ela e `HEAD`;
3. examine `git status`, os commits do intervalo e `git diff --stat`;
4. leia o diff completo das mudanças materiais.

Não trate apenas `git diff` sem intervalo como o conteúdo do PR: ele pode mostrar somente alterações locais. Avise se houver mudanças não commitadas que não façam parte do intervalo analisado.

### 3. Extraia o que o revisor precisa saber

Identifique somente fatos sustentados pelo código, histórico ou contexto fornecido:

- problema, motivação e comportamento anterior;
- solução e comportamento resultante;
- decisões não óbvias e alternativas relevantes;
- testes realmente executados e seus resultados;
- compatibilidade, segurança, desempenho, migração, rollout e rollback, quando afetados;
- documentação, release notes e issues exigidas pelo projeto.

Se faltar uma informação obrigatória que não possa ser obtida do repositório, faça uma pergunta objetiva antes de finalizar. Não invente testes, resultados, links, métricas ou justificativas.

### 4. Redija para revisão

- Explique primeiro o **porquê** e depois o **quê**.
- Descreva comportamento e impacto; não narre o diff arquivo por arquivo.
- Use texto direto, bullets curtos e detalhe proporcional ao risco.
- Preserve integralmente campos obrigatórios do template.
- Remova seções opcionais vazias em vez de adicionar conteúdo artificial.
- Para testes não executados, escreva `Não executado` e o motivo verdadeiro; nunca sugira que passaram.
- Se também pedirem um título, siga a convenção do projeto e descreva o resultado em linguagem específica.

### 5. Faça uma auditoria silenciosa

Antes de entregar, confira:

- cada afirmação material possui evidência no diff, nos commits ou no contexto;
- cada mudança material aparece na descrição;
- escopo, riscos, breaking changes e passos operacionais estão explícitos quando aplicáveis;
- testes e verificações não foram exagerados;
- todos os campos e regras do projeto foram atendidos;
- a descrição não contém placeholders nem detalhes irrelevantes.

Corrija os problemas encontrados. Entregue somente o título e/ou a descrição prontos para copiar, salvo se o usuário pedir análise ou checklist.

## Formato padrão

Use este formato apenas quando o repositório não fornecer um template. Inclua somente seções relevantes.

```markdown
## Contexto

[Problema, motivação e comportamento anterior.]

## Solução

[Abordagem adotada, comportamento resultante e decisões importantes.]

## Validação

- [Comando ou verificação realmente executada e resultado observado.]

## Impactos

- [Compatibilidade, risco, migração, rollout ou rollback aplicável.]

## Referências

- [Issue, documentação ou release note existente e relevante.]
```
