# Busca Binária

Este é um código simples implementando o algoritmo de **Busca Binária**, que permite buscar um **item** dentro de uma **lista ordenada**. O algoritmo funciona dividindo repetidamente a lista ao meio até que o item seja encontrado ou se conclua que o item não existe na lista.

## Descrição do código

O código define uma função chamada `busca_binaria` que recebe dois parâmetros:
- `lista`: uma lista ordenada de elementos.
- `item`: o valor que você deseja procurar na lista.

A função retorna o **índice** do item, caso ele seja encontrado na lista, ou **None** se o item não for encontrado.

### Fluxo do algoritmo:
1. Define-se a variável `baixo`, que inicia no índice 0, e a variável `alto`, que inicia no índice do último elemento da lista.
2. Em seguida, o algoritmo entra em um laço `while` que continua enquanto `baixo` for menor ou igual a `alto`. Esse laço divide a lista ao meio, procurando o item.
3. Dentro do laço:
    - O valor do índice médio da lista é calculado pela fórmula `(baixo + alto) // 2`.
    - O valor da lista nesse índice é comparado com o item procurado.
    - Se o valor for igual ao item, o índice médio é retornado, indicando que o item foi encontrado.
    - Se o valor for maior que o item, o valor de `alto` é ajustado para procurar na metade inferior da lista.
    - Se o valor for menor que o item, o valor de `baixo` é ajustado para procurar na metade superior da lista.
4. Se o item não for encontrado após a divisão de toda a lista, a função retorna `None`.

### Exemplos

1. Para a lista `[1, 3, 5, 7, 9]` e o item `3`, a função retorna o índice `1`, pois o item 3 está no índice 1.
2. Para a lista `[1, 3, 5, 7, 9]` e o item `-1`, a função retorna `None`, pois o item não está na lista.

## Código:

```python
def busca_binaria(lista, item):
    baixo = 0
    alto = len(lista) - 1
    
    while baixo <= alto:
        meio = (baixo + alto) // 2
        chute = lista[meio]

        if chute == item:
            return meio
        if chute > item:
            alto = meio - 1
        else:
            baixo = meio + 1
    return None

minha_lista = [1, 3, 5, 7, 9]

# Testes
print(busca_binaria(minha_lista, 3))  # Saída: 1
print(busca_binaria(minha_lista, -1))  # Saída: None
```

### Observações:
- **Complexidade de tempo**: O algoritmo de pesquisa binária possui complexidade **O(log n)**, onde n é o número de elementos da lista, o que o torna muito eficiente para listas grandes.
- **Pré-requisito**: A lista precisa estar ordenada para que a busca binária funcione corretamente.
