import math

def calculadora():
    print("=" * 40)
    print("        CALCULADORA EM PYTHON")
    print("=" * 40)
    
    while True:
        print("\nOperações disponíveis:")
        print("  +  Adição")
        print("  -  Subtração")
        print("  *  Multiplicação")
        print("  /  Divisão")
        print("  ** Potência")
        print("  %  Módulo (resto)")
        print("  r  Raiz quadrada")
        print("  s  Seno (em graus)")
        print("  c  Cosseno (em graus)")
        print("  t  Tangente (em graus)")
        print("  l  Logaritmo (base 10)")
        print("  n  Logaritmo natural")
        print("  0  Sair")
        print("-" * 40)
        
        opcao = input("Escolha uma operação: ").strip().lower()
        
        if opcao == '0':
            print("\nObrigado por usar a calculadora!")
            break
        
        # Operações que precisam de 1 número
        if opcao in ['r', 's', 'c', 't', 'l', 'n']:
            try:
                num = float(input("Digite o número: "))
                
                if opcao == 'r':
                    if num < 0:
                        print("Erro: Não existe raiz quadrada de número negativo!")
                    else:
                        print(f"Raiz quadrada de {num} = {math.sqrt(num):.4f}")
                
                elif opcao == 's':
                    print(f"Seno de {num}° = {math.sin(math.radians(num)):.4f}")
                
                elif opcao == 'c':
                    print(f"Cosseno de {num}° = {math.cos(math.radians(num)):.4f}")
                
                elif opcao == 't':
                    if num % 180 == 90:
                        print("Erro: Tangente não definida para este ângulo!")
                    else:
                        print(f"Tangente de {num}° = {math.tan(math.radians(num)):.4f}")
                
                elif opcao == 'l':
                    if num <= 0:
                        print("Erro: Logaritmo só é definido para números positivos!")
                    else:
                        print(f"Log10({num}) = {math.log10(num):.4f}")
                
                elif opcao == 'n':
                    if num <= 0:
                        print("Erro: Logaritmo natural só é definido para números positivos!")
                    else:
                        print(f"ln({num}) = {math.log(num):.4f}")
            
            except ValueError:
                print("Erro: Digite um número válido!")
        
        # Operações que precisam de 2 números
        elif opcao in ['+', '-', '*', '/', '**', '%']:
            try:
                num1 = float(input("Digite o primeiro número: "))
                num2 = float(input("Digite o segundo número: "))
                
                if opcao == '+':
                    print(f"{num1} + {num2} = {num1 + num2}")
                
                elif opcao == '-':
                    print(f"{num1} - {num2} = {num1 - num2}")
                
                elif opcao == '*':
                    print(f"{num1} × {num2} = {num1 * num2}")
                
                elif opcao == '/':
                    if num2 == 0:
                        print("Erro: Divisão por zero não permitida!")
                    else:
                        print(f"{num1} ÷ {num2} = {num1 / num2}")
                
                elif opcao == '**':
                    print(f"{num1} ^ {num2} = {num1 ** num2}")
                
                elif opcao == '%':
                    if num2 == 0:
                        print("Erro: Módulo por zero não permitido!")
                    else:
                        print(f"{num1} % {num2} = {num1 % num2}")
            
            except ValueError:
                print("Erro: Digite números válidos!")
        
        else:
            print("Erro: Operação inválida! Tente novamente.")
        
        input("\nPressione Enter para continuar...")

# Executar a calculadora
if __name__ == "__main__":
    calculadora()
