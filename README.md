# aula
Unitins
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class Queue:
    def __init__(self):
        self.front = None
        self.rear = None

    def enqueue(self, data):
        new_node = Node(data)
        if self.rear is None:
            self.front = new_node
            self.rear = new_node
        else:
            self.rear.next = new_node
            self.rear = new_node

    def dequeue(self):
        if self.front is None:
            return None
        temp = self.front
        self.front = self.front.next
        if self.front is None:
            self.rear = None
        return temp.data

    def is_empty(self):
        return self.front is None

    def peek(self):
        if self.front is None:
            return None
        return self.front.data

    def display_queue(self):
        current = self.front
        while current:
            print(current.data, end=" ")
            current = current.next
        print()

# Criando uma fila
queue = Queue()

# Enfileirando elementos
queue.enqueue(1)
queue.enqueue(2)
queue.enqueue(3)
queue.enqueue(4)  # Adicionando elemento 4
queue.enqueue(5)  # Adicionando elemento 5
queue.enqueue(6)  # Adicionando elemento 6

# Exibindo o estado atual da fila
print("Estado atual da fila após enfileirar elementos:")
queue.display_queue()

# Desenfileirando elementos
print("\nRemovendo dois elementos da fila:")
queue.dequeue()
queue.dequeue()

# Exibindo o estado atual da fila após desenfileirar elementos
print("\nEstado atual da fila após desenfileirar elementos:")
queue.display_queue()

# Visualizando o primeiro elemento da fila
print("\nPrimeiro elemento da fila:", queue.peek())

# Verificando se a fila está vazia
if queue.is_empty():
    print("\nFila está vazia")
else:
    print("\nFila não está vazia")
