CÓDIGO 2:

•	Código para Análise estatística 
import json
import statistics

# Função para carregar dados de um arquivo JSON
def carregar_dados(arquivo):
    try:
        with open(arquivo, 'r') as f:
            return json.load(f)
    except FileNotFoundError:
        return []  # Retorna uma lista vazia se o arquivo não existir

# Função para salvar dados em um arquivo JSON
def salvar_dados(arquivo, dados):
    with open(arquivo, 'w') as f:
        json.dump(dados, f, indent=4)

# Função para adicionar um novo usuário
def adicionar_usuario(usuarios, nome, idade, curso):
    usuario = {
        'nome': nome,
        'idade': idade,
        'curso': curso
    }
    usuarios.append(usuario)

# Função para exibir todos os usuários
def exibir_usuarios(usuarios):
    for usuario in usuarios:
        print(f"Nome: {usuario['nome']}, Idade: {usuario['idade']}, Curso: {usuario['curso']}")

# Função para calcular a média de idades
def calcular_media_idade(usuarios):
    idades = [usuario['idade'] for usuario in usuarios]
    if idades:
        return statistics.mean(idades)
    return 0

# Função para calcular a mediana de idades
def calcular_mediana_idade(usuarios):
    idades = [usuario['idade'] for usuario in usuarios]
    if idades:
        return statistics.median(idades)
    return 0

# Função principal
def main():
    arquivo = 'usuarios.json'
    usuarios = carregar_dados(arquivo)

    while True:
        print("\n1. Adicionar Usuário")
        print("2. Exibir Usuários")
        print("3. Análise Estatística")
        print("4. Sair")
        opcao = input("Escolha uma opção: ")

        if opcao == '1':
            nome = input("Digite o nome do usuário: ")
            idade = int(input("Digite a idade do usuário: "))  # Convertendo para inteiro
            curso = input("Digite o curso do usuário: ")
            adicionar_usuario(usuarios, nome, idade, curso)
            salvar_dados(arquivo, usuarios)
            print("Usuário adicionado com sucesso!")

        elif opcao == '2':
            exibir_usuarios(usuarios)

        elif opcao == '3':
            media_idade = calcular_media_idade(usuarios)
            mediana_idade = calcular_mediana_idade(usuarios)
            print(f"Média de Idades: {media_idade}")
            print(f"Mediana de Idades: {mediana_idade}")

        elif opcao == '4':
            break

        else:
            print("Opção inválida. Tente novamente.")

if _name_ == "_main_":
    main()
