**Guia Prático de Linked List – Ciência da Computação**

---

# 1️⃣ Conceito Geral

Uma **Linked List (Lista Encadeada)** é uma estrutura de dados formada por **nós** onde cada nó contém:

- **Dado**: a informação que queremos armazenar
- **Referência (ou ponteiro)**: para o próximo nó da lista

Diferente das listas normais (arrays), os elementos não estão contíguos na memória. Isso permite **inserções e remoções rápidas** sem precisar mover todos os elementos.

Analogia anos 90: cada cartucho de jogo tem uma etiqueta apontando para o próximo cartucho na fila. Para chegar no 5º cartucho, você segue os apontamentos desde o 1º.

---

# 2️⃣ Tipos de Linked List

| Tipo                 | Característica                         | Analogia anos 90                                       |
| -------------------- | -------------------------------------- | ------------------------------------------------------ |
| Singly Linked List   | Cada nó aponta para o próximo          | Corrente de cartuchos: você só consegue ir para frente |
| Doubly Linked List   | Cada nó aponta para próximo e anterior | Fitas VHS com etiqueta frente e verso, pode voltar     |
| Circular Linked List | Último nó aponta para o primeiro       | Fita VHS loop: depois do último volta para o primeiro  |

---

# 3️⃣ Implementação em Python

## a) Singly Linked List

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        last = self.head
        while last.next:
            last = last.next
        last.next = new_node

    def print_list(self):
        current = self.head
        while current:
            print(current.data, end=' -> ')
            current = current.next
        print('None')

# Exemplo de uso
lista = LinkedList()
lista.append(10)
lista.append(20)
lista.append(30)
lista.print_list()  # 10 -> 20 -> 30 -> None
```

Analogia anos 90: cada nó é um cartucho de jogo, e o ponteiro é a etiqueta indicando o próximo cartucho.

---

# 4️⃣ Operações comuns

- **Inserir no início**: mudar a cabeça da lista
- **Inserir no fim**: percorrer até o último nó e adicionar
- **Remover nó**: alterar o ponteiro do nó anterior para pular o nó removido
- **Buscar nó**: percorrer a lista até encontrar o dado desejado

```python
# Inserir no início
def prepend(self, data):
    new_node = Node(data)
    new_node.next = self.head
    self.head = new_node

# Remover nó
def remove(self, key):
    current = self.head
    prev = None
    while current and current.data != key:
        prev = current
        current = current.next
    if current is None:
        return
    if prev is None:
        self.head = current.next
    else:
        prev.next = current.next
```

---

# 5️⃣ Dicas do professor anos 90

- Linked lists são ótimas quando você precisa de **inserções e remoções rápidas**.
- Não são ideais se você precisa acessar elementos por índice frequentemente (precisa percorrer toda a lista).
- Visualize como uma fila de fitas ou cartuchos interligados por etiquetas: você precisa seguir a sequência para chegar em qualquer ponto.

---

# 6️⃣ Comparação Visual (anos 90 style)

```
Cabeça -> 10 -> 20 -> 30 -> None
Inserir 5 no início: 5 -> 10 -> 20 -> 30 -> None
Remover 20: 5 -> 10 -> 30 -> None
```

---

#

