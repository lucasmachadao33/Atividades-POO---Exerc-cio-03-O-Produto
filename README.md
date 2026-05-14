3-
public class Produto {

    // Atributos
    String nome;
    double preco;
    int quantidadeEstoque;

    // Método para vender produto
    void vender(int quantidade) {

        if (quantidade <= quantidadeEstoque) {
            quantidadeEstoque -= quantidade;
            System.out.println("Venda realizada com sucesso!");
        } else {
            System.out.println("Estoque insuficiente!");
        }
    }

    // Método para repor estoque
    void repor(int quantidade) {
        quantidadeEstoque += quantidade;
    }

    // Método para calcular valor total do estoque
    double calcularValorTotal() {
        return preco * quantidadeEstoque;
    }

    // Método para exibir informações
    void exibirInformacoes() {

        System.out.println(
            "Produto: " + nome +
            " | Preço: R$ " + preco +
            " | Estoque: " + quantidadeEstoque + " unidades"
        );

        System.out.println(
            "Valor total em estoque: R$ " + calcularValorTotal()
        );
    }

    // Método principal
    public static void main(String[] args) {

        Produto produto = new Produto();

        produto.nome = "Caneta Azul";
        produto.preco = 2.50;
        produto.quantidadeEstoque = 100;

        produto.vender(30);

        produto.exibirInformacoes();
    }
}
