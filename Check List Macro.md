# Checklist Geral — MVP Reserva de Salas de Reunião

> **Projeto:** Gestão de Salas de Reunião  
> **Plataforma:** ServiceNow  
> **Escopo:** MVP — Reserva de Salas de Reunião

---

## 1. Levantamento e Escopo

- [ ] Levantar requisitos funcionais
- [ ] Levantar requisitos não funcionais
- [ ] Validar processo atual
- [ ] Identificar atores envolvidos
- [ ] Identificar perfis de acesso
- [ ] Definir regras de negócio
- [ ] Definir critérios de aceite
- [ ] Validar escopo do MVP
- [ ] Documentar funcionalidades que ficarão fora do MVP

---

## 2. Arquitetura da Solução

- [ ] Definir arquitetura da aplicação
- [ ] Definir estrutura do aplicativo
- [ ] Definir estratégia de tabelas
- [ ] Avaliar utilização de tabelas nativas ServiceNow
- [ ] Definir relacionamentos entre entidades
- [ ] Definir estratégia de extensibilidade
- [ ] Validar arquitetura com a equipe técnica
- [ ] Documentar decisões arquiteturais

---

## 3. Banco de Dados / Modelo de Dados

- [ ] Definir modelo conceitual
- [ ] Definir entidades
- [ ] Criar tabelas necessárias
- [ ] Definir campos
- [ ] Definir tipos dos campos
- [ ] Definir relacionamentos
- [ ] Definir referências entre tabelas
- [ ] Definir campos obrigatórios
- [ ] Definir valores padrão
- [ ] Definir regras de integridade
- [ ] Validar modelo de dados

---

## 4. Cadastro e Gestão de Salas

- [ ] Definir cadastro de unidades
- [ ] Definir cadastro de prédios
- [ ] Definir cadastro de andares
- [ ] Definir cadastro de salas
- [ ] Definir capacidade das salas
- [ ] Definir características das salas
- [ ] Definir localização das salas
- [ ] Definir situação da sala
- [ ] Permitir ativação/inativação de salas
- [ ] Permitir bloqueio de salas
- [ ] Permitir manutenção de salas
- [ ] Definir responsável pela gestão das salas

---

## 5. Reserva de Sala

- [ ] Criar funcionalidade de consulta de disponibilidade
- [ ] Criar funcionalidade de reserva
- [ ] Selecionar data
- [ ] Selecionar horário
- [ ] Selecionar sala
- [ ] Informar quantidade de participantes
- [ ] Informar finalidade da reunião
- [ ] Permitir observações
- [ ] Validar disponibilidade
- [ ] Impedir conflito de reservas
- [ ] Validar capacidade da sala
- [ ] Criar confirmação da reserva
- [ ] Permitir alteração da reserva
- [ ] Permitir cancelamento da reserva
- [ ] Registrar histórico das alterações

---

## 6. Gestão de Horários

- [ ] Definir intervalo padrão de agendamento
- [ ] Definir horário inicial permitido
- [ ] Definir horário final permitido
- [ ] Definir regras por unidade
- [ ] Considerar diferenças de fuso horário
- [ ] Validar horários disponíveis
- [ ] Impedir reservas fora do horário permitido
- [ ] Permitir bloqueio de períodos
- [ ] Validar sobreposição de horários

---

## 7. Fluxos e Automação

- [ ] Mapear fluxo completo da reserva
- [ ] Criar fluxo de criação da reserva
- [ ] Criar validações automáticas
- [ ] Criar fluxo de alteração
- [ ] Criar fluxo de cancelamento
- [ ] Criar fluxo de bloqueio de sala
- [ ] Criar automações necessárias
- [ ] Definir condições dos fluxos
- [ ] Definir ações dos fluxos
- [ ] Testar automações

---

## 8. Regras de Negócio

- [ ] Criar regras para disponibilidade
- [ ] Criar regra para conflito de horários
- [ ] Criar regra para capacidade
- [ ] Criar regra para sala bloqueada
- [ ] Criar regra para sala em manutenção
- [ ] Criar regra para cancelamento
- [ ] Criar regra para alteração
- [ ] Criar regras de acesso
- [ ] Validar todas as regras de negócio

---

## 9. Segurança e Permissões

- [ ] Definir perfis de usuário
- [ ] Criar roles
- [ ] Definir permissões de consulta
- [ ] Definir permissões de criação
- [ ] Definir permissões de alteração
- [ ] Definir permissões de cancelamento
- [ ] Definir permissões de administração
- [ ] Criar ACLs
- [ ] Testar acesso por perfil
- [ ] Validar segurança da aplicação

---

## 10. Experiência do Usuário

- [ ] Definir jornada do usuário
- [ ] Criar protótipo da interface
- [ ] Definir identidade visual
- [ ] Definir navegação
- [ ] Criar acesso pelo Employee Center
- [ ] Criar opção "Reservar Sala"
- [ ] Criar consulta de disponibilidade
- [ ] Exibir informações da sala
- [ ] Simplificar processo de reserva
- [ ] Criar tela de minhas reservas
- [ ] Validar experiência do usuário

---

## 11. Notificações

- [ ] Definir eventos que geram notificações
- [ ] Criar notificação de reserva
- [ ] Criar notificação de alteração
- [ ] Criar notificação de cancelamento
- [ ] Criar notificações relacionadas a bloqueios
- [ ] Definir destinatários
- [ ] Definir conteúdo das mensagens
- [ ] Avaliar notificações via e-mail
- [ ] Avaliar notificações via Teams
- [ ] Testar notificações

---

## 12. Carga / Importação de Dados

- [ ] Identificar fonte do inventário de salas
- [ ] Definir formato da carga
- [ ] Definir campos de origem
- [ ] Definir campos de destino
- [ ] Criar mecanismo de importação
- [ ] Criar transformação dos dados
- [ ] Validar dados importados
- [ ] Definir rotina de atualização
- [ ] Testar carga inicial
- [ ] Testar atualização do inventário

---

## 13. Integrações

- [ ] Levantar integrações necessárias
- [ ] Avaliar integração com SAP
- [ ] Avaliar integração com arquivos de rede
- [ ] Avaliar APIs disponíveis
- [ ] Avaliar integração com Outlook
- [ ] Avaliar Microsoft Graph
- [ ] Avaliar integração com Teams
- [ ] Definir integrações que fazem parte do MVP
- [ ] Documentar integrações futuras

---

## 14. Relatórios

- [ ] Definir relatórios necessários
- [ ] Criar relatório de reservas
- [ ] Criar relatório por sala
- [ ] Criar relatório por unidade
- [ ] Criar relatório de ocupação
- [ ] Criar relatório de cancelamentos
- [ ] Avaliar dashboard
- [ ] Validar informações dos relatórios

---

## 15. Testes

- [ ] Criar plano de testes
- [ ] Criar cenários de teste
- [ ] Testar criação de reserva
- [ ] Testar alteração de reserva
- [ ] Testar cancelamento
- [ ] Testar conflito de horários
- [ ] Testar capacidade da sala
- [ ] Testar sala bloqueada
- [ ] Testar sala em manutenção
- [ ] Testar permissões
- [ ] Testar notificações
- [ ] Criar testes automatizados com ATF
- [ ] Corrigir inconsistências encontradas

---

## 16. Homologação

- [ ] Disponibilizar MVP para homologação
- [ ] Validar funcionalidades com o negócio
- [ ] Validar regras de negócio
- [ ] Validar experiência do usuário
- [ ] Validar dados
- [ ] Validar segurança
- [ ] Registrar ajustes necessários
- [ ] Implementar correções
- [ ] Realizar homologação final
- [ ] Obter aprovação do MVP

---

## 17. Implantação

- [ ] Preparar ambiente de produção
- [ ] Validar configurações
- [ ] Validar dados
- [ ] Validar roles e ACLs
- [ ] Validar notificações
- [ ] Executar testes finais
- [ ] Realizar implantação
- [ ] Validar aplicação em produção
- [ ] Liberar utilização pelos usuários

---

## 18. Documentação

- [ ] Documentar requisitos
- [ ] Documentar arquitetura
- [ ] Documentar modelo de dados
- [ ] Documentar tabelas
- [ ] Documentar regras de negócio
- [ ] Documentar flows
- [ ] Documentar Business Rules
- [ ] Documentar roles e ACLs
- [ ] Documentar integrações
- [ ] Documentar testes
- [ ] Documentar critérios de aceite
- [ ] Atualizar README

---

# Critério de conclusão do MVP

O MVP será considerado concluído quando:

- [ ] Usuário conseguir consultar salas disponíveis
- [ ] Usuário conseguir realizar uma reserva
- [ ] Sistema impedir conflitos de horários
- [ ] Sistema validar as regras definidas
- [ ] Usuário conseguir consultar suas reservas
- [ ] Usuário conseguir alterar/cancelar uma reserva conforme as regras
- [ ] Gestor conseguir administrar as salas
- [ ] Gestor conseguir bloquear salas
- [ ] Notificações estiverem funcionando
- [ ] Controle de acesso estiver implementado
- [ ] Dados necessários estiverem disponíveis
- [ ] Testes principais estiverem concluídos
- [ ] MVP estiver homologado
- [ ] MVP estiver disponível para utilização

---

## Evoluções futuras

Itens identificados durante o levantamento, mas **fora do escopo inicial do MVP**:

- [ ] Reserva de vagas para veículos elétricos
- [ ] Reserva de vagas para visitantes
- [ ] Reserva de outros tipos de espaços
- [ ] Reserva de equipamentos
- [ ] Integração completa com Outlook
- [ ] Integração com Microsoft Graph
- [ ] Integração com Teams
- [ ] Novos serviços de agendamento
- [ ] Expansão para o conceito de Gestão de Espaços
