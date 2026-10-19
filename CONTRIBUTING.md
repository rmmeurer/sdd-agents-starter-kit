# Guia de Contribuição & Governança de Desenvolvimento (SDD Framework)

Bem-vindo a este projeto! Este documento estabelece as diretrizes obrigatórias de engenharia, versionamento e governança multi-agente que todos os desenvolvedores humanos e agentes de IA devem seguir rigorosamente.

---

## 1. Princípio Fundamental: Spec-Driven Development (SDD)

Neste projeto, **código de produção é o reflexo de especificações aprovadas**.

1. **Nenhuma feature começa pelo código:** Qualquer nova funcionalidade, alteração estrutural ou refatoração ampla deve iniciar no **[MODO: ARQUITETO]**, gerando uma especificação formal em `documentation/specs/spec-[numero]-[nome].md`.
2. **Aprovação prévia:** O código só pode ser escrito após o documento de especificação ser revisado e aprovado pelo usuário / tech lead.
3. **Auditoria de Entrega:** Ao finalizar a implementação, o **[MODO: AUDITOR]** gera um relatório em `documentation/audits/audit-[nome].md` comprovando conformidade estrita com a spec.

Consulte o arquivo [AGENTS.md](./AGENTS.md) para detalhes completos da orquestração multi-agente.

---

## 2. Fluxo de Branches (GitHub Flow)

Trabalhamos com o modelo **GitHub Flow Simplificado**.

### Regras de Ouro:
* A branch `main` é a versão oficial de produção.
* **É expressamente proibido fazer commit direto na `main`.**
* **É expressamente proibido criar branches com nomes pessoais** (ex: `joao-silva`, `maria-dev`).

### Nomenclatura Padrão de Branches:
| Prefixo | Uso | Exemplo |
| :--- | :--- | :--- |
| `feat/` | Nova funcionalidade, página ou integração | `feat/auth-magic-link` |
| `fix/` | Correção de bug ou falha técnica | `fix/input-mask-phone` |
| `docs/` | Criação ou alteração de documentações, specs ou PRDs | `docs/spec-dashboard-analytics` |
| `style/` | Ajustes visuais, CSS e estilização sem mudança de lógica | `style/dark-mode-contrast` |
| `refactor/`| Melhoria interna de código sem alteração funcional | `refactor/api-client-timeout` |
| `chore/` | Tooling, dependências e configurações de CI | `chore/update-dependencies` |

---

## 3. Padrão de Mensagens de Commit (Conventional Commits)

Todos os commits devem seguir a especificação [Conventional Commits](https://www.conventionalcommits.org/):

```text
<tipo>(<escopo>): <descrição objetiva no infinitivo e minúsculas>

[corpo opcional explicando o contexto ou motivação]
```

### Exemplos Válidos:
* `feat(auth): implementar autenticacao via magic link`
* `fix(api): tratar timeout em chamadas de webhook externo`
* `docs(specs): adicionar spec-001 de modelagem de dados`
* `style(ui): ajustar contraste de cores no dark mode`

### Exemplos Não Permitidos:
* ❌ `Ajustes`
* ❌ `Update files`
* ❌ `Add files via upload`
* ❌ `Fixes do dia`

---

## 4. Checklist Pré-Push e Pull Requests

Antes de abrir um Pull Request (PR) ou enviar commits para o GitHub:

1. **Validação Estática de Tipagem & Sintaxe:**
   Execute a validação estática do projeto para garantir zero quebras de compilação.
2. **Validação de Linting:**
   Garanta que o código siga os padrões de formatação e boas práticas.
3. **Template de PR:**
   Preencha obrigatoriamente todos os campos do [.github/pull_request_template.md](./.github/pull_request_template.md), apontando o link da spec correspondente em `documentation/specs/`.

---

## 5. Estrutura da Pasta de Documentação (`documentation/`)

Todo documento deve ser alocado em sua subpasta taxonômica correspondente:

* **`documentation/prd/`**: Documentos de Requisitos de Produto (visão macro).
* **`documentation/specs/`**: Especificações técnicas atômicas de cada feature.
* **`documentation/audits/`**: Auditorias de entrega, segurança e conformidade.
* **`documentation/playbooks/`**: Manuais operacionais e tutoriais passo a passo.
* **`documentation/architecture/`**: Diagramas de topologia e fluxo de dados.
