## Diagrama de Classes - Entidades

```mermaid
classDiagram
  class Instrumento {
    -int id
    -String nome
    -double preco
    -int quantidadeEstoque
    +vender(qtd: int): void
    +repor(qtd: int): void
  }

  class Funcionario {
    -int id
    -String nome
    -String cpf
    -String login
    -String senha
    +autenticar(): boolean
  }

  class Corda {
    -int numeroCordas
    -String tipoMadeira
  }

  Instrumento <|-- Corda
