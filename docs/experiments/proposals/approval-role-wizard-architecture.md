---
summary: "Proposta arquitetural para aprovação guiada por roles no pairing do OpenClaw"
owner: "anarkaike"
status: "proposed"
last_updated: "2026-02-16"
title: "Approval Role Wizard — Architecture Proposal"
---

# Approval Role Wizard — Architecture Proposal

## Decisão proposta

Adicionar um wizard no fluxo de aprovação que atribui role por número e aplica provisioning automaticamente.

## Roles (MVP)

- `restricted`
- `tenant`
- `superadmin`

## Fonte de verdade

Manter um mapa de políticas por principal (número/canal), com:

- role
- agentId
- metadata de aprovação (`approvedBy`, `approvedAt`)

## Fluxo

1. Número entra em pending.
2. Approver seleciona role no wizard.
3. Se `superadmin`, exigir confirmação forte.
4. Aplicar provisioning (agent + binding + policy).
5. Registrar auditoria append-only.

## Guardrails

- Números sem policy: deny por padrão.
- `superadmin` com allowlist explícita + confirmação forte.
- Comando de rollback (`role set`, `revoke`).

## Compatibilidade

Proposta incremental, sem quebrar o fluxo atual:

- Fase 1: wizard + policy map + auditoria.
- Fase 2: comandos administrativos e melhorias de UX.
- Fase 3: validações avançadas e hardening.
