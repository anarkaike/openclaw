---
summary: "Análise inicial para aprovação com perfis de acesso (restricted, tenant, superadmin) no OpenClaw"
owner: "anarkaike"
status: "active"
last_updated: "2026-02-16"
title: "Approval Role Wizard — Discovery & Analysis"
---

# Approval Role Wizard — Discovery & Analysis

## Problema

Hoje, o fluxo de aprovação de novos números é funcional, mas não orientado por perfil de confiança.
Isso gera trabalho manual e risco operacional ao escalar múltiplos usuários com níveis diferentes de acesso.

## Objetivo

No momento da aprovação, classificar cada número em um perfil explícito:

- `restricted`: conversa com o bot sem permissões sensíveis.
- `tenant`: ambiente isolado dedicado.
- `superadmin`: administração avançada, com confirmação forte.

## Hipóteses

1. Um wizard curto no approve reduz erros de configuração pós-aprovação.
2. "Deny by default" para números sem perfil aumenta segurança.
3. Registro de auditoria reduz risco e melhora rastreabilidade.

## Riscos

- Escalonamento indevido para `superadmin` sem confirmação robusta.
- Drift de configuração entre policies e bindings.
- Falta de rollback simples em mudanças de role.

## Critérios de sucesso

- Aprovação com role em um único fluxo.
- Provisionamento automático por role (agent/binding/política).
- Logs auditáveis para approve/change/revoke.
- Rebaixamento/revogação com efeito imediato.
