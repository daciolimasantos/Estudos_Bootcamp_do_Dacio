**Guia Prático de Trees – Introdução**

---

# 1️⃣ Conceito Geral

Uma **Tree (Árvore)** é uma estrutura de dados hierárquica composta por **nós**, onde cada nó pode ter zero ou mais nós filhos, mas **apenas um nó pai** (exceto a raiz, que não tem pai).

Analogia anos 90: pense em uma árvore genealógica ou no menu de um jogo de RPG, onde cada menu principal leva a submenus. A raiz é o ponto de partida, e cada nó representa uma decisão ou elemento do jogo.

---

# 2️⃣ Terminologia de Árvores

| Termo           | Descrição                     | Analogia anos 90                     |
| --------------- | ----------------------------- | ------------------------------------ |
| Raiz (Root)     | Nó inicial da árvore          | Menu principal de RPG                |
| Nó (Node)       | Cada elemento da árvore       | Menu ou submenu                      |
| Filho (Child)   | Nó ligado a outro nó superior | Submenu ligado a um menu principal   |
| Pai (Parent)    | Nó que tem filhos             | Menu principal que leva a submenus   |
| Folha (Leaf)    | Nó sem filhos                 | Último submenu sem opções adicionais |
| Altura (Height) | Número de níveis da árvore    | Número de telas de menu até o final  |

---

# 3️⃣ Tipos Comuns de Árvores

| Tipo               | Característica                                                          | Analogia anos 90                                                                   |
| ------------------ | ----------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Binary Tree        | Cada nó tem no máximo 2 filhos                                          | Jogador escolhe entre duas portas no jogo                                          |
| Binary Search Tree | Binary Tree com valores ordenados: filho esquerdo < pai < filho direito | Árvores de decisões onde escolhas menores vão para esquerda e maiores para direita |
| Balanced Tree      | Altura da árvore minimizada para eficiência                             | Menu bem organizado, onde é fácil chegar em qualquer submenu rapidamente           |

---

# 4️⃣ Implementação Básica em Python (Binary Tree)

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

# Criando a árvore
root = Node(10)
root.left = Node(5)
root.right = Node(15)
root.left.left = Node(3)
root.left.right = Node(7)
root.right.left = Node(12)
root.right.right = Node(18)

# Função para percorrer a árvore em ordem (Inorder Traversal)
def inorder(node):
    if node:
        inorder(node.left)
        print(node.data, end=' ')
        inorder(node.right)

inorder(root)  # Saída: 3 5 7 10 12 15 18
```

Analogia anos 90: percorrer a árvore é como explorar todas as opções de menu em ordem, da esquerda para a direita.

---

# 5️⃣ Dicas do professor anos 90

- Árvores são ideais para **representar hierarquias** e **estruturas de decisão**.
- **Binary Search Trees (BST)** tornam a busca mais rápida, similar a usar mapas de labirintos para encontrar tesouros rapidamente.
- Sempre visualize a raiz como o ponto inicial e siga os ponteiros para navegar pelos nós filhos.

---

# 6️⃣ Comparação Visual (anos 90 style)

```
        10
       /  \
      5    15
     / \   / \
    3   7 12 18
```

- Raiz: 10
- Folhas: 3, 7, 12, 18
- Inorder Traversal: 3 5 7 10 12 15 18
