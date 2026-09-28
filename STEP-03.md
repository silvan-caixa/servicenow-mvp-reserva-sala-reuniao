# STEP 03 — Definir arquitetura da solução
## Objetivo

Definir como a aplicação será estruturada tecnicamente.

## Atividades
 - [x] Definir entidades
 - [x] Definir tabelas
 - [x] Definir relacionamentos
 - [x] Avaliar tabelas nativas ServiceNow
 - [x] Avaliar tabelas customizadas
 - [x] Avaliar extensão da tabela Task
 - [x] Avaliar utilização de Location
 - [x] Avaliar utilização de Building
 - [x] Avaliar utilização de User
 - [x] Evitar extensão desnecessária da CMDB
 - [x] Definir estratégia para futuras expansões
 - [x] Documentar decisões arquiteturais

## Modelo inicial
```text
Unidade
   │
   └── Prédio
          │
          └── Andar
                 │
                 └── Sala
                        │
                        ├── Reserva
                        │
                        └── Bloqueio
```
## Entregáveis
- [x] Diagrama da arquitetura
- [x] Modelo conceitual
- [x] Decisões arquiteturais
## Critério de conclusão
 - [x] Arquitetura aprovada
