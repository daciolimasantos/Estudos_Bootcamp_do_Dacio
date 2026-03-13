**Guia Prático de Estruturas de Dados – List, Dict e Set (anos 90)**

---

# 1️⃣ Conceito Geral

Em Python (e na programação em geral), usamos **estruturas de dados** para armazenar e organizar informações de forma eficiente. As três mais comuns são:

- **List** (lista) → coleção ordenada de elementos, permite duplicatas e acesso por índice.
- **Dict** (dicionário) → coleção de pares chave-valor, eficiente para buscas rápidas por chave.
- **Set** (conjunto) → coleção de elementos únicos, não ordenada, ideal para eliminar duplicatas e operações matemáticas de conjuntos.

Pense nelas como diferentes tipos de **caixas para guardar coisas**, cada uma com suas regras e superpoderes.

---

# 2️⃣ List (Lista)

| Característica           | Descrição                  | Exemplo Python | Analogia anos 90 |
| ------------------------ | -------------------------- | -------------- | ---------------- |
| Ordenada                 | Mantém a ordem de inserção | \`\`\`python   |                  |
| lista = [10, 20, 30, 40] |                            |                |                  |
| print(lista[2])  # 30    |                            |                |                  |

````|
| Mutável | Pode adicionar, remover ou alterar elementos | ```python
lista.append(50)
lista[1] = 25
``` | Adicionar ou trocar a fita no player |
| Permite duplicatas | Mesmos valores podem existir várias vezes | ```python
lista = [1, 2, 2, 3]
``` | Vários cartuchos iguais no estojo |

**Operações comuns:**
```python
lista.append(5)     # adicionar no final
lista.insert(1, 99) # adicionar no índice 1
lista.remove(2)     # remove primeira ocorrência
len(lista)          # tamanho da lista
lista[0]            # acessar o primeiro elemento
````

---

# 3️⃣ Dict (Dicionário)

| Característica                     | Descrição                                                             | Exemplo Python | Analogia anos 90 |
| ---------------------------------- | --------------------------------------------------------------------- | -------------- | ---------------- |
| Não ordenado\*                     | A ordem das chaves pode não ser a inserida (Python 3.7+ mantém ordem) | \`\`\`python   |                  |
| dict = {'nome':'Mario','idade':30} |                                                                       |                |                  |
| print(dict['nome'])  # Mario       |                                                                       |                |                  |

````|
| Mutável | Pode adicionar, alterar ou remover chaves/valores | ```python
dict['idade'] = 31
dict['cidade'] = 'São Paulo'
``` | Escrever ou atualizar o contato na agenda |
| Chaves únicas | Cada chave só aparece uma vez | ```python
dict = {'a':1,'b':2}
``` | Não dá para ter dois contatos com o mesmo nome |

**Operações comuns:**
```python
dict.keys()     # todas as chaves
dict.values()   # todos os valores
dict.items()    # pares chave-valor
'dict.get('nome')'  # busca segura da chave
````

---

# 4️⃣ Set (Conjunto)

| Característica | Descrição                       | Exemplo Python | Analogia anos 90 |
| -------------- | ------------------------------- | -------------- | ---------------- |
| Não ordenado   | Ordem dos elementos não importa | \`\`\`python   |                  |
| s = {1,2,3}    |                                 |                |                  |

````|
| Elementos únicos | Não permite duplicatas | ```python
s = {1,2,2,3}  # resulta em {1,2,3}
``` | Cada figurinha só existe uma vez |
| Operações de conjunto | União, interseção, diferença | ```python
a = {1,2,3}
b = {2,3,4}
print(a & b)  # interseção {2,3}
print(a | b)  # união {1,2,3,4}
``` | Comparar figurinhas com amigos |

**Operações comuns:**
```python
s.add(5)      # adiciona elemento
s.remove(2)   # remove elemento
len(s)        # tamanho do set
````

---

# 5️⃣ Comparação Visual (anos 90 style)

```
List:  [10, 20, 30, 30, 40]  # ordenada, permite duplicatas
Dict:  {'nome':'Mario','idade':30}  # chave única, busca rápida
Set:   {1, 2, 3, 4}  # único, não ordenado, operações de conjunto
```

---

# Dicas do professor anos 90

- **Lista:** quando precisa de ordem e duplicatas.
- **Dicionário:** quando precisa achar coisas rapidamente por uma chave.
- **Set:** quando precisa de elementos únicos e operações matemáticas.

---

#

