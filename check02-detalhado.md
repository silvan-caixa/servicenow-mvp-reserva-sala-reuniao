# CHECKLIST TÉCNICO DETALHADO

## Este será o checklist que eu usaria durante o desenvolvimento do MVP.

## 1. ANALYZE & DESIGN BUSINESS LOGIC
### 1.1 Definição do MVP
- [ ] Definir formalmente o MVP
- [ ] Documentar o que está dentro do MVP
- [ ] Documentar o que está fora do MVP
- [ ] Definir critérios de aceite
- [ ] Definir resultado esperado: empregado consegue reservar uma sala disponível
## Dentro do MVP
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
## Fora do MVP
- [ ] Vagas de veículos elétricos
- [ ] Vagas de visitantes
- [ ] Outros espaços
- [ ] Equipamentos
- [ ] Agendamento de outros serviços
- [ ] Integração completa com Outlook/Teams
- [ ] Outros canais de reserva
## 1.2 Personas / atores
- [ ] Empregado / solicitante
- [ ] Gestor da sala
- [ ] Administrador da aplicação
- [ ] Gestor da unidade/centralizadora
- [ ] Sistema/integração responsável pelo inventário
## 1.3 Processo de reserva

## Definir o processo completo:

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

## Checklist:

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

## 1.4 Regras de negócio
### Disponibilidade
☐ Sala disponível pode ser reservada
☐ Sala ocupada não pode ser reservada
☐ Dois usuários não podem reservar o mesmo horário
☐ Reserva deve considerar data + horário + sala
☐ Intervalos de 30 minutos
☐ Definir horário inicial permitido
☐ Definir horário final permitido
Capacidade
☐ Informar número de participantes
☐ Consultar capacidade da sala
☐ Impedir reserva quando participantes > capacidade
☐ Informar ao usuário o motivo do bloqueio
Sala
☐ Sala ativa pode ser reservada
☐ Sala inativa não pode ser reservada
☐ Sala em manutenção não pode ser reservada
☐ Sala bloqueada não pode ser reservada
Reserva
☐ Criar
☐ Alterar
☐ Cancelar
☐ Consultar
☐ Histórico
2. DESIGN & BUILD DATA MODEL

Aqui está uma parte importante do projeto.

2.1 Arquitetura proposta

Eu sugiro que o modelo seja construído sem estender a CMDB para representar salas, seguindo a preocupação levantada na reunião sobre não poluir a CMDB.

A arquitetura inicial pode ser:

'''text
                Gestão de Espaços
                       │
                       ├── Unidade
                       │
                       ├── Prédio
                       │
                       ├── Andar
                       │
                       ├── Sala
                       │
                       └── Reserva
'''
2.2 Tabelas
Tabela: Unidade
☐ Criar tabela Unidade
☐ Código da unidade
☐ Nome
☐ Região/centralizadora
☐ Status
☐ Localização
☐ Fuso horário
