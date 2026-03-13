**Guia Prático de Big O – Ciência da Computação (anos 90)**

---

# 1️⃣ Conceito

Big O mede quanto tempo ou esforço um algoritmo vai levar para processar os dados, conforme o tamanho da entrada (n).

- Foco no pior caso.
- Ignora constantes e operações menores.
- Expressa crescimento relativo, não tempo absoluto.

---

# 2️⃣ Tabela de Complexidades com Exemplos

| Big O | Nome | Descrição | Exemplo Python | Analogia anos 90 |
|-------|------|-----------|----------------|-----------------|
| `O(1)` | Constante | Tempo fixo, independente do tamanho da entrada | ```python
lista=[10,20,30]
print(lista[0])
``` | Passa o corredor sem inimigos |

| `O(log n)` | Logarítmica | Divide o problema pela metade a cada passo | ```python
def busca_binaria(lista, alvo):
    inicio, fim = 0, len(lista)-1
    while inicio <= fim:
        meio = (inicio+fim)//2
        if lista[meio]==alvo:
            return True
        elif lista[meio]<alvo:
            inicio = meio+1
        else:
            fim = meio-1
    return False
``` | Usa teletransporte e corta caminho |

| `O(n)` | Linear | Percorre todos os elementos uma vez | ```python
total=0
for num in lista:
    total+=num
``` | Derrota inimigos 1 a 1 |

| `O(n log n)` | Linearítmica | Combina linear + divisão (como merge sort) | ```python
def merge_sort(lista):
    if len(lista)<=1:
        return lista
    meio=len(lista)//2
    esquerda=merge_sort(lista[:meio])
    direita=merge_sort(lista[meio:])
    return merge(esquerda,direita)
``` | Derruba inimigos em grupos por corredor |

| `O(n²)` | Quadrática | Todos os pares ou dupla iteração | ```python
for i in lista:
    for j in lista:
        print(i,j)
``` | Luta com todos os inimigos de todos os corredores |

| `O(n³)` | Cúbica | Três loops aninhados | ```python
for i in lista:
    for j in lista:
        for k in lista:
            print(i,j,k)
``` | Cada corredor tem 3 inimigos e você enfrenta todos |

| `O(2^n)` | Exponencial | Cresce dobrando a cada entrada | ```python
def fib(n):
    if n<=1: return n
    return fib(n-1)+fib(n-2)
``` | Cada inimigo cria 2 novos inimigos cada turno |

| `O(n!)` | Fatorial | Cresce ultra rápido, não escalável | ```python
import itertools
for p in itertools.permutations(lista):
    print(p)
``` | Todos os inimigos fazem todas as combinações de ataques |

---

# 3️⃣ Dicas para Memorizar

- O(1) → "estou voando" → nada aumenta com n
- O(log n) → "teleporte" → corta metade do caminho
- O(n) → "caminhar corredor a corredor"
- O(n log n) → "caminhar + teletransporte em grupos"
- O(n²) → "luta com todo mundo em todos os corredores"
- O(n³), O(2^n), O(n!) → "modo impossível" → só para inputs pequenos

---

# 4️⃣ Exemplos Extras

```python
# O(1) – acessar elemento
lista = [1,2,3,4]
print(lista[-1])

# O(n) – soma
total = sum(lista)

# O(n²) – comparação de pares
for i in lista:
    for j in lista:
        if i != j:
            print(i,j)

# O(log n) – busca binária manual
def busca_binaria(lista, alvo):
    inicio, fim = 0, len(lista)-1
    while inicio <= fim:
        meio = (inicio+fim)//2
        if lista[meio] == alvo:
            return True
        elif lista[meio] < alvo:
            inicio = meio + 1
        else:
            fim = meio - 1
    return False
```

---

# Resumo visual (anos 90 style)

```
O(1)      ■
O(log n)  ■■
O(n)      ■■■■■
O(n log n)■■■■■■
O(n²)     ■■■■■■■■■■
O(2^n)    ■■■■■■■■■■■■■■■■■
O(n!)     ■■■■■■■■■■■■■■■■■■■■■■■
```

---



