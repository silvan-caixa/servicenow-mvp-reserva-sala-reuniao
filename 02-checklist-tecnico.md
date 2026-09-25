# Checklist Técnico Detalhado — MVP Reserva de Salas de Reunião

> **Projeto:** Gestão de Salas de Reunião  
> **Plataforma:** ServiceNow  
> **Escopo:** MVP — Reserva de Salas de Reunião  
> **Objetivo:** Construir uma solução funcional em ServiceNow para consulta, reserva, alteração e cancelamento de salas de reunião.

---

# 1. Levantamento e definição do MVP

## 1.1 Processo atual

- [ ] Documentar o funcionamento do SIASR atual
- [ ] Mapear o processo atual de reserva
- [ ] Mapear o processo de cancelamento
- [ ] Mapear o processo de alteração
- [ ] Mapear o processo de bloqueio de salas
- [ ] Identificar limitações do sistema atual
- [ ] Identificar funcionalidades que serão mantidas
- [ ] Identificar funcionalidades que serão melhoradas
- [ ] Identificar funcionalidades que serão descartadas

## 1.2 Atores

- [ ] Identificar usuário solicitante
- [ ] Identificar gestor/responsável pela sala
- [ ] Identificar administrador da aplicação
- [ ] Identificar equipe responsável pelo inventário
- [ ] Identificar responsáveis pelas unidades/centralizadoras
- [ ] Definir responsabilidades de cada ator

## 1.3 Escopo do MVP

- [ ] Definir funcionalidades obrigatórias
- [ ] Definir funcionalidades desejáveis
- [ ] Definir funcionalidades fora do MVP
- [ ] Definir critérios de aceite
- [ ] Validar escopo com o negócio
- [ ] Registrar versão do escopo aprovado

---

# 2. Arquitetura da aplicação

## 2.1 Estrutura da aplicação

- [ ] Criar aplicação scoped
- [ ] Definir nome da aplicação
- [ ] Definir nome técnico
- [ ] Definir descrição
- [ ] Definir escopo da aplicação
- [ ] Definir módulos da aplicação
- [ ] Definir convenção de nomes

## 2.2 Arquitetura

- [ ] Definir entidades principais
- [ ] Definir relacionamento entre entidades
- [ ] Avaliar tabelas nativas ServiceNow
- [ ] Avaliar tabelas customizadas
- [ ] Definir estratégia de extensão de tabelas
- [ ] Evitar extensão desnecessária de tabelas CMDB
- [ ] Definir arquitetura para futura expansão para "Gestão de Espaços"
- [ ] Validar arquitetura com equipe técnica
- [ ] Registrar decisões arquiteturais

> **Diretriz:** o MVP deve resolver a reserva de salas sem criar dependências desnecessárias com estruturas corporativas ou CMDB.

---

# 3. Modelo de dados

## 3.1 Entidades principais

Definir inicialmente as seguintes entidades:

- [ ] Unidade
- [ ] Prédio
- [ ] Andar
- [ ] Sala
- [ ] Reserva
- [ ] Bloqueio de Sala
- [ ] Horário / Janela de Uso
- [ ] Regras de acesso
- [ ] Usuário

---

# 4. Tabelas

## 4.1 Tabela de Sala

Definir tabela para representar as salas disponíveis para reserva.

Sugestão:

`u_sala`

Campos a avaliar:

- [ ] Número/código da sala
- [ ] Nome da sala
- [ ] Unidade
- [ ] Prédio
- [ ] Andar
- [ ] Capacidade
- [ ] Localização
- [ ] Descrição
- [ ] Status
- [ ] Ativa
- [ ] Características
- [ ] Responsável
- [ ] Data de início de disponibilidade
- [ ] Data de término de disponibilidade

---

## 4.2 Tabela de Reserva

A reserva representa o agendamento realizado pelo usuário.

Sugestão:

`u_reserva_sala`

Campos:

- [ ] Número da reserva
- [ ] Solicitante
- [ ] Sala
- [ ] Data
- [ ] Hora inicial
- [ ] Hora final
- [ ] Quantidade de participantes
- [ ] Assunto/finalidade
- [ ] Observações
- [ ] Estado
- [ ] Data de criação
- [ ] Criado por
- [ ] Data de alteração
- [ ] Alterado por
- [ ] Motivo do cancelamento

---

## 4.3 Tabela de Bloqueio

Representar períodos em que uma sala não pode ser reservada.

Sugestão:

`u_bloqueio_sala`

Campos:

- [ ] Sala
- [ ] Data inicial
- [ ] Data final
- [ ] Hora inicial
- [ ] Hora final
- [ ] Motivo
- [ ] Tipo de bloqueio
- [ ] Responsável
- [ ] Estado
- [ ] Observação

Tipos possíveis:

- [ ] Manutenção
- [ ] Evento
- [ ] Indisponibilidade
- [ ] Restrição operacional
- [ ] Outro

---

# 5. Relacionamentos

Definir os relacionamentos:

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
