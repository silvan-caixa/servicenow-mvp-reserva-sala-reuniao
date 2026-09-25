# 1. CHECKLIST GENÉRICO — MVP RESERVA DE SALA
## 1. Analyze & design business logic
- Problema de negócio
- Objetivos e resultados esperados
- Personas / stakeholders
- Entradas e saídas
- Processo de reserva
- Regras de negócio
2. Design & build data model
- Tabelas
- Campos
- Relacionamentos
- Dados iniciais das salas
- Modelo de reserva
3. Design & create user interface
- Employee Center
- Service Catalog
- Formulário de reserva
- Consulta de disponibilidade
- Minhas reservas
- Interface responsiva
4. Apply security
- Roles
- Access Control
- Permissões para reserva
- Permissões para gestão das salas
- Auditoria
5. Automate
- Flow Designer
- Regras de negócio
- Validação de disponibilidade
- Controle de conflitos
- Cancelamento
- Notificações
- Atualização de status
6. Integrate
- Carga do inventário de salas
- Fonte de dados das salas
- Import Set / Transform Map
- Integrações necessárias ao MVP
7. Test
- Testes funcionais
- Testes de regras de negócio
- Testes de segurança
- Testes de concorrência/conflito
- ATF
- Homologação
8. Enhance user interface
- Identidade visual Caixa
- Experiência do usuário
- Catálogo
- Busca de salas
- Visualização de disponibilidade
- Minhas reservas
- Mensagens e notificações
- Dashboard/relatórios básicos
2. CHECKLIST TÉCNICO DETALHADO

Este será o checklist que eu usaria durante o desenvolvimento do MVP.

1. ANALYZE & DESIGN BUSINESS LOGIC
1.1 Definição do MVP
- Definir formalmente o MVP
- Documentar o que está dentro do MVP
- Documentar o que está fora do MVP
- Definir critérios de aceite
- Definir resultado esperado: empregado consegue reservar uma sala disponível
Dentro do MVP
- Cadastro/inventário de salas
- Consulta de disponibilidade
- Reserva
- Cancelamento
- Alteração
- Controle de conflitos
- Capacidade da sala
- Localização da sala
- Notificação
- Gestão das salas
- Bloqueio/manutenção
- Auditoria
- Relatórios básicos
Fora do MVP
- Vagas de veículos elétricos
- Vagas de visitantes
- Outros espaços
- Equipamentos
- Agendamento de outros serviços
- Integração completa com Outlook/Teams
- Outros canais de reserva
1.2 Personas / atores
- Empregado / solicitante
- Gestor da sala
- Administrador da aplicação
- Gestor da unidade/centralizadora
- Sistema/integração responsável pelo inventário
1.3 Processo de reserva

Definir o processo completo:

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

Checklist:

- Definir início do processo
- Definir dados obrigatórios
- Definir busca da sala
- Definir seleção de horário
- Validar disponibilidade
- Validar capacidade
- Validar permissão
- Criar reserva
- Confirmar reserva
- Enviar notificação
