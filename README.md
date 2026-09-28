# Gestão de Salas de Reunião — ServiceNow

## Sobre o projeto

Este projeto tem como objetivo desenvolver, utilizando a plataforma **ServiceNow**, uma solução moderna para **reserva e gestão de salas de reunião**, substituindo gradualmente o modelo atualmente utilizado pelo sistema legado de agendamento de salas.

O projeto faz parte de uma iniciativa de desenvolvimento e capacitação em ServiceNow, utilizando um **caso de uso real** para aplicar conceitos de desenvolvimento de aplicações, automação, segurança, integração, experiência do usuário e governança da plataforma.

A proposta não é simplesmente reproduzir o sistema existente, mas **preservar suas principais regras de negócio e melhorar a experiência do usuário**, utilizando os recursos nativos e boas práticas da plataforma ServiceNow.

---

## Objetivo

Criar um **MVP (Minimum Viable Product)** para permitir que empregados possam:

- Consultar a disponibilidade de salas;
- Localizar salas por unidade, prédio e andar;
- Informar a quantidade de participantes;
- Consultar características e capacidade das salas;
- Realizar reservas;
- Alterar reservas;
- Cancelar reservas;
- Receber notificações relacionadas às reservas.

Além disso, a solução deverá permitir que áreas responsáveis façam a **gestão do inventário e disponibilidade das salas**, incluindo bloqueios e períodos de manutenção.

---

## Cenário atual

O processo atual é realizado por meio de um sistema legado de agendamento de salas.

Entre as funcionalidades existentes estão:

- Consulta de disponibilidade;
- Agendamento de salas;
- Salas compartilhadas entre unidades;
- Visualização da ocupação por horário;
- Intervalos de agendamento;
- Relatórios de programação e ocupação;
- Controle de salas disponíveis e ocupadas.

Embora o sistema atenda ao processo básico de reserva, foram identificadas oportunidades de evolução relacionadas à:

- Experiência do usuário;
- Gestão das salas;
- Informações disponíveis sobre os ambientes;
- Bloqueio de salas para manutenção;
- Regras de negócio;
- Autonomia das unidades responsáveis;
- Integração com outras fontes de informação;
- Manutenção e evolução da solução.

---

## Proposta

A nova solução será desenvolvida no ServiceNow buscando:

- Modernizar a experiência de reserva;
- Simplificar a navegação do usuário;
- Centralizar o processo de reserva;
- Automatizar regras de negócio;
- Melhorar a gestão das salas;
- Permitir maior autonomia às áreas responsáveis;
- Garantir rastreabilidade das operações;
- Preparar a arquitetura para futuras expansões.

A aplicação deverá ser construída de forma **modular, governável e extensível**, permitindo que novos tipos de espaços possam ser incorporados futuramente sem comprometer a arquitetura inicial.

---

# Escopo do MVP

O primeiro MVP será **exclusivamente voltado para reserva de salas de reunião**.

### Dentro do MVP

- Cadastro/inventário de salas;
- Unidade;
- Prédio;
- Andar;
- Sala;
- Capacidade;
- Características da sala;
- Consulta de disponibilidade;
- Reserva;
- Alteração de reserva;
- Cancelamento;
- Controle de conflitos;
- Bloqueio de salas;
- Manutenção;
- Regras de acesso;
- Notificações;
- Auditoria;
- Minhas reservas;
- Relatórios básicos;
- Interface integrada ao Employee Center.

### Fora do MVP

Os seguintes itens poderão ser avaliados em futuras evoluções:

- Vagas para veículos elétricos;
- Vagas para visitantes;
- Outros tipos de espaços;
- Reserva de equipamentos;
- Outros serviços de agendamento;
- Integração completa com Outlook/Microsoft Graph;
- Integrações adicionais com outros sistemas corporativos.

---

# Arquitetura conceitual

A solução deverá possuir uma estrutura semelhante a:

```text
                    Gestão de Espaços
                           │
                           ▼
                  Reserva de Salas
                           │
          ┌────────────────┼────────────────┐
          │                │                │
          ▼                ▼                ▼
       Unidades         Prédios          Reservas
                           │                │
                           ▼                │
                         Andares            │
                           │                │
                           ▼                │
                         Salas ─────────────┘
```

# 🚀 Steps de Desenvolvimento — MVP Reserva de Salas de Reunião

> Projeto desenvolvido em ServiceNow para substituir o processo atual de reserva de salas de reunião.

---

# STEP 01 — Levantamento e definição do MVP

## Objetivo

Definir claramente o que será desenvolvido na primeira versão da aplicação.

## Atividades

- [ ] Documentar o processo atual
- [ ] Identificar os principais problemas do sistema atual
- [ ] Identificar os usuários envolvidos
- [ ] Identificar responsáveis pelas salas
- [ ] Identificar regras atuais de reserva
- [ ] Identificar regras de cancelamento
- [ ] Identificar regras de alteração
- [ ] Identificar regras de bloqueio
- [ ] Definir funcionalidades do MVP
- [ ] Definir funcionalidades fora do MVP
- [ ] Validar escopo com o negócio

## Entregáveis

- Documento de escopo
- Lista de requisitos
- Lista de regras de negócio
- Definição do MVP

## Critério de conclusão

- [ ] Escopo aprovado pelo negócio

---

# STEP 02 — Criar a aplicação ServiceNow

## Objetivo

Criar a estrutura inicial da aplicação.

## Atividades

- [ ] Criar aplicação Scoped
- [ ] Definir nome da aplicação
- [ ] Definir nome técnico
- [ ] Definir descrição
- [ ] Definir Application Menu
- [ ] Criar módulos iniciais
- [ ] Definir padrão de nomenclatura
- [ ] Validar escopo da aplicação

## Entregáveis

```text
Application
├── Application Menu
├── Modules
└── Application Scope
```

## Critério de conclusão
 - [ ] Aplicação criada
 - [ ] Scope validado
 - [ ] Menu criado

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

# STEP 04 — Criar modelo de dados
## Objetivo

Criar a estrutura de dados necessária para o MVP.

## Atividades
Sala
- [ ] Criar tabela de sala
- [ ] Número/código
- [ ] Nome
- [ ] Unidade
- [ ] Prédio
- [ ] Andar
- [ ] Capacidade
- [ ] Características
- [ ] Responsável
- [ ] Status
- [ ] Ativo
Reserva
- [ ] Criar tabela de reserva
- [ ] Número
- [ ] Solicitante
- [ ] Sala
- [ ] Data
- [ ] Hora inicial
- [ ] Hora final
- [ ] Quantidade de participantes
- [ ] Assunto
- [ ] Observações
- [ ] Estado
- [ ] Motivo do cancelamento

Bloqueio
- [ ] Criar tabela de bloqueio
- [ ] Sala
- [ ] Data inicial
- [ ] Data final
- [ ] Hora inicial
- [ ] Hora final
- [ ] Motivo
- [ ] Responsável
- [ ] Estado

## Entregáveis
- [ ] Sala
- [ ] Reserva
- [ ] Bloqueio

 ## Critério de conclusão
 - [ ] Tabelas criadas
 - [ ] Campos criados
 - [ ] Referências configuradas
 - [ ] Relacionamentos testados

# STEP 05 — Criar cadastro de salas
## Objetivo

Permitir administrar o inventário de salas.

## Atividades
- [ ] Criar formulário
- [ ] Criar lista
- [ ] Criar campos obrigatórios
- [ ] Criar validações
- [ ] Criar identificação única
- [ ] Definir capacidade
- [ ] Definir características
- [ ] Definir responsável
- [ ] Definir status
- [ ] Criar ativação/inativação
- [ ] Testar cadastro

## Entregável
Cadastro de Salas
## Critério de conclusão
- [ ] Sala pode ser cadastrada
- [ ]  Sala pode ser alterada
- [ ]  Sala pode ser inativada
- [ ]  Dados obrigatórios são validados

# STEP 06 — Criar carga do inventário
## Objetivo

Preparar a importação do inventário corporativo de salas.

## Atividades
- [ ] Definir fonte do inventário
- [ ] Definir formato
- [ ] Criar Import Set
- [ ] Criar tabela de importação
- [ ] Criar Transform Map
- [ ] Mapear campos
- [ ] Definir Coalesce
- [ ] Tratar novos registros
- [ ] Tratar registros existentes
- [ ] Tratar registros inativos
- [ ] Testar carga
- [ ] Validar dados importados

## Entregáveis
```text
Arquivo
   ↓
Import Set
   ↓
Transform Map
   ↓
Tabela de Salas
```
## Critério de conclusão
- [ ] Inventário carregado corretamente

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
## Critério de conclusão
- [ ] Usuário consegue consultar salas disponíveis

# STEP 08 — Criar regras de horário
## Objetivo

Controlar quando uma sala pode ser reservada.

## Atividades
- [ ] Definir horário inicial
- [ ] Definir horário final
- [ ] Definir intervalo de reserva
- [ ] Definir dias permitidos
- [ ] Tratar finais de semana
- [ ] Tratar feriados
- [ ] Avaliar regras por unidade
- [ ] Configurar timezone
- [ ] Testar diferentes fusos horários

## Exemplo
```text
08:00
08:30
09:00
09:30
10:00
10:30
...
```

 ## Critério de conclusão
- [ ] Sistema impede reservas fora dos horários permitidos

# STEP 09 — Criar controle de conflitos
## Objetivo

Impedir duas reservas simultâneas para a mesma sala.

## Atividades
 Criar regra de conflito
- [ ] Comparar sala
- [ ] Comparar data
- [ ] Comparar hora inicial
- [ ] Comparar hora final
- [ ] Detectar sobreposição
- [ ] Permitir horários consecutivos
- [ ] Impedir sobreposição parcial
- [ ] Criar mensagem de erro
- [ ] Testar concorrência

## Exemplo
```text
Reserva existente
10:00 ───────── 11:00

Nova reserva
10:30 ───────── 11:30

❌ CONFLITO
```

Exemplo permitido

```text
Reserva existente
10:00 ───────── 11:00

Nova reserva
11:00 ───────── 12:00

✅ PERMITIDO
```

## Critério de conclusão
- [ ] Sistema não permite reservas conflitantes

# STEP 10 — Criar controle de capacidade
## Objetivo

Garantir que a quantidade de participantes seja compatível com a capacidade da sala.

## Atividades
- [ ] Recuperar capacidade da sala
- [ ] Informar participantes
- [ ] Comparar participantes x capacidade
- [ ] Bloquear excesso
- [ ] Criar mensagem de erro
- [ ] Testar capacidade exata
- [ ] Testar capacidade excedida

## Exemplo
```text
Sala: Sala 01
Capacidade: 10

Participantes: 8

✅ Reserva permitida
```
```text
Sala: Sala 01
Capacidade: 10

Participantes: 15

❌ Reserva não permitida
```

## Critério de conclusão
- [ ] Capacidade validada automaticamente

# STEP 11 — Criar bloqueio de salas
## Objetivo

Permitir que responsáveis bloqueiem uma sala temporariamente.

## Atividades
- [ ] Criar formulário
- [ ] Selecionar sala
- [ ] Informar período
- [ ] Informar motivo
- [ ] Criar bloqueio
- [ ] Impedir novas reservas
- [ ] Exibir sala como indisponível
- [ ] Registrar responsável
- [ ] Registrar histórico
- [ ] Definir tratamento de reservas existentes

## Exemplos
 - [ ] Manutenção
 - [ ] Evento
 - [ ] Reforma
 - [ ] Indisponibilidade
 - [ ] Restrição operacional

## Critério de conclusão
- [ ] Sala bloqueada não pode ser reservada

# STEP 12 — Criar Business Rules
## Objetivo

Implementar as validações de negócio no servidor.

## Business Rules
### Reserva
- [ ] Validar sala ativa
- [ ] Validar disponibilidade
- [ ] Validar conflito
- [ ] Validar capacidade
- [ ] Validar horário
- [ ] Validar bloqueio
### Alteração
- [ ] Revalidar disponibilidade
- [ ] Revalidar conflito
- [ ] Revalidar capacidade
- [ ] Registrar alteração
### Cancelamento
- [ ] Validar permissão
- [ ] Validar antecedência
- [ ] Atualizar estado
- [ ] Registrar motivo

## Critério de conclusão
- [ ] Todas as regras críticas executadas no servidor

# STEP 13 — Criar Flow Designer
## Objetivo

Automatizar o ciclo de vida da reserva.

## Fluxo de criação
```text
Reserva criada
      ↓
Validar dados
      ↓
Validar disponibilidade
      ↓
Criar reserva
      ↓
Atualizar estado
      ↓
Enviar confirmação
```
## Fluxo de alteração
```text
Reserva alterada
      ↓
Validar dados
      ↓
Validar disponibilidade
      ↓
Atualizar reserva
      ↓
Enviar notificação
```

## Fluxo de cancelamento
```text
Reserva cancelada
      ↓
Atualizar estado
      ↓
Liberar horário
      ↓
Enviar notificação
```
## Checklist
- [ ] Criar Flow de criação
- [ ] Criar Flow de alteração
- [ ] Criar Flow de cancelamento
- [ ] Criar Flow de bloqueio
- [ ] Testar automações

# STEP 14 — Criar notificações
## Objetivo

Informar os usuários sobre alterações nas reservas.

## Notificações
- [ ] Reserva criada
- [ ] Reserva alterada
- [ ] Reserva cancelada
- [ ] Sala bloqueada
- [ ] Reserva afetada por bloqueio
## Conteúdo
- [ ] Número da reserva
- [ ] Sala
- [ ] Prédio
- [ ] Data
- [ ] Horário
- [ ] Solicitante
- [ ] Assunto
- [ ] Observações
## Critério de conclusão
- [ ] Notificações recebidas corretamente

# STEP 15 — Criar segurança e permissões
## Objetivo

Controlar o acesso aos dados e funcionalidades.

## Usuário
- [ ] Consultar salas
- [ ] Consultar disponibilidade
- [ ] Criar reserva
- [ ] Consultar próprias reservas
- [ ] Alterar próprias reservas
- [ ] Cancelar próprias reservas
## Gestor
- [ ] Gerenciar salas
- [ ] Bloquear salas
- [ ] Consultar reservas
- [ ] Administrar disponibilidade
## Administrador
- [ ] Administração completa
## ACL
- [ ] Read
- [ ] Create
- [ ] Write
- [ ] Delete
- [ ] Testar acesso por perfil
## Critério de conclusão
- [ ] Usuários só acessam o que é permitido

# STEP 16 — Criar experiência no Employee Center
## Objetivo

Disponibilizar a funcionalidade para os empregados.

## Atividades
- [ ] Criar entrada no Employee Center
- [ ] Criar categoria
- [ ] Criar item "Reserva de Sala"
- [ ] Criar descrição
- [ ] Criar ícone
- [ ] Criar navegação
- [ ] Criar acesso às minhas reservas

## Fluxo
```text
Employee Center
      ↓
Gestão de Espaços
      ↓
Reserva de Sala
      ↓
Consultar disponibilidade
      ↓
Reservar
```
## Critério de conclusão
- [ ] Usuário consegue iniciar uma reserva pelo Employee Center

# STEP 17 — Criar interface de disponibilidade
## Objetivo

Criar uma experiência simples para visualizar as salas.

## Atividades
- [ ] Criar tela de consulta
- [ ] Criar filtros
- [ ] Exibir salas
- [ ] Exibir capacidade
- [ ] Exibir características
- [ ] Exibir horários
- [ ] Exibir disponibilidade
- [ ] Exibir bloqueios
- [ ] Permitir seleção

## Exemplo
```text
Sala              08:00  08:30  09:00  09:30  10:00

Sala 01 - 12      🟢     🟢     🔴     🟢     🟢
Sala 02 - 06      🟢     🟢     🟢     🟢     🔴
Sala 03 - 10      🔴     🔴     🟢     🟢     🟢
Legenda
🟢 Disponível
🔴 Ocupado
⚫ Bloqueado
```
## Critério de conclusão
- [ ] Usuário identifica rapidamente os horários disponíveis

# STEP 18 — Criar "Minhas Reservas"
## Objetivo

Permitir que o usuário acompanhe suas reservas.

## Atividades
- [ ] Criar lista de reservas
- [ ] Exibir reservas futuras
- [ ] Exibir reservas realizadas
- [ ] Exibir reservas canceladas
- [ ] Visualizar detalhes
- [ ] Alterar reserva
- [ ] Cancelar reserva
## Informações
- [ ] Número
- [ ] Sala
- [ ] Data
- [ ] Horário
- [ ] Status
- [ ] Assunto
## Critério de conclusão
- [ ] Usuário consegue gerenciar suas reservas

# STEP 19 — Criar relatórios
## Objetivo

Disponibilizar indicadores sobre utilização das salas.

## Relatórios
- [ ] Reservas por sala
- [ ] Reservas por unidade
- [ ] Reservas por prédio
- [ ] Reservas por período
- [ ] Ocupação
- [ ] Cancelamentos
- [ ] Salas mais utilizadas
- [ ] Salas menos utilizadas
## Dashboard
- [ ] Total de reservas
- [ ] Salas disponíveis
- [ ] Salas bloqueadas
- [ ] Taxa de ocupação
- [ ] Cancelamentos
- [ ] Reservas por unidade
- [ ] Reservas por prédio
## Critério de conclusão
- [ ] Indicadores disponíveis para gestão

# STEP 20 — Testes funcionais
## Objetivo

Validar todas as funcionalidades do MVP.

## Reserva
- [ ] Criar reserva válida
- [ ] Criar reserva inválida
- [ ] Reservar sala ocupada
- [ ] Reservar sala bloqueada
- [ ] Reservar sala inativa
- [ ] Reservar fora do horário
- [ ] Reservar acima da capacidade
- [ ] Alterar reserva
- [ ] Cancelar reserva
## Usuários
- [ ] Testar usuário comum
- [ ] Testar gestor
- [ ] Testar administrador
- [ ] Testar usuário sem permissão
## Concorrência
- [ ] Dois usuários reservando mesma sala
- [ ] Mesmo horário
- [ ] Horários sobrepostos
- [ ] Alteração simultânea
## Critério de conclusão
- [ ] Casos críticos aprovados

# STEP 21 — Automated Test Framework
## Objetivo

Automatizar os principais testes.

## ATFs
- [ ] Criar reserva
- [ ] Consultar disponibilidade
- [ ] Validar conflito
- [ ] Validar capacidade
- [ ] Validar bloqueio
- [ ] Validar sala inativa
- [ ] Alterar reserva
- [ ] Cancelar reserva
- [ ] Criar bloqueio
- [ ] Validar segurança
## Critério de conclusão
- [ ] Principais cenários automatizados

# STEP 22 — Auditoria e rastreabilidade
## Objetivo

Garantir rastreabilidade das operações.

## Registrar
- [ ] Quem criou
- [ ] Data de criação
- [ ] Quem alterou
- [ ] Data da alteração
- [ ] Quem cancelou
- [ ] Data do cancelamento
- [ ] Motivo do cancelamento
- [ ] Alterações de horário
- [ ] Alterações de sala
- [ ] Bloqueios
## Critério de conclusão
- [ ] Histórico das principais operações disponível

# STEP 23 — Tratamento de erros
## Objetivo

Garantir mensagens claras e recuperação adequada.

## Atividades
- [ ] Criar mensagens amigáveis
- [ ] Tratar conflito
- [ ] Tratar sala indisponível
- [ ] Tratar sala inexistente
- [ ] Tratar capacidade excedida
- [ ] Tratar erro de integração
- [ ] Tratar erro de importação
- [ ] Registrar logs
- [ ] Definir reprocessamento
## Critério de conclusão
- [ ] Erros críticos tratados

# STEP 24 — Homologação
## Objetivo

Validar o MVP com os usuários do negócio.

## Homologar
- [ ] Cadastro de salas
- [ ] Consulta
- [ ] Disponibilidade
- [ ] Reserva
- [ ] Alteração
- [ ] Cancelamento
- [ ] Bloqueio
- [ ] Notificações
- [ ] Relatórios
- [ ] Segurança
- [ ] Employee Center
## Evidências
- [ ] Registrar testes
- [ ] Registrar evidências
- [ ] Registrar problemas
- [ ] Corrigir problemas
- [ ] Reexecutar testes
- [ ] Obter aceite
## Critério de conclusão
- [ ] MVP homologado

# STEP 25 — Implantação
## Objetivo

Disponibilizar o MVP para utilização.

## Atividades
- [ ] Validar aplicação
- [ ] Validar configurações
- [ ] Validar roles
- [ ] Validar ACLs
- [ ] Validar dados
- [ ] Validar notificações
- [ ] Validar integrações
- [ ] Executar testes finais
- [ ] Executar deployment
- [ ] Validar ambiente
- [ ] Registrar versão
## Critério de conclusão
- [ ] MVP implantado

# STEP 26 — Documentação
## Objetivo

Documentar a solução para manutenção e evolução.

## Documentar
- [ ] Arquitetura
- [ ] Modelo de dados
- [ ] Tabelas
- [ ] Campos
- [ ] Relacionamentos
- [ ] Business Rules
- [ ] Flows
- [ ] Notifications
- [ ] Roles
- [ ] ACLs
- [ ] Import Sets
- [ ] Transform Maps
- [ ] Integrações
- [ ] ATFs
- [ ] Regras de negócio
- [ ] Procedimentos operacionais
## Estrutura sugerida
```text
docs/
├── 01-escopo.md
├── 02-arquitetura.md
├── 03-modelo-dados.md
├── 04-regras-negocio.md
├── 05-flows.md
├── 06-seguranca.md
├── 07-integracoes.md
├── 08-testes.md
└── 09-implantacao.md
```
# STEP 27 — Encerramento do MVP
## Critérios finais
- [ ] Cadastro de salas funcionando
- [ ] Consulta de disponibilidade funcionando
- [ ] Reserva funcionando
- [ ] Alteração funcionando
- [ ] Cancelamento funcionando
- [ ] Controle de conflitos funcionando
- [ ] Controle de capacidade funcionando
- [ ] Bloqueio funcionando
- [ ] Business Rules funcionando
- [ ] Flows funcionando
- [ ] Notifications funcionando
- [ ] Segurança funcionando
- [ ] Employee Center funcionando
- [ ] Relatórios funcionando
- [ ] Testes concluídos
- [ ] ATFs principais concluídos
- [ ] Homologação concluída
- [ ] Documentação concluída
- [ ] Deployment concluído

# STEP 28 — Evoluções futuras

Estas funcionalidades não fazem parte do MVP inicial.

## Gestão de Espaços
- Vagas para veículos elétricos
- Vagas de visitantes
- Outros espaços
- Equipamentos
- Recursos compartilhados
- Outros tipos de reserva
## Integrações
- SAP
- Outlook
- Microsoft Graph
- Teams
- Outros sistemas corporativos
## Gestão
- Dashboard executivo
- Indicadores avançados
- Taxa de ocupação
- Análise de utilização
- Otimização de espaços
## Fluxo geral do projeto
```text
STEP 01
Levantamento
   ↓
STEP 02
Criar aplicação
   ↓
STEP 03
Arquitetura
   ↓
STEP 04
Modelo de dados
   ↓
STEP 05
Cadastro de salas
   ↓
STEP 06
Importação
   ↓
STEP 07
Disponibilidade
   ↓
STEP 08
Horários
   ↓
STEP 09
Conflitos
   ↓
STEP 10
Capacidade
   ↓
STEP 11
Bloqueios
   ↓
STEP 12
Business Rules
   ↓
STEP 13
Flow Designer
   ↓
STEP 14
Notificações
   ↓
STEP 15
Segurança
   ↓
STEP 16
Employee Center
   ↓
STEP 17
Interface
   ↓
STEP 18
Minhas Reservas
   ↓
STEP 19
Relatórios
   ↓
STEP 20
Testes
   ↓
STEP 21
ATF
   ↓
STEP 22
Auditoria
   ↓
STEP 23
Tratamento de erros
   ↓
STEP 24
Homologação
   ↓
STEP 25
Implantação
   ↓
STEP 26
Documentação
   ↓
STEP 27
MVP CONCLUÍDO
   ↓
STEP 28
EVOLUÇÕES
```
## Resultado esperado

Ao final dos Steps 01 a 27, teremos um MVP funcional de Reserva de Salas de Reunião em ServiceNow, disponível pelo Employee Center, permitindo:

- consulta de salas;
- consulta de disponibilidade;
- criação de reservas;
- alteração de reservas;
- cancelamento;
- controle de conflitos;
- controle de capacidade;
- bloqueio de salas;
- notificações;
- controle de acesso;
- relatórios;
- auditoria.

As funcionalidades de Gestão de Espaços serão desenvolvidas posteriormente, utilizando a arquitetura criada no MVP como base.


