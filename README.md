# 🏢 Gestão de Salas de Reunião — ServiceNow

## 📋 Sobre o projeto

Este projeto tem como objetivo desenvolver, utilizando a plataforma **ServiceNow**, uma solução moderna para **reserva e gestão de salas de reunião**, substituindo gradualmente o modelo atualmente utilizado pelo sistema legado de agendamento de salas.

O projeto faz parte de uma iniciativa de desenvolvimento e capacitação em ServiceNow, utilizando um **caso de uso real** para aplicar conceitos de desenvolvimento de aplicações, automação, segurança, integração, experiência do usuário e governança da plataforma.

A proposta não é simplesmente reproduzir o sistema existente, mas **preservar suas principais regras de negócio e melhorar a experiência do usuário**, utilizando os recursos nativos e boas práticas da plataforma ServiceNow.

---

## 🎯 Objetivo

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

## 🏛️ Cenário atual

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

## 💡 Proposta

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

# 🚀 Escopo do MVP

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

# 🧩 Arquitetura conceitual

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
