
```mermaid
classDiagram
    class Agenda {
      +id: UUID
      +data: Date
      +descricao: string
    }

    class Sala {
      +id: UUID
      +numero: int
      +nome: string
    }

    class Especialidade {
      +id: UUID
      +nome: string
    }

    class Paciente {
      +id: UUID
      +nome: string
      +documento?: string
      +contato?: string
    }

    class Convenio {
      +id: UUID
      +nome: string
      +codigoANS?: string
    }

    class TimeSlot {
      +id: UUID
      +horaInicio: Time
      +horaFim: Time
      +periodo: enum {Manhã, Tarde}
    }

    class Agendamento {
      +id: UUID
      +status: enum {Novo, Confirmado, Cancelado, Atendido, Faltou}
      +observacoes?: string
      +criadoEm: DateTime
    }

    Agenda "1" o-- "many" TimeSlot : possui >
    Sala "1" --> "1" Especialidade : é de >
    Paciente "many" --> "1" Convenio : possui >
    Sala "1" o-- "many" Agendamento : realiza >
    Paciente "1" o-- "many" Agendamento : marca >
    TimeSlot "1" o-- "many" Agendamento : ocupa >
    Agenda "1" o-- "many" Agendamento : agrega >
    Especialidade "1" o-- "many" Sala : aloca >

```
