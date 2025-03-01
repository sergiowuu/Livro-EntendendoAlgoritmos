# Ordenação por Seleção

Este código implementa o algoritmo de **Ordenação por Seleção**, um método simples de ordenação de uma lista de elementos. O algoritmo funciona selecionando o menor elemento da lista em cada iteração e movendo-o para a posição correta até que toda a lista esteja ordenada.

## Descrição do Código

O código define duas funções:
1. **`buscaMenor(arr)`**: Encontra o menor elemento em uma lista `arr` e retorna o índice desse menor elemento.
2. **`ordenacaoPorSelecao(arr)`**: Ordena a lista `arr` utilizando o algoritmo de ordenação por seleção, que utiliza a função `buscaMenor` para encontrar o menor valor e movê-lo para o início da lista.

### Função `buscaMenor(arr)`:
- A função percorre todos os elementos da lista `arr`, com exceção do primeiro.
- Compara cada elemento com o valor mínimo encontrado até aquele ponto e, caso um valor menor seja encontrado, atualiza o índice do menor elemento.
- Retorna o índice do menor valor encontrado.

### Função `ordenacaoPorSelecao(arr)`:
- Inicializa uma lista `novoArr` que será a lista ordenada.
- Em seguida, utiliza a função `buscaMenor` para encontrar o menor valor da lista `arr` e move esse valor para a lista `novoArr`.
- A lista `arr` vai sendo modificada (o menor valor é removido a cada iteração) até que todos os valores sejam ordenados em `novoArr`.

### Exemplo:

- Para a lista `[5, 3, 6, 2, 10]`, a função `ordenacaoPorSelecao` irá ordenar os valores e retornar a lista `[2, 3, 5, 6, 10]`.

## Código:

```python
def buscaMenor(arr):
    menor = arr[0]
    menor_indice = 0
    for i in range(1, len(arr)):
        if arr[i] < menor:
            menor_indice = i
            menor = arr[i]      
    return menor_indice

def ordenacaoPorSelecao(arr):
    novoArr = []
    for i in range(len(arr)):
        menor = buscaMenor(arr)
        novoArr.append(arr.pop(menor))
    return novoArr

print(ordenacaoPorSelecao([5, 3, 6, 2, 10]))  # Saída: [2, 3, 5, 6, 10]
```

### Explicação do fluxo:
1. A função `buscaMenor` encontra o menor valor da lista `arr` e retorna seu índice.
2. A função `ordenacaoPorSelecao` usa `buscaMenor` repetidamente para extrair o menor elemento de `arr` e adicioná-lo à nova lista `novoArr`.
3. O processo é repetido até que todos os elementos de `arr` sejam retirados e colocados ordenadamente em `novoArr`.

### Complexidade:
- **Complexidade de tempo**: A complexidade do algoritmo de ordenação por seleção é **O(n²)**, onde `n` é o número de elementos na lista. Isso ocorre porque o algoritmo precisa percorrer a lista várias vezes, comparando elementos entre si.
- **Complexidade de espaço**: A complexidade de espaço é **O(n)**, pois o algoritmo cria uma nova lista para armazenar os valores ordenados.