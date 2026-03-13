**Guia Prático de Sorting – Ciência da Computação**

---

# 1️⃣ Conceito Geral

**Sorting (Ordenação)** é o processo de organizar elementos de uma lista em uma ordem específica, geralmente **crescente ou decrescente**. Ordenar é essencial para facilitar buscas, análises e visualizações de dados.

Pense em sorting como organizar fitas VHS em ordem alfabética ou jogos em ordem de lançamento na prateleira do seu quarto nos anos 90.

---

# 2️⃣ Tipos de Algoritmos de Ordenação

| Algoritmo      | Complexidade | Característica                                         | Analogia anos 90                                            |
| -------------- | ------------ | ------------------------------------------------------ | ----------------------------------------------------------- |
| Bubble Sort    | O(n²)        | Compara e troca elementos vizinhos repetidamente       | Agitar fitas VHS até que todas fiquem na ordem certa        |
| Insertion Sort | O(n²)        | Insere cada elemento na posição correta                | Inserir cada cartucho na prateleira na posição certa        |
| Selection Sort | O(n²)        | Seleciona o menor elemento e coloca na posição correta | Escolher a menor fita e colocar no início da fila           |
| Merge Sort     | O(n log n)   | Divide e conquista, junta listas ordenadas             | Dividir prateleiras, organizar e juntar as seções ordenadas |
| Quick Sort     | O(n log n)   | Escolhe um pivô e separa menores e maiores             | Escolher fita pivô e organizar lado esquerdo/direito        |

---

# 3️⃣ Exemplos em Python

## a) Bubble Sort

```python
def bubble_sort(lista):
    n = len(lista)
    for i in range(n):
        for j in range(0, n-i-1):
            if lista[j] > lista[j+1]:
                lista[j], lista[j+1] = lista[j+1], lista[j]
    return lista

numeros = [5, 1, 4, 2, 8]
print(bubble_sort(numeros))  # [1, 2, 4, 5, 8]
```

## b) Insertion Sort

```python
def insertion_sort(lista):
    for i in range(1, len(lista)):
        chave = lista[i]
        j = i-1
        while j >=0 and chave < lista[j]:
            lista[j+1] = lista[j]
            j -= 1
        lista[j+1] = chave
    return lista

numeros = [12, 11, 13, 5, 6]
print(insertion_sort(numeros))  # [5, 6, 11, 12, 13]
```

## c) Selection Sort

```python
def selection_sort(lista):
    for i in range(len(lista)):
        min_idx = i
        for j in range(i+1, len(lista)):
            if lista[j] < lista[min_idx]:
                min_idx = j
        lista[i], lista[min_idx] = lista[min_idx], lista[i]
    return lista

numeros = [64, 25, 12, 22, 11]
print(selection_sort(numeros))  # [11, 12, 22, 25, 64]
```

## d) Merge Sort

```python
def merge_sort(lista):
    if len(lista) <= 1:
        return lista
    meio = len(lista)//2
    esquerda = merge_sort(lista[:meio])
    direita = merge_sort(lista[meio:])
    return merge(esquerda, direita)

def merge(esq, dir):
    resultado = []
    while esq and dir:
        if esq[0] <= dir[0]:
            resultado.append(esq.pop(0))
        else:
            resultado.append(dir.pop(0))
    resultado += esq + dir
    return resultado

numeros = [38, 27, 43, 3, 9, 82, 10]
print(merge_sort(numeros))  # [3, 9, 10, 27, 38, 43, 82]
```

## e) Quick Sort

```python
def quick_sort(lista):
    if len(lista) <= 1:
        return lista
    pivot = lista[0]
    menores = [x for x in lista[1:] if x <= pivot]
    maiores = [x for x in lista[1:] if x > pivot]
    return quick_sort(menores) + [pivot] + quick_sort(maiores)

numeros = [10, 7, 8, 9, 1, 5]
print(quick_sort(numeros))  # [1, 5, 7, 8, 9, 10]
```

---

# 4️⃣ Dicas do professor anos 90

- Para listas pequenas, **Bubble, Insertion ou Selection** são suficientes.
- Para listas grandes, prefira **Merge ou Quick Sort**.
- Sempre visualize como organizar suas fitas, cartuchos ou figurinhas de forma sistemática.
- Merge Sort e Quick Sort usam a técnica **divide e conquista**, como dividir fases de um jogo e ordenar separadamente.

---

# 5️⃣ Comparação Visual (anos 90 style)

```
Lista: [5, 1, 4, 2, 8]

Bubble Sort passagens:
Passo 1: [1, 5, 4, 2, 8]
Passo 2: [1, 4, 5, 2, 8]
Passo 3: [1, 4, 2, 5, 8]
Passo 4: [1, 2, 4, 5, 8]

Insertion Sort passagens:
[5, 1, 4, 2, 8] -> [1, 5, 4, 2, 8] -> [1, 4, 5, 2, 8] -> [1, 2, 4, 5, 8] -> [1, 2, 4, 5, 8]

Selection Sort passagens:
[5, 1, 4, 2, 8] -> [1, 5, 4, 2, 8] -> [1, 2, 4, 5, 8] -> [1, 2, 4, 5, 8] -> [1, 2, 4, 5, 8]

Merge Sort passagens:
[5, 1, 4, 2, 8] -> dividir [5, 1, 4] & [2, 8] -> ordenar -> [1, 4, 5, 2, 8] -> juntar -> [1, 2, 4, 5, 8]

Quick Sort passagens:
[5, 1, 4, 2, 8] -> pivot=5 -> menores=[1,4,2], maiores=[8] -> ordenar menores -> [1,2,4] -> juntar -> [1,2,4,5,8]
```

---

