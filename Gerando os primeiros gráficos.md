## Gerando os primeiros gráficos

Código para importar a biblioteca *Matplotlib* ao programa e definir algumas características iniciais de estilo

##### Importando Bibliotecas

```python
from matplotlib import pyplot as plt
plt.style.use('seaborn-whitegrid')
```

Importando a biblioteca para *numpy*, esta traz a possibilidade de trabalhar com algebra linear, transformada de Fourier e Matrizes

```python
import numpy as np
```

##### Criando os primeiros gráficos

Criando o primeiro gráfico com uma grade retangular e seus eixos:

```python
fig = plt.figure()
ax = plt.axes()
#Para que se possa visualizar
plt.show()
```

Plotando algo no gráfico criado 

```python
x = np.linspace(0, 10, 1000)
ax.plot(x, np.sin(x));
#Para que se possa visualizar
plt.show()
#Pode se usar também o seguinte comando para plotar o mesmo gráfico:
plt.plot(x, np.sin(x));
plt.show #Para visualizar
```

Para criar dois gráficos na mesma figura:

```python
plt.plot(x, np.sin(x))
plt.plot(x, np.cos(x));
```

##### Ajustando os gráficos quanto suas cores e estilos de linha

Pode-se mudar as cores das curvas da seguinte maneira:

```python
plt.plot(x, np.sin(x-0), color='blue')			#Especificando a cor pelo nome
plt.plot(x, np.sin(x-1), color='g')				#Especificando o codigo da cor (rgbcmyk)
plt.plot(x, np.sin(x-2), color='0.75')			#Especificando a escala de cinza (0 a 1)
plt.plot(x, np.sin(x-3), color='#FFDD44')		#Especificando o código hexadecimal
plt.plot(x, np.sin(x), color=(1.0,0.2,0.3))		#Especificando RGB tuple
plt.plot(x, np.sin(x), color='chartreuse')		#Especificando o nome da cor em HTML
```

O estilo da linha pode ser mudado da seguinte maneira:

```python
plt.plot(x, x + 0, linestyle='solid')		#Linha sólida
plt.plot(x, x + 1, linestyle='dashed')		#Linha em traços
plt.plot(x, x + 2, linestyle='dashdot')		#Linha traço ponto
plt.plot(x, x + 3, linestyle='dotted');		#Linha Pontilhada

plt.plot(x, x + 4, linestyle='-')  # solid		#Linha sólida
plt.plot(x, x + 5, linestyle='--') # dashed		#Linha em traços
plt.plot(x, x + 6, linestyle='-.') # dashdot	#Linha traço ponto
plt.plot(x, x + 7, linestyle=':');  # dotted	#Linha Pontilhada
```

Mudando estilo de linha e cor ao mesmo tempo:

```python
plt.plot(x, x + 0, '-g')	#Linha sólida e verde
plt.plot(x, x + 1, '--c')	#Linha tracejada e ciano
plt.plot(x, x + 2, '-.k')	#Linha traço ponto e preta
plt.plot(x, x + 3, ':r');	#Linha Pontilhada e vermelha
```

##### Ajustando os limites dos eixos do gráfico

Primeira maneira:

```
plt.plot(x, np.sin(x))

plt.xlim(-1, 11)
plt.ylim(-1.5, 1.5);
```

Vale lembrar que se ingressados os valores acima ao contrário, o gráfico também sairá ao contrário

Segunda maneira:

```python
plt.axis([-1, 11, -1.5, 1.5]);
```

Desta maneira pode-se ajustar o eixo x e depois o y na mesma linha de comando 

Terceira maneira:

```python
plt.plot(x, np.sin(x))
plt.axis('tight');
```

Ajusta a plotagem ao tamanho da tela

Quarta maneira:

```
plt.plot(x, np.sin(x))
plt.axis('equal');
```

Abre mais a imagem (aumenta o eixo y)

##### Incluindo Labels aos gráficos

```python
plt.plot(x, np.sin(x))			#Função plotada
plt.title("Curva Senoidal")		#Título do gráfico
plt.xlabel("x")					#Eixo x
plt.ylabel("sin(x)");			#Eixo y
```

O código acima tem a capacidade de colocar um título na figura e definir nomes para os eixos x e y

##### Plotando duas curvas em um mesmo gráfico ajustando linhas e incorporando legenda:

```python
plt.plot(x, np.sin(x), '-g', label='sin(x)')
plt.plot(x, np.cos(x), ':b', label='cos(x)')
plt.axis('equal')

plt.legend();
```

