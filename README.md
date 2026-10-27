Compras = []    (primeiro eu criei uma lista vazia pra armazenar as informaçoes de cada compra)

while True: (aqui eu comecei a usar o loop fazer o programa repetir as compras em loop ate receber o comando para parar)
    Valor = float(input("Digite o valor da compra (0 para sair):"))
    
    if Valor == 0:   (aqui eu dei a condiçao para fazer o loop parar)
        break

    if Valor < 0:      (depois coloquei uma condiçao para que as compras nao apresentem valores negativos)
         print("Valor invalido!!!")
         continue
    
    Idade = int(input("Digite a idade do cliente: "))  (em seguida adicionei a idade do cliente, usei int porque a idade e um valor inteiro nao existe 12,4 anos, apenas 12 ou 13)

    if Idade < 0:     (tambem adicionei uma condiçao para que nao se apresentem idades negativas)
         print("Idade invalido!!!")
         continue

    Final = Valor     (aqui eu criei uma variavel e coloquei nela o valor original da compra)

    if Idade >= 65:  (depois adicionei a condiçao para poder calcular os descontos de 20%)
         Final = Final - (Final * 20 / 100)
   
    if Final > 100:
        Final = Final - (Final * 10 / 100)  (em seguida adicionei o segundo desconto aplicando-o sobre o valor que ja recebeu o desconto por idade)

    Desconto = Valor - Final (depois subtrai o valor final do valor original para descobrir quanto foi descontado no total)

    Compras.append([Valor, Desconto, Final])  (depois guardei os dados da compra, usei .append pra colocar um novo item no fim da lista porque precisamos guardar todas as compras pra soma-las depois )

    print(f"Valor final: R$ {Final:.2f}") (depois eu usei esse comando para informar o preço final de cada compra, e o comando 2f foi mostrar o numero com duas casas decimais)

Total = 0 (eu criei 3 variaveis e comecei todas com 0 porque ainda nao somei nenhuma compra ainda, cada uma vai guardar um total diferente durante o calculo do resumo)
Descontos = 0
Final_dia = 0

for Compra in Compras:      ( usei o for para passar por cada compra que ficou guardada na lista. como cada compra tem 3 informaçoes, usei os numeros entre colchetes para acessar cada uma delas e somar ao total)
    Total = Total + Compra[0]
    Descontos = Descontos + Compra[1]
    Final_dia = Final_dia + Compra[2]

print("\nResumo do dia")  (mostra o titulo do resumo)
print("Quantidade de compras:", len(Compras)) ( conta quantas compras estao registradas na lista)
print(f"Total bruto: R$ {Total:.2f}") (mostra a soma de todos os valores originais) 
print(f"Total de descontos: R$ {Descontos:.2f}")
print(f"Total final: R$ {Final_dia:.2f}")
