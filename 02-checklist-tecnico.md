# 🔧 Checklist Técnico Detalhado — MVP Reserva de Salas de Reunião

> **Projeto:** Gestão de Salas de Reunião  
> **Plataforma:** ServiceNow  
> **Escopo:** MVP — Reserva de Salas de Reunião  
> **Objetivo:** Construir uma solução funcional em ServiceNow para consulta, reserva, alteração e cancelamento de salas de reunião.

---

# 1. 📋 Levantamento e definição do MVP

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

# 2. 🏗️ Arquitetura da aplicação

## 2.1 Estrutura da aplicação

- [ ] Criar aplicação Scoped
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
- [ ] Avaliar extensão da tabela Task para reservas
- [ ] Evitar extensão desnecessária de tabelas CMDB
- [ ] Definir arquitetura para futura expansão para Gestão de Espaços
- [ ] Validar arquitetura com equipe técnica
- [ ] Registrar decisões arquiteturais

> **Diretriz:** o MVP deve resolver a reserva de salas sem criar dependências desnecessárias com estruturas corporativas ou CMDB.

---

# 3. 🗃️ Modelo de dados

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

## 3.2 Modelo conceitual

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
