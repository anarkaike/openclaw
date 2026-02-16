---
summary: "Plano MVP para implementar aprovação por role no OpenClaw"
owner: "anarkaike"
status: "active"
last_updated: "2026-02-16"
title: "Approval Role Wizard — MVP Plan"
---

# Approval Role Wizard — MVP Plan

## Escopo MVP

- Definir roles: `restricted`, `tenant`, `superadmin`.
- Introduzir wizard no approve para escolha de role.
- Provisionar agent/binding por role.
- Persistir policy map por número.
- Registrar auditoria básica de mudanças.

## Fora do MVP

- UI avançada de administração.
- Multi-step wizard com formulários complexos.
- Políticas dinâmicas por grupo/canal além do necessário para o fluxo inicial.

## Entregáveis

1. Policy map persistente.
2. Handler de approval com role.
3. Confirmação forte para `superadmin`.
4. Audit log append-only.
5. Comandos administrativos mínimos (`role get/set`, `revoke`).

## Dependências

- Estruturas de sessão/agent/binding existentes.
- Camada de config/persistência em uso pelo gateway.

## Checklist

- [ ] Role selection no approve
- [ ] Provisionamento automático por role
- [ ] Guardrail deny-by-default
- [ ] Superadmin com confirmação e allowlist
- [ ] Auditoria de eventos críticos
- [ ] Testes happy path e rollback
