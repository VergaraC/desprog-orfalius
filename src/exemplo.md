BUCKET SORT
======

Desafios de Programação                         
André Rocco, Arthur Carvalho, Victor Vergara

---------

Introdução
---------

1. Vetores

Imagine que você recebeu uma lista de alunos de um colégio e é necessário ordenar essa lista por ordem de idade. Você, como um bom aluno de engenharia da computação, pensa direto nas aulas que teve com o ilustre Marcelo Hashimoto e decide usar um dos algoritmos passados por ele. Isso é válido, visto que foram dadas múltiplas maneiras de enfrentar múltiplos problemas, porém, na vida real, você pode tratar com bases de dados com centenas milhares de elementos em databases enormes, e nesses casos seria bom conhecer uma alternativa especializada para estes casos.

2. O que fazer?

Um dos jeitos de lidar com esses casos é o algoritmo {red}(Bucket Sort). Este algoritmo tem o papel de ordenar um vetor em **3 etapas** básicas: 

A **primeira etapa** consiste em separar esse vetor em vários "baldes", cada um deles comportando elementos em uma faixa de valores, por exemplo o intervalo de 1 a 20.

![](etapa1.png)

^^^^ imagem merda ^^^^

Após separados em baldes, na **segunda etapa** é usado um **algoritmo secundário** para ordenar os valores dentro de cada balde individualmente.

Na **terceira etapa**, após ordenados os elementos dentros dos baldes, pode-se apenas concatená-los para gerar o vetor ordenado.

??? Simulação

Simule o começo do algoritmo para o vetor abaixo, separando o vetor dado em 3 buckets:

Vetor = **[1, 5, 7, 3, 2, 9, 4]**

intervalo do primeiro bucket: **1-3**

intervalo do segundo bucket:  **4-6**

intervalo do terceiro bucket: **7-9**

Em particular, escreva como serão distribuidos os elementos em cada bucket:

::: Gabarito

```
Bucket 1: 1, 3, 2

Bucket 2: 5, 4

Bucket 3: 7, 9 
```

:::

???

Note que os valores estão separados nos buckets apropriados, porém não estão ordenados internamente.

3. Algoritimo secundário

Após isso, será necessário rodar outro algoritmo de ordenação, dessa vez dentro de cada "balde". 

O algoritmo a ser implementado para essa função é o **insertion sort**. Ele é um ótimo algoritimo para este caso pois se sobressai quando o número de elementos é {red}(pequeno) e o vetor não tem {red}(ordem aparente).

``` c
pseudocódigo de como é implementado o insertion sort
```

Após isso, cada bucket ficará ordenado, ou seja, com essa aparência:

```
Bucket 1: 1 2 3

Bucket 2: 4 5

Bucket 3: 7 9
```




----------------------------
Complexidade
---------

Agora vamos Calcular a Complexidade do *Bucket Sort*.
Caso esteja em dúvida de como calcular volte para a [Aula 6](https://ensino.hashi.pro.br/desprog/aula6/index.html)

Vamos começar com o cálculo do Pior Caso:
Em qual situação ocorre o pior caso do *bucket sort*? Qual a Complexidade?

??? Exercício

Agora vamos calcular a complexidade do Caso Médio:

::: Gabarito
 O pior caso acontece quando todos os elementos estão no mesmo bucket, nesse caso seria a mesma coisa que aplicar o *insertion sort* no vetor inteiro.

Nesse Caso a O(n) = n²

A explicação do cálculo está na [Aula 7](https://ensino.hashi.pro.br/desprog/aula7/index.html)
:::

???


-------------------------------
Para criar um parágrafo, basta escrever um texto contínuo, sem pular linhas.

Você também pode criar

1. listas;

2. ordenadas,

assim como

* listas;

* não-ordenadas

e imagens. Lembre que todas as imagens devem estar em uma subpasta *img*.

![](logo.png)

Para tabelas, usa-se a [notação do
MultiMarkdown](https://fletcher.github.io/MultiMarkdown-6/syntax/tables.html),
que é muito flexível. Vale a pena abrir esse link para saber todas as
possibilidades.

| coluna a | coluna b |
|----------|----------|
| 1        | 2        |

Ao longo de um texto, você pode usar *itálico*, **negrito**, {red}(vermelho) e
[[tecla]]. Também pode usar uma equação LaTeX: $f(n) \leq g(n)$. Se for muito
grande, você pode isolá-la em um parágrafo.

$$\lim_{n \rightarrow \infty} \frac{f(n)}{g(n)} \leq 1$$

Para inserir uma animação, use `md ;` seguido do nome de uma pasta onde as
imagens estão. Essa pasta também deve estar em *img*.

;bubble

Você também pode inserir código, inclusive especificando a linguagem.

``` py
def f():
    print('hello world')
```

``` c
void f() {
    printf("hello world\n");
}
```

Se não especificar nenhuma, o código fica com colorização de terminal.

```
hello world
```


!!! Aviso
Este é um exemplo de aviso, entre `md !!!`.
!!!


??? Exercício

Este é um exemplo de exercício, entre `md ???`.

::: Gabarito
Este é um exemplo de gabarito, entre `md :::`.
:::

???