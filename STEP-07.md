# STEP 07 — Criar consulta de disponibilidade
## Objetivo

Permitir que o usuário encontre salas disponíveis.

## Atividades
- [ ] Selecionar unidade
- [ ] Selecionar prédio
- [ ] Selecionar andar
- [ ] Selecionar data
- [ ] Selecionar horário
- [ ] Informar quantidade de participantes
- [ ] Consultar salas
- [ ] Exibir capacidade
- [ ] Exibir características
- [ ] Exibir disponibilidade

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
│ Unidade     Prédio       Andar               │
│ [▼]         [▼]          [▼]                 │
│                                              │
│ Data        Horário      Participantes       │
│ [📅]        [🕐]         [   ]                │
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
- [ ] Usuário consegue consultar salas disponíveis
