**Guia Prático de Estruturas de Dados – Stack e Queue**

---

# 1️⃣ Conceito Geral

Em programação, **Stack (pilha)** e **Queue (fila)** são estruturas de dados que controlam a forma como os elementos são inseridos e removidos.

- **Stack (Pilha)** → segue a regra **LIFO (Last In, First Out)**: o último a entrar é o primeiro a sair.
- **Queue (Fila)** → segue a regra **FIFO (First In, First Out)**: o primeiro a entrar é o primeiro a sair.

Pense nelas como **caixas empilháveis ou filas de arcade nos anos 90**: cada uma com sua maneira de organizar os jogadores.

---

# 2️⃣ Stack (Pilha)

| Característica                | Descrição                                    | Exemplo Python | Analogia anos 90 |
| ----------------------------- | -------------------------------------------- | -------------- | ---------------- |
| LIFO                          | Último elemento inserido é o primeiro a sair | \`\`\`python   |                  |
| stack = []                    |                                              |                |                  |
| stack.append('Fita1')         |                                              |                |                  |
| stack.append('Fita2')         |                                              |                |                  |
| print(stack.pop())  # 'Fita2' |                                              |                |                  |

````|
| Mutável            | Pode adicionar ou remover elementos                | ```python
stack.append('Fita3')
stack.pop()
``` | Empilha ou remove a fita do topo |
| Usos comuns        | Desfazer ações, chamadas de função, histórico      | ```python
historico = []
historico.append('abrir jogo')
historico.pop()  # desfaz última ação
``` | Botão UNDO nos jogos |

**Operações principais:**
```python
stack.append(x)  # empilha
stack.pop()      # desempilha
stack[-1]        # olha o topo sem remover
len(stack)       # tamanho da pilha
````

---

# 3️⃣ Queue (Fila)

| Característica                       | Descrição                                      | Exemplo Python | Analogia anos 90 |
| ------------------------------------ | ---------------------------------------------- | -------------- | ---------------- |
| FIFO                                 | Primeiro elemento inserido é o primeiro a sair | \`\`\`python   |                  |
| from collections import deque        |                                                |                |                  |
| queue = deque()                      |                                                |                |                  |
| queue.append('Jogador1')             |                                                |                |                  |
| queue.append('Jogador2')             |                                                |                |                  |
| print(queue.popleft())  # 'Jogador1' |                                                |                |                  |

````|
| Mutável            | Pode adicionar ou remover elementos                | ```python
queue.append('Jogador3')
queue.popleft()
``` | Entrar na fila e ser chamado para jogar |
| Usos comuns        | Impressoras, simulações, filas de tarefas         | ```python
tarefas = deque()
tarefas.append('imprimir')
tarefas.popleft()
``` | Lista de espera no fliperama |

**Operações principais:**
```python
queue.append(x)     # enfileira
queue.popleft()     # desenfileira
queue[0]            # olha o primeiro da fila
len(queue)          # tamanho da fila
````

---

# 4️⃣ Comparação Visual (anos 90 style)

```
Stack: [Topo] Fita3, Fita2, Fita1 [Base]  # LIFO
Queue: [Frente] Jogador1, Jogador2, Jogador3 [Traseira]  # FIFO
```

---

# Dicas do professor anos 90

- **Stack:** use quando precisa desfazer ações ou seguir histórico.
- **Queue:** use quando precisa respeitar ordem de chegada ou processar tarefas sequenciais.

---

#
