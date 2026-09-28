# STEP 03 — Definir arquitetura da solução
## Objetivo

Definir como a aplicação será estruturada tecnicamente.

## Atividades
 - [ ] Definir entidades
 - [ ] Definir tabelas
 - [ ] Definir relacionamentos
 - [ ] Avaliar tabelas nativas ServiceNow
 - [ ] Avaliar tabelas customizadas
 - [ ] Avaliar extensão da tabela Task
 - [ ] Avaliar utilização de Location
 - [ ] Avaliar utilização de Building
 - [ ] Avaliar utilização de User
 - [ ] Evitar extensão desnecessária da CMDB
 - [ ] Definir estratégia para futuras expansões
 - [ ] Documentar decisões arquiteturais

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
- [ ] Diagrama da arquitetura
- [ ] Modelo conceitual
- [ ] Decisões arquiteturais
## Critério de conclusão
 - [ ] Arquitetura aprovada
