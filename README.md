@startuml

class Usuario {
  - ID: int
  - Nome: string
  - Email: string
  - Tipo: string
  + Registar()
  + FazerLogin()
  + AdicionarAoCarrinho(Produto produto)
  + Comprar()
}

class Produto {
  - ID: int
  - Nome: string
  - Preço: float
  - Descrição: string
  + ExibirDetalhes()
}

class CarrinhoDeCompras {
  - Itens: list of Produto
  - Total: float
  + AdicionarItem(Produto produto)
  + RemoverItem(Produto produto)
  + CalcularTotal()
  + FinalizarCompra()
}

Usuario "1" -- "0..*" Produto: Tem
Usuario "1" -- "1" CarrinhoDeCompras: Possui
CarrinhoDeCompras "0..*" -- "0..*" Produto: Contém

@enduml
