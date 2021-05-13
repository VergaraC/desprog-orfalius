BUCKET SORT
======

Desafios de Programação                         
André Rocco, Arthur Carvalho, Victor Vergara

---------

Introdução
---------

1. Vetores

introdução sobre ordenação de vetores > exemplo com poucos dados, ordenar turma por idade

2. O que fazer?

porém na vida real você vai tratar com bases de dados com milhares de elementos.
Um dos jeitos é o algoritmo bucket sort.

??? Simulação

Simule o começo do algoritmo para o vetor abaixo, separando em 3 buckets:

Vetor = [1, 5, 7, 3, 2, 9, 4]

Primeiro bucket: 1-3

Segundo bucket:  4-6

Terceiro bucket: 7-9

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
::: Gabarito
 O pior caso acontece quando todos os elementos estão no mesmo bucket, nesse caso seria a mesma coisa que aplicar o *insertion sort* no vetor inteiro.

Nesse Caso a O(n) = n²

A explicação do cálculo está na [Aula 7](https://ensino.hashi.pro.br/desprog/aula7/index.html)
:::
Agora vamos calcular a complexidade do Caso Médio:


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