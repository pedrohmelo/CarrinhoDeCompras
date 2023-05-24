# Carrinho de Compras - Java
Este repositório contém um código bem simples em Java de um sistema de carrinho de compras

## Execução
O usuário deve inserir o limite do cartão de crédito, descrição e valor do produto. Feito isso, o produto será adicionado no carrinho de compras até o usuário sair do sistema ou o limite do cartão de crédito estourar.
Não há nada de complexo no código, o único detalhe que vale ressaltar é a implementação dos seguintes métodos:

1. Construtor para inserir o produto no carrinho:
```
public boolean lancaCompra(Compra compra){
        if(this.saldo > compra.getValor()){
            this.saldo -= compra.getValor();
            this.compras.add(compra);
            return true;
        } else return false;
    }
```

2. Método para buscar e imprimir cada produto do carrinho:
```
@Override
    public String toString() {
        return "Compra: descrição = " + descricao + '\'' + " valor = " + valor;
    }
```
3. Ordenando a impressão dos produtos por ordem de menor valor dos produtos:
```
@Override
    public int compareTo(Compra outraCompra) {
        return Double.valueOf(this.valor).compareTo(Double.valueOf(outraCompra.valor));
    }
```
