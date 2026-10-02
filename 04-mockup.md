## Visualização de disponibilidade

#### Manter a ideia do SIASR, mas modernizá-la:

#### Sistema atual
O usuário vê algo parecido com:

```text
Sala                  08:00  08:30  09:00  09:30  10:00
-----------------------------------------------------------
Sala 02 - 12 assentos    □      □      □      X      □
Sala 04 - 04 assentos    □      □      □      □      □
Sala 05 - 04 assentos    X      X      X      X      □
```
Funciona, mas exige que o usuário interprete uma grande quantidade de informação visual.

#### Nova experiência
```text
┌─────────────────────────────────────────────┐
│ Reservar sala                               │
│ Sala: [ Brasília ▼ ]                        │
│ Data: [ 25/09/2026             ▼ ]          │
│ Horário: [ 10:00 ▼ ] até [ 11:00 ▼ ]        │
│ Pessoas: [ 8 participantes     ▼ ]          │
│ Prédio: [ Edifício Sede        ▼ ]          │
│                                             │
│ Salas disponíveis                           │
│                                             │
│ Sala 02       12 lugares       ✓ Disponível │
│ Sala 04        4 lugares       ✕ Capacidade │
│ Sala 05        8 lugares       ✓ Disponível │
└─────────────────────────────────────────────┘
```
