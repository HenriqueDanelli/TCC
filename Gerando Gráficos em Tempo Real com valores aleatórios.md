## Gerando Gráficos em Tempo Real com valores aleatórios

##### Programa 

```python
import random 
from itertools import count 
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation

plt.style.use('fivethirtyeight')

x_vals = []
y_vals = []

index = count()

def animate(i):
    x_vals.append(next(index))
    y_vals.append(random.randint(0, 5))
    
    plt.cla()
    plt.plot(x_vals, y_vals)
    
ani = FuncAnimation(plt.gcf(), animate, interval=1000)

plt.tight_layout
plt.show() 
```

##### Bibliotecas utilizadas

`import random` : Esta biblioteca tem por função implementar números aleatórios para varias distribuições

`from itertools import count` : Esta traz por meio da função `count()` uma contagem sequencial.

`import matplotlib.pyplot as plt` : Biblioteca de plotagem de gráficos

`from matplotlib.animation import FuncAnimation` : Função para animação dos gráficos (tempo real)



##### Estilo do Gráfico

`plt.style.use('fivethirtyeight')`: Definindo o estilo do gráfico a ser gerado

##### Inicio do programa

```python
x_vals = []
y_vals = []
```

Como não se quer utilizar valores fixos e pré definidos para os gráficos, define-se estas duas variáveis como conjuntos vazios.

```python
index = count()
```

Inicializando a função count() em uma variável

###### Função

```
def animate(i):
    x_vals.append(next(index))
    y_vals.append(random.randint(0, 5))
    
    plt.cla()
    plt.plot(x_vals, y_vals)
```

`x_vals` está levando como parâmetro a variável index, ou seja, está assumindo um caráter sequencial de contagem enquanto `y_vals` assume um caráter aleatório de valores inteiros entre 0 e 5.

`plt.cla()` garante a permanência da mesma cor do gráfico conforme os valores vão se alterando 

` plt.plot(x_vals, y_vals)` Plota o grafico de x_vals em relação a y_vals



##### Função de animação

`ani = FuncAnimation(plt.gcf(), animate, interval=1000)` está função é inicializada na variável ani e e leva como argumento a `plt.gcf` que quer dizer para que a mesma anime o gráfico que está sendo executado no momento e exprime um intervalo de 1000, que quer dizer uma atualização por segundo.

##### Funções de plotagem 

```python
plt.tight_layout
plt.show() 
```

A primeira função diz respeito ao estilo do gráfico, neste caso estilo tight 

E a segunda função imprime o gráfico plotado na tela.



