# Circo

from statistics import mean

valor_ingresso = 20

idades = []

nomes = []

precos = []

idosos = []

valores_descontos = []

count_desc = 0

count_8 = 0

while True:

   nome = input('Informe o nome do cliente(-1 para parar):')

   if nome == "-1":

       break

   nomes.append(nome)

   idade= int(input('Informe a idade do cliente:'))

   idades.append(idade)

   if idade in range(0,5):

       precos.append(valor_ingresso*0.9)

       valores_descontos.append( valor_ingresso * 0.9 )

       count_desc += 1

       count_8 +=1

   elif idade in range(6,12):

       precos.append( valor_ingresso * 0.92)

       valores_descontos.append( valor_ingresso * 0.92)

       count_desc += 1

   elif idade in range(13,25):

       precos.append(valor_ingresso * 0.95)

       valores_descontos.append( valor_ingresso * 0.95)

       count_desc += 1

   elif idade > 60:

       precos.append(valor_ingresso*0.85)

       valores_descontos.append(valor_ingresso * 0.85)

       count_desc += 1

       idosos.append(nome)

   else:

       precos.append(valor_ingresso)

print(f"-"*50)

for x,y,z in zip(nomes,idades,precos):

   print(f'{x} tem  {y} anos e pagou R${z:.2f}')

print(f"-"*50)

print(f'{count_desc} Clientes com desconto.')

print(f"-"*50)

print(f'{round(count_8/(len(nomes)*100),2)} Clientes que tiveram 8% desconto.')

print(f"-"*50)

print(f'RELAÇÃO IDOSOS!')

for i in idosos:

   print(i)

print(f"-"*50)

print(f'A média de valor dos descontos aplicados foi de {round(mean(valores_descontos),2)}')
