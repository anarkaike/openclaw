---
summary: "Sprint inicial para colocar Approval Role Wizard em produção com segurança"
owner: "anarkaike"
status: "planned"
last_updated: "2026-02-16"
title: "Sprint 01 — Approval Role Wizard"
---

# Sprint 01 — Approval Role Wizard

## Meta da sprint

Entregar versão funcional do wizard de aprovação por role com guardrails mínimos.

## Itens da sprint

1. Modelagem de policy map.
2. Implementação do wizard de role no approval.
3. Provisionamento por role (`restricted`, `tenant`, `superadmin`).
4. Auditoria de approve/change/revoke.
5. Testes de segurança e regressão.

## Definition of Done

- Fluxo completo do approve com role em ambiente local.
- Testes de regressão verdes para roteamento principal.
- Documentação de operação atualizada em `docs/experiments`.
