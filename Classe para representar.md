# Classe para representar uma peça de bijutaria
class Bijutaria:
    def __init__(self, nome, material, preço):
        self.nome = nome
        self.material = material
        self.preço = preço

# Função para exibir o menu da loja
def exibir_menu():
    print("Bem-vindo à Loja de Bijutarias!")
    print("1. Ver bijutarias disponíveis")
    print("2. Adicionar bijutaria ao carrinho")
    print("3. Ver carrinho")
    print("4. Finalizar compra")
    print("5. Sair")

# Função para exibir as bijutarias disponíveis
def exibir_bijutarias(bijutarias):
    print("Bijutarias disponíveis:")
    for bijutaria in bijutarias:
        print(f"{bijutaria.nome} - Material: {bijutaria.material} - Preço: {bijutaria.preço}")

# Função para adicionar uma bijutaria ao carrinho
def adicionar_ao_carrinho(bijutaria, carrinho):
    carrinho.append(bijutaria)
    print(f"{bijutaria.nome} adicionada ao carrinho!")

# Função para exibir o carrinho
def exibir_carrinho(carrinho):
    if len(carrinho) == 0:
        print("Carrinho vazio")
    else:
        print("Itens no carrinho:")
        for bijutaria in carrinho:
            print(f"{bijutaria.nome} - Material: {bijutaria.material} - Preço: {bijutaria.preço}")

# Função para finalizar a compra e calcular o total
def finalizar_compra(carrinho):
    total = 0
    print("Itens comprados:")
    for bijutaria in carrinho:
        print(f"{bijutaria.nome} - Material: {bijutaria.material} - Preço: {bijutaria.preço}")
        total += bijutaria.preço
    print(f"Total: {total}€")
    carrinho.clear()
    print("Compra finalizada!")

# Função principal do programa
def main():
    bijutarias_disponiveis = [
        Bijutaria("Colar", "Prata", 15),
        Bijutaria("Brincos", "Ouro", 20),
        Bijutaria("Pulseira", "Aço Inoxidável", 12)
    ]
    carrinho = []

    while True:
        exibir_menu()
        escolha = input("Escolha uma opção: ")

        if escolha == "1":
            exibir_bijutarias(bijutarias_disponiveis)
        elif escolha == "2":
            exibir_bijutarias(bijutarias_disponiveis)
            bijutaria_escolhida = input("Digite o nome da bijutaria que deseja adicionar ao carrinho: ")
            for bijutaria in bijutarias_disponiveis:
                if bijutaria.nome.lower() == bijutaria_escolhida.lower():
                    adicionar_ao_carrinho(bijutaria, carrinho)
                    break
            else:
                print("Bijutaria não encontrada!")
        elif escolha == "3":
            exibir_carrinho(carrinho)
        elif escolha == "4":
            finalizar_compra(carrinho)
        elif escolha == "5":
            print("Obrigado por visitar a Loja de Bijutarias!")
            break
        else:
            print("Opção inválida. Por favor, escolha novamente.")

# Executar o programa
main()
