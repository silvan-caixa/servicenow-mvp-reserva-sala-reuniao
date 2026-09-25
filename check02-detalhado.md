# CHECKLIST TÉCNICO DETALHADO

## Este será o checklist que eu usaria durante o desenvolvimento do MVP.

## 1. ANALYZE & DESIGN BUSINESS LOGIC
### 1.1 Definição do MVP
- [ ] Definir formalmente o MVP
- [ ] Documentar o que está dentro do MVP
- [ ] Documentar o que está fora do MVP
- [ ] Definir critérios de aceite
- [ ] Definir resultado esperado: empregado consegue reservar uma sala disponível
### Dentro do MVP
- [ ] Cadastro/inventário de salas
- [ ] Consulta de disponibilidade
- [ ] Reserva
- [ ] Cancelamento
- [ ] Alteração
- [ ] Controle de conflitos
- [ ] Capacidade da sala
- [ ] Localização da sala
- [ ] Notificação
- [ ] Gestão das salas
- [ ] Bloqueio/manutenção
- [ ] Auditoria
- [ ] Relatórios básicos
### Fora do MVP
- [ ] Vagas de veículos elétricos
- [ ] Vagas de visitantes
- [ ] Outros espaços
- [ ] Equipamentos
- [ ] Agendamento de outros serviços
- [ ] Integração completa com Outlook/Teams
- [ ] Outros canais de reserva
### 1.2 Personas / atores
- [ ] Empregado / solicitante
- [ ] Gestor da sala
- [ ] Administrador da aplicação
- [ ] Gestor da unidade/centralizadora
- [ ] Sistema/integração responsável pelo inventário
### 1.3 Processo de reserva

### Definir o processo completo:

```text
        Usuário
           ↓
        Escolhe data
           ↓
        Escolhe unidade/prédio
           ↓
        Informa quantidade de pessoas
           ↓
        Consulta salas disponíveis
           ↓
        Seleciona sala
           ↓
        Seleciona horário
           ↓
        Sistema valida regras
           ↓
        Reserva criada
           ↓
        Notificação
```

### Checklist:

- [ ] Definir início do processo
- [ ] Definir dados obrigatórios
- [ ] Definir busca da sala
- [ ] Definir seleção de horário
- [ ] Validar disponibilidade
- [ ] Validar capacidade
- [ ] Validar permissão
- [ ] Criar reserva
- [ ] Confirmar reserva
- [ ] Enviar notificação

### 1.4 Regras de negócio
### Disponibilidade
- [ ] Sala disponível pode ser reservada
- [ ] Sala ocupada não pode ser reservada
- [ ] Dois usuários não podem reservar o mesmo horário
- [ ] Reserva deve considerar data + horário + sala
- [ ] Intervalos de 30 minutos
- [ ] Definir horário inicial permitido
- [ ] Definir horário final permitido
### Capacidade
- [ ] Informar número de participantes
- [ ] Consultar capacidade da sala
- [ ] Impedir reserva quando participantes > capacidade
- [ ] Informar ao usuário o motivo do bloqueio
Sala
- [ ] Sala ativa pode ser reservada
- [ ] Sala inativa não pode ser reservada
- [ ] Sala em manutenção não pode ser reservada
- [ ] Sala bloqueada não pode ser reservada
Reserva
- [ ] Criar
- [ ] Alterar
- [ ] Cancelar
- [ ] Consultar
- [ ] Histórico
## 2. DESIGN & BUILD DATA MODEL

## Aqui está uma parte importante do projeto.

### 2.1 Arquitetura proposta

### Eu sugiro que o modelo seja construído sem estender a CMDB para representar salas, seguindo a preocupação levantada na reunião sobre não poluir a CMDB.

### A arquitetura inicial pode ser:

```text
                Gestão de Espaços
                       │
                       Unidade
                           │
                           └── Prédio
                                  │
                                  └── Andar
                                         │
                                         └── Sala
                                                │
                                                ├── Capacidade
                                                ├── Recursos
                                                ├── Status
                                                └── Disponibilidade
                                                       │
                                                       └── Reserva
                                                              │
                                                              ├── Solicitante
                                                              ├── Data
                                                              ├── Hora inicial
                                                              ├── Hora final
                                                              ├── Participantes
                                                              ├── Status
                                                              └── Observações
```
### 2.2 Tabelas
### Tabela: Unidade
- [ ] Criar tabela Unidade
- [ ] Código da unidade
- [ ] Nome
- [ ] Região/centralizadora
- [ ] Status
- [ ] Localização
- [ ] Fuso horário

### Tabela: Prédio
- [ ] Criar tabela Prédio
- [ ] Código
- [ ] Nome
- [ ] Unidade
- [ ] Endereço
- [ ] Cidade
- [ ] Estado
- [ ] Fuso horário
- [ ] Status

Relacionamento:

Unidade 1 ───── N Prédios
### Tabela: Andar
- [ ] Criar tabela Andar
- [ ] Identificação do andar
- [ ] Prédio
- [ ] Descrição
- [ ] Status

Relacionamento:

Prédio 1 ───── N Andares
### Tabela: Sala
- [ ] Criar tabela Sala
- [ ] Número/nome da sala
- [ ] Andar
- [ ] Prédio
- [ ] Capacidade
- [ ] Descrição
- [ ] Status
- [ ] Disponível para reserva
- [ ] Data de início de operação
- [ ] Data de encerramento, se aplicável
- [ ] Observações

Relacionamento:

Andar 1 ───── N Salas

### 2.3 Recursos da sala

Para o MVP podemos avaliar se esses campos serão necessários.

- [ ] Projetor
- [ ] Videoconferência
- [ ] TV/monitor
- [ ] Quadro
- [ ] Internet
- [ ] Outros recursos

Decisão de arquitetura:

- [ ] Campos diretamente na tabela Sala

ou

- [ ] Tabela de Recursos + relacionamento Sala × Recurso

Para o MVP, eu começaria simples, caso esses recursos sejam apenas informativos.

### 2.4 Tabela de Reserva

#### Aqui está o núcleo do sistema.

#### Proposta

#### Reserva estendendo Task, conforme a linha que já foi estudada no projeto preliminar.

- [ ] Criar tabela Reserva
- [ ] Avaliar extensão de Task
- [ ] Definir número da reserva
- [ ] Solicitante
- [ ] Sala
- [ ] Data
- [ ] Hora inicial
- [ ] Hora final
- [ ] Quantidade de participantes
- [ ] Status
- [ ] Observações
- [ ] Data/hora de criação
- [ ] Criado por
- [ ] Data/hora de alteração
- [ ] Atualizado por

Relacionamentos:

Usuário ─────── N Reservas
Sala ────────── N Reservas
2.5 Estados da Reserva

Definir os estados:

Requested
    ↓
Reserved
    ↓
Completed

Com possibilidade de:

Requested → Cancelled
Reserved  → Cancelled

Checklist:

- [ ] Definir estados
- [ ] Definir valores internos
- [ ] Definir transições permitidas
- [ ] Definir quem pode alterar cada estado
3. DESIGN & CREATE USER INTERFACE
3.1 Employee Center
- [ ] Criar entrada no Employee Center
- [ ] Definir categoria Gestão de Espaços
- [ ] Criar item Reservar Sala de Reunião
- [ ] Criar item Minhas Reservas
- [ ] Definir navegação
3.2 Service Catalog

Criar:

Catalog Item — Reservar Sala de Reunião

Campos:

- [ ] Data
- [ ] Horário inicial
- [ ] Horário final
- [ ] Unidade
- [ ] Prédio
- [ ] Andar
- [ ] Quantidade de participantes
- [ ] Sala
- [ ] Observações
3.3 Consulta de disponibilidade

O usuário deverá conseguir:

- [ ] Selecionar data
- [ ] Selecionar horário
- [ ] Informar quantidade de pessoas
- [ ] Filtrar por prédio
- [ ] Filtrar por andar
- [ ] Visualizar salas disponíveis
- [ ] Visualizar capacidade
- [ ] Visualizar recursos
- [ ] Selecionar sala
3.4 Minhas reservas
- [ ] Listar reservas do usuário
- [ ] Mostrar data
- [ ] Mostrar horário
- [ ] Mostrar sala
- [ ] Mostrar prédio
- [ ] Mostrar status
- [ ] Permitir abrir reserva
- [ ] Permitir cancelar
- [ ] Permitir alterar, conforme regra
4. APPLY SECURITY
4.1 Roles

Criar/definir:

- [ ] Usuário da aplicação
- [ ] Gestor de salas
- [ ] Administrador
4.2 ACL
Sala
- [ ] Usuário pode consultar salas
- [ ] Gestor pode criar sala
- [ ] Gestor pode alterar sala
- [ ] Usuário não pode excluir sala
Reserva
- [ ] Usuário pode criar reserva
- [ ] Usuário pode consultar suas reservas
- [ ] Usuário pode cancelar suas reservas
- [ ] Gestor pode consultar reservas da sua unidade
- [ ] Administrador possui acesso completo
5. AUTOMATE

Essa será uma das principais partes do desenvolvimento.

5.1 Flow — Criar reserva
Solicitação
     ↓
Validar dados
     ↓
Validar sala
     ↓
Validar capacidade
     ↓
Validar disponibilidade
     ↓
Criar Reserva
     ↓
Atualizar status
     ↓
Enviar confirmação

Checklist:

- [ ] Criar Flow
- [ ] Trigger
- [ ] Validar sala
- [ ] Validar capacidade
- [ ] Validar disponibilidade
- [ ] Criar reserva
- [ ] Atualizar estado
- [ ] Enviar notificação
5.2 Controle de conflito

Regra fundamental:

Sala A
Data: 25/09/2026
10:00 → 11:00

Não permitir:

Sala A
25/09/2026
10:30 → 11:30

porque existe sobreposição.

Checklist:

- [ ] Definir regra de sobreposição
- [ ] Criar Business Rule ou mecanismo equivalente
- [ ] Consultar reservas existentes
- [ ] Identificar sobreposição
- [ ] Bloquear gravação
- [ ] Exibir mensagem ao usuário
- [ ] Testar concorrência
5.3 Cancelamento
- [ ] Definir quem pode cancelar
- [ ] Definir antecedência mínima
- [ ] Alterar status para Cancelled
- [ ] Liberar horário
- [ ] Registrar histórico
- [ ] Enviar notificação
5.4 Bloqueio de sala

Processo:

Gestor
   ↓
Seleciona sala
   ↓
Define período
   ↓
Informa motivo
   ↓
Sala indisponível
- [ ] Criar mecanismo de bloqueio
- [ ] Data inicial
- [ ] Data final
- [ ] Motivo
- [ ] Impedir novas reservas
- [ ] Exibir indisponibilidade
5.5 Notificações
Reserva criada

- [ ] Enviar confirmação

Reserva alterada

- [ ] Enviar alteração

Reserva cancelada

- [ ] Enviar cancelamento

Lembrete

- [ ] Avaliar lembrete da reserva para o MVP

6. INTEGRATE

Aqui precisamos separar integração obrigatória de integração futura.

6.1 Inventário de salas

O sistema precisa receber:

Unidade
   ↓
Prédio
   ↓
Andar
   ↓
Sala
   ↓
Capacidade

Checklist:

- [ ] Definir fonte do inventário
- [ ] Definir layout do arquivo
- [ ] Criar Import Set
- [ ] Criar tabela de staging
- [ ] Criar Transform Map
- [ ] Fazer mapeamento
- [ ] Validar registros
- [ ] Criar atualização incremental
- [ ] Tratar novos registros
- [ ] Tratar salas desativadas
6.2 SAP

Para o MVP:

- [ ] Definir se o SAP será integrado diretamente

ou

- [ ] Consumir arquivo/exportação fornecida pelo processo existente.

Minha sugestão para o MVP de capacitação seria deixar a integração SAP completa como uma etapa posterior, caso ela não seja necessária para colocar a reserva de salas funcionando.

6.3 Outlook / Microsoft Graph

A reunião levantou essa possibilidade, mas como estamos delimitando o MVP:

- [ ] Documentar integração futura

Não incluir no MVP inicial, salvo se o grupo decidir que ela é indispensável para o critério de aceite.

7. TEST
7.1 Testes de reserva
- [ ] Reserva de sala disponível
- [ ] Reserva de sala ocupada
- [ ] Reserva em horário parcialmente sobreposto
- [ ] Reserva em horário livre
- [ ] Reserva com capacidade válida
- [ ] Reserva acima da capacidade
- [ ] Reserva de sala bloqueada
- [ ] Reserva de sala inativa
7.2 Testes de usuário
- [ ] Usuário comum
- [ ] Gestor
- [ ] Administrador
- [ ] Usuário sem permissão
7.3 Testes de processo
- [ ] Criar
- [ ] Consultar
- [ ] Alterar
- [ ] Cancelar
- [ ] Reagendar
- [ ] Notificação
- [ ] Histórico
7.4 ATF
- [ ] Criar teste automatizado de reserva
- [ ] Testar disponibilidade
- [ ] Testar conflito
- [ ] Testar cancelamento
- [ ] Testar permissões
- [ ] Testar formulário
- [ ] Executar suíte de testes
8. ENHANCE USER INTERFACE
8.1 Experiência de reserva

Objetivo:

O usuário deve conseguir encontrar e reservar uma sala com o menor número possível de passos.

- [ ] Tela inicial simples
- [ ] Data
- [ ] Horário
- [ ] Número de participantes
- [ ] Local
- [ ] Filtros
- [ ] Salas disponíveis
- [ ] Informações da sala
- [ ] Confirmação
8.2 Visualização de disponibilidade

Podemos manter a ideia do SIASR, mas modernizá-la:

┌─────────────────────────────────────────────┐
│ Reservar sala                               │
│                                             │
│ 📅 25/09/2026                               │
│ ⏰ 10:00 - 11:00                            │
│ 👥 8 participantes                          │
│ 📍 Edifício Sede                            │
│                                             │
│ Salas disponíveis                           │
│                                             │
│ Sala 02       12 lugares       ✓ Disponível │
│ Sala 04        4 lugares       ✕ Capacidade │
│ Sala 05        8 lugares       ✓ Disponível │
└─────────────────────────────────────────────┘
- [ ] Protótipo UX
- [ ] Validar protótipo com negócio
- [ ] Aplicar identidade visual Caixa
- [ ] Implementar interface
- [ ] Testar usabilidade
- [ ] Ajustar interface
9. RELATÓRIOS E GESTÃO

Para o MVP, manteria apenas o essencial.

Usuário
- [ ] Minhas reservas
Gestor
- [ ] Reservas por sala
- [ ] Ocupação por sala
- [ ] Ocupação por período
Administração
- [ ] Salas cadastradas
- [ ] Salas ativas/inativas
- [ ] Reservas
- [ ] Cancelamentos
10. GOVERNANÇA E DOCUMENTAÇÃO

Como esse projeto também é um case de aprendizado em ServiceNow, essa parte é importante.

- [ ] Documentar arquitetura
- [ ] Documentar tabelas
- [ ] Documentar campos
- [ ] Documentar relacionamentos
- [ ] Documentar Roles
- [ ] Documentar ACLs
- [ ] Documentar Business Rules
- [ ] Documentar Flows
- [ ] Documentar Notifications
- [ ] Documentar Import Sets
- [ ] Documentar Transform Maps
- [ ] Documentar catálogo
- [ ] Documentar critérios de aceite
- [ ] Documentar testes
- [ ] Documentar decisões arquiteturais
Visão final do nosso projeto

Eu organizaria o desenvolvimento do MVP nesta sequência:

1. REQUISITOS
       ↓
2. PROCESSO
       ↓
3. MODELO DE DADOS
       ↓
4. SEGURANÇA
       ↓
5. CATÁLOGO / INTERFACE
       ↓
6. BUSINESS RULES
       ↓
7. FLOW DESIGNER
       ↓
8. NOTIFICAÇÕES
       ↓
9. CARGA DO INVENTÁRIO
       ↓
10. TESTES / ATF
       ↓
11. HOMOLOGAÇÃO
       ↓
12. MVP DE RESERVA DE SALAS
