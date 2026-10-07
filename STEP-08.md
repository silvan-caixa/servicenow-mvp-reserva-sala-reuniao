# STEP 08 — Criar regras de horário e reserva

## Objetivo

Controlar quando uma sala pode ser reservada e iniciar o processo de reserva a partir da consulta de disponibilidade.

## 1. Seleção da sala e início da reserva

- [ ] Permitir seleção de uma única sala disponível
- [ ] Capturar a sala selecionada
- [ ] Armazenar o `sys_id` da sala selecionada
- [ ] Criar ação/botão "Reservar sala"
- [ ] Abrir formulário/processo de reserva
- [ ] Preencher automaticamente a sala selecionada
- [ ] Preencher automaticamente a data da consulta
- [ ] Preencher automaticamente o horário inicial
- [ ] Preencher automaticamente a quantidade de participantes
- [ ] Validar novamente a disponibilidade antes de gravar
- [ ] Impedir reserva caso a sala tenha sido ocupada nesse intervalo

## 2. Regras de horário

- [ ] Definir horário inicial
- [ ] Definir horário final
- [ ] Definir intervalo de reserva
- [ ] Definir dias permitidos
- [ ] Tratar finais de semana
- [ ] Tratar feriados
- [ ] Avaliar regras por unidade
- [ ] Configurar timezone
- [ ] Testar diferentes fusos horários

## Exemplo de intervalos

```text
08:00
08:30
09:00
09:30
10:00
10:30
...

## 3. Validações da reserva

- [ ] Horário inicial dentro do horário permitido
- [ ] Horário final dentro do horário permitido
- [ ] Horário final maior que horário inicial
- [ ] Duração mínima respeitada
- [ ] Duração máxima respeitada
- [ ] Não permitir reserva no passado
- [ ] Não permitir conflito de reservas
- [ ] Não permitir reserva de sala inativa
- [ ] Não permitir reserva acima da capacidade da sala
- [ ] Não permitir reserva fora dos dias permitidos

## 4. Critério de conclusão

- [ ] Usuário consegue selecionar uma sala disponível
- [ ] Sistema inicia a reserva com os dados da consulta
- [ ] Sistema impede reservas fora dos horários permitidos
- [ ] Sistema impede conflitos de horário
- [ ] Sistema impede reserva de sala indisponível
- [ ] Sistema grava uma reserva válida na tabela `Reserva`
