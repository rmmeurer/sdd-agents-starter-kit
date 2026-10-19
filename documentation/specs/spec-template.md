# SPEC-[NUMERO]: [Título Conciso da Funcionalidade ou Refatoração]

> **Status:** [Draft | Under Review | Approved | Implemented]  
> **Autor(a):** [Nome / Agente Arquiteto]  
> **Data:** [YYYY-MM-DD]  
> **Modos Envolvidos:** [MODO: ARQUITETO], [MODO: ENGENHEIRO {DOMÍNIO}], [MODO: AUDITOR]

---

## 1. Contexto e Objetivos
* **Problema:** Descreva qual problema de negócio, usuário ou débito técnico esta especificação resolve.
* **Objetivo:** O que este desenvolvimento deve alcançar de forma mensurável e tangível.
* **Não-Escopo:** O que explicitamente **NÃO** faz parte desta entrega para evitar escopo inflado (*scope creep*).

---

## 2. Requisitos Funcionais e Casos de Uso
1. **[RF-01]** O sistema deve ...
   - *Critério de validação:* Quando o usuário clicar em X, Y deve ocorrer.
2. **[RF-02]** O endpoint / componente deve ...
   - *Critério de validação:* Em caso de payload inválido, retornar erro 422 formatado.

---

## 3. Especificação Técnica & Arquitetura

### 3.1. Estrutura de Arquivos Afetados
```text
caminho/do/projeto/
├── novo-modulo/
│   ├── index.ts
│   └── tipos.ts
└── modulo-existente/
    └── componente.tsx
```

### 3.2. Contratos de Dados & Interfaces (TypeScript / Schemas)
```typescript
export interface ExemploContrato {
  id: string;
  titulo: string;
  criadoEm: string;
}
```

### 3.3. Tratamento de Estados e Exceções
- **Loading:** Como o estado de carregamento é tratado visualmente ou programaticamente.
- **Empty State:** O que ocorre quando não há dados.
- **Error Handling:** Como falhas de rede, validações ou timeouts são interceptados e tratados.

---

## 4. Plano de Execução em Fases (Checklist Atômico)

- [ ] **Fase 1: Preparação e Modelagem**
  - [ ] Criar tipagens e interfaces.
  - [ ] Validar dependências necessárias.

- [ ] **Fase 2: Implementação Core**
  - [ ] Implementar a lógica / backend / componentes.
  - [ ] Conectar pontos de integração.

- [ ] **Fase 3: Refinamento & Estados de UI (se aplicável)**
  - [ ] Implementar estados vazios, erros e loading.
  - [ ] Validar responsividade e acessibilidade.

- [ ] **Fase 4: Validação & Auditoria**
  - [ ] Executar checagens de tipos estáticos e lint.
  - [ ] Gerar relatório de auditoria em `documentation/audits/audit-[nome].md`.

---

## 5. Critérios de Aceitação (Definition of Done)
1. Todos os itens do plano de execução marcados como concluídos.
2. 0 erros de tipagem estática e 0 warnings impeditivos de linter.
3. Alinhamento milimétrico entre o código produzido e esta especificação técnica.
