BUCKET SORT
======

Desafios de Programação                         
André Rocco, Arthur Carvalho, Victor Vergara

---------

Introdução
---------

* Vetores

Imagine que você recebeu uma lista de alunos de um colégio e é necessário ordenar essa lista por ordem de idade. Você, como um bom aluno de engenharia da computação, pensa direto nas aulas que teve com o ilustre **{green}(Marcelo Hashimoto)** e decide usar um dos algoritmos passados por ele. Isso é válido, visto que foram dadas múltiplas maneiras de enfrentar múltiplos problemas, porém, na vida real, você pode tratar com bases de dados com centenas de milhares de elementos em databases enormes, em quais realizar operações no disco é demorado, e nesses casos seria bom conhecer uma alternativa especializada para estes casos.

* O que fazer?

Um dos jeitos de lidar com esses casos é o algoritmo {red}(Bucket Sort). Este algoritmo pretende ordenar vetores quebrando-os em vetores menores e ordenando cada vetor menor individualmente, similar ao **quick sort**, só que, ao invés de quebrar o vetor em "valores menores" e "valores maiores", o **Bucket sort** almeija separá-lo em vários pedacinhos, como "valores menores", "valores pequenos-médios", "valores médios", e assim em diante. Para isso ser feito, é preciso percorrer **3 etapas** básicas de implementação: 

A *primeira etapa* consiste em separar esse vetor em vários "baldes", cada um deles comportando elementos em uma faixa de valores, por exemplo o intervalo de 1 a 20.

![](imagemexemplo.png)


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

Note que os valores estão separados nos buckets apropriados, porém não estão ordenados internamente. Então, entrando na *segunda etapa* de implementação, resta a pergunta: **Como ordenar os valores internamente?**

* Algoritmo secundário

Como você deve ter imaginado, será necessário rodar outro algoritmo de ordenação, dessa vez dentro de cada "balde". Os algoritmos geralmente utilizados para fazer essa função são os que vocês estudaram na [Aula 7](https://ensino.hashi.pro.br/desprog/aula7/index.html).

??? Pergunta

Entre os algoritmos disponibilizados existe um que se sobressai para essa tarefa. Você consegue identificar qual é esse algoritmo?

::: Gabarito

O algoritmo a ser implementado para essa função é o *insertion sort*. Ele é um ótimo algoritimo para este caso pois se sobressai quando o número de elementos é {red}(pequeno) e o vetor não tem {red}(ordem aparente).

:::

???



Após isso, cada bucket ficará ordenado, ou seja, com essa aparência:

```
Bucket 1: 1 2 3

Bucket 2: 4 5

Bucket 3: 7 9
```

* Concatenação

Por fim, na *terceira etapa* da implementação, resta concatenar os baldes com os valores ordenados entre si, dessa vez em um novo vetor, deixando o caráter desse algoritmo como **estável**.

Veja a animação abaixo ilustrando o passo a passo do bucket sort:

;Exemplo

Visto isso, o pseudocódigo abaixo ilustra a implementação do bucket sort. Veja se você entendeu:

``` c
function bucketSort(array, k){
    buckets ← new array of k empty lists
    M ← the maximum key value in the array
    for i = 1 to length(array) do
        insert array[i] into buckets[floor(k × array[i] / M)]
    for i = 1 to k do
        insertionSort(buckets[i])
    return the concatenation of buckets[1], ...., buckets[k]
}
```

----------------------------
Complexidade
---------

Agora vamos Calcular a Complexidade do Bucket Sort.
Caso esteja em dúvida de como calcular volte para a [Aula 6](https://ensino.hashi.pro.br/desprog/aula6/index.html)


??? Pior Caso

Vamos começar com o cálculo do Pior Caso:
Em qual situação ocorre o pior caso do bucket sort? Qual a Complexidade?

::: Gabarito
 O pior caso acontece quando todos os elementos estão no mesmo bucket, nesse caso seria a mesma coisa que aplicar o insertion sort no vetor inteiro.

Nesse caso a complexidade é O(n²)

A explicação do cálculo está na [Aula 7](https://ensino.hashi.pro.br/desprog/aula7/index.html)
:::

???
???Caso Médio
Agora vamos calcular a complexidade do Caso Médio:

1. Primeiro vamos calcular a complecidade da criação dos buckets e achar o valor máximo dos buckets:  
::: Gabarito
 Isso tem uma complexidade O(n), visto que é necessário percorrer cada item do elemento
:::
2. Depois vamos calcular a complexidade de separar os elementos nos buckets criados:

::: Gabarito
 Isso tem uma complexidade O(n), visto que é necessário percorrer cada item do elemento
:::
3. Agora vamos calcular a complexidade da aplicação do Insertion Sort em cada bucket:
::: Gabarito
Por buckets se tratarem de vetores pequenos é posssível afirmar que os elementos em cada bucket seguem uma distribuição binomial e sendo ni = número de itens em cada bucket, é possível afirmar que a complexidade é:



![](SomaExpectation.png)


E[ni]= n (1/n) = 1 


Var[ni] = E[ni] q = 1 - (1/n)

E[ni²] = Var[ni] + E²[ni] = 2 - (1/n)


Assim a complexidade seria O(n)
:::
4. Por fim, vamos calcular a complexidade da concatenação dos buckets no vetor final:
::: Gabarito
Sendo k = número de buckets

A complexidade da etapa é O(k)
:::
5. Assim a complexidade final do algoritimo no caso médio é: 
::: Gabarito
O(n)
:::
???
??? Melhorar Caso 

Qual a melhor complexidade possível no *Bucket Sort*?
???
-------------------------------

