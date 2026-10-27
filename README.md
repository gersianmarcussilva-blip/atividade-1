Compras = []

while True:
    Valor = float(input("Digite o valor da compra (0 para sair):"))
    
    if Valor == 0:
        break

    if Valor < 0:
         print("Valor invalido!!!")
         continue
    
    Idade = int(input("Digite a idade do cliente: "))

    if Idade < 0:
         print("Idade invalido!!!")
         continue

    Final = Valor

    if Idade >= 65:
         Final = Final - (Final * 20 / 100)
   
    if Final > 100:
        Final = Final - (Final * 10 / 100)

    Desconto = Valor - Final

    Compras.append([Valor, Desconto, Final])

    print(f"Valor final: R$ {Final:.2f}")

Total = 0
Descontos = 0
Final_dia = 0

for Compra in Compras:
    Total = Total + Compra[0]
    Descontos = Descontos + Compra[1]
    Final_dia = Final_dia + Compra[2]

print("\nResumo do dia")
print("Quantidade de compras:", len(Compras))
print(f"Total bruto: R$ {Total:.2f}")
print(f"Total de descontos: R$ {Descontos:.2f}")
print(f"Total final: R$ {Final_dia:.2f}")
