# STEP 07 — Criar consulta de disponibilidade
## Objetivo

Permitir que o usuário encontre salas disponíveis.

## Atividades
- [x] Selecionar unidade
- [x] Selecionar prédio
- [x] Selecionar andar
- [x] Selecionar data
- [x] Selecionar horário
- [x] Informar quantidade de participantes
- [x] Consultar salas
- [x] Exibir capacidade
- [-] Exibir características
- [x] Exibir disponibilidade

## Fluxo
```text
Unidade
   ↓
Prédio
   ↓
Andar
   ↓
Data
   ↓
Horário
   ↓
Participantes
   ↓
Salas disponíveis
```
## UX
```
┌──────────────────────────────────────────────┐
│       CONSULTA DE DISPONIBILIDADE            │
│                                              │
│ Prédio     Andar                             │
│ [▼]         [▼]                              │
│                                              │
│ Data        Horário      Participantes       │
│ [📅]        [🕐]         [   ]               │
│                                              │
│              [ CONSULTAR SALAS ]             │
│                                              │
│ RESULTADO                                    │
│                                              │
│ Sala 001 - Reunião                           │
│ Capacidade: 12                               │
│ Características: ...                         │
│ Disponibilidade: DISPONÍVEL                  │
└──────────────────────────────────────────────┘
```
## Critério de conclusão
- [x] Usuário consegue consultar salas disponíveis
