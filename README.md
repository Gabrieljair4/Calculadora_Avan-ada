# Calculadora_Avan-ada
Calculadora avançada em Python que executa desde operações básicas até funções trigonométricas, logaritmos e potências. Conta com tratamento de exceções (erros) para evitar quebras e roda direto no terminal. Ideal para estudos de lógica de programação! 🚀🐍
import math

def mostrar_menu():
    print("\n--- Calculadora Avançada ---")
    print("1. Soma (+)")
    print("2. Subtração (-)")
    print("3. Multiplicação (*)")
    print("4. Divisão (/)")
    print("5. Potência (^)")
    print("6. Raiz Quadrada (√)")
    print("7. Logaritmo (log)")
    print("8. Seno (sin)")
    print("9. Cosseno (cos)")
    print("10. Tangente (tan)")
    print("0. Sair")

def calculadora():
    while True:
        mostrar_menu()
        opcao = input("\nEscolha uma operação: ")

        if opcao == '0':
            print("Encerrando a calculadora. Até logo!")
            break

        try:
            if opcao in ['1', '2', '3', '4', '5']:
                num1 = float(input("Digite o primeiro número: "))
                num2 = float(input("Digite o segundo número: "))

                if opcao == '1':
                    print(f"Resultado: {num1 + num2}")
                elif opcao == '2':
                    print(f"Resultado: {num1 - num2}")
                elif opcao == '3':
                    print(f"Resultado: {num1 * num2}")
                elif opcao == '4':
                    if num2 == 0:
                        print("Erro: Divisão por zero não permitida.")
                    else:
                        print(f"Resultado: {num1 / num2}")
                elif opcao == '5':
                    print(f"Resultado: {math.pow(num1, num2)}")

            elif opcao in ['6', '7', '8', '9', '10']:
                num = float(input("Digite o número: "))

                if opcao == '6':
                    if num < 0:
                        print("Erro: Não existe raiz quadrada de número negativo nos reais.")
                    else:
                        print(f"Resultado: {math.sqrt(num)}")
                elif opcao == '7':
                    base = input("Digite a base (ou pressione Enter para base decimal): ")
                    if base == "":
                        print(f"Resultado: {math.log10(num)}")
                    else:
                        print(f"Resultado: {math.log(num, float(base))}")
                elif opcao == '8':
                    # Converte para radianos pois o math.sin espera radianos
                    print(f"Resultado: {math.sin(math.radians(num))}")
                elif opcao == '9':
                    print(f"Resultado: {math.cos(math.radians(num))}")
                elif opcao == '10':
                    print(f"Resultado: {math.tan(math.radians(num))}")

            else:
                print("Opção inválida! Tente novamente.")

        except ValueError:
            print("Erro: Por favor, insira apenas números válidos.")

if __name__ == "__main__":
    calculadora()
