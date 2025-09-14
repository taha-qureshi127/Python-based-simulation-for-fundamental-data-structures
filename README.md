class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.head = None

    def add_at_start(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node

    def add_at_end(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        last = self.head
        while last.next:
            last = last.next
        last.next = new_node

    def delete_from_start(self):
        if self.head:
            self.head = self.head.next

    def delete_from_end(self):
        if not self.head:
            return
        if not self.head.next:
            self.head = None
            return
        second_last = self.head
        while second_last.next.next:
            second_last = second_last.next
        second_last.next = None

    def display(self):
        current = self.head
        while current:
            print(current.data, end=" -> ")
            current = current.next
        print("None")

# Implementing Stack using List
class Stack:
    def __init__(self):
        self.stack = []

    def push(self, data):
        self.stack.append(data)

    def pop(self):
        if not self.is_empty():
            return self.stack.pop()
        return "Stack is empty!"

    def peek(self):
        if not self.is_empty():
            return self.stack[-1]
        return "Stack is empty!"

    def is_empty(self):
        return len(self.stack) == 0

# Implementing Queue using List
class Queue:
    def __init__(self):
        self.queue = []

    def enqueue(self, data):
        self.queue.append(data)

    def dequeue(self):
        if not self.is_empty():
            return self.queue.pop(0)
        return "Queue is empty!"

    def is_empty(self):
        return len(self.queue) == 0

# Implementing Deque using List
class Deque:
    def __init__(self):
        self.deque = []

    def add_front(self, data):
        self.deque.insert(0, data)

    def add_rear(self, data):
        self.deque.append(data)

    def remove_front(self):
        if not self.is_empty():
            return self.deque.pop(0)
        return "Deque is empty!"

    def remove_rear(self):
        if not self.is_empty():
            return self.deque.pop()
        return "Deque is empty!"

    def is_empty(self):
        return len(self.deque) == 0

class Graph:
    def __init__(self):
        self.graph = {}

    def add_vertex(self, vertex):
        if vertex not in self.graph:
            self.graph[vertex] = []

    def add_edge(self, vertex, edge):
        if vertex in self.graph:
            self.graph[vertex].append(edge)

    def display(self):
        for vertex in self.graph:
            print(f"{vertex}: {', '.join(map(str, self.graph[vertex]))}")

class Menu:
    def __init__(self):
        self.run()

    def run(self):
        while True:
            print("\nMain Menu:")
            print("1. Linked List")
            print("2. Stack")
            print("3. Queue")
            print("4. Tree")
            print("5. Graph")
            print("6. Bubble Sort")
            print("7. Exit")
            choice = input("Choose an option: ")

            if choice == '1':
                self.linked_list_menu()
            elif choice == '2':
                self.stack_menu()
            elif choice == '3':
                self.queue_menu()
            elif choice == '4':
                self.tree_menu()
            elif choice == '5':
                self.graph_menu()
            elif choice == '6':
                self.bubble_sort_menu()
            elif choice == '7':
                print("Exiting...")
                break
            else:
                print("Invalid choice, please try again.")

    def linked_list_menu(self):
        while True:
            print("\nLinked List Menu:")
            print("1. Singly Linked List")
            print("2. Doubly Linked List")
            print("3. Circular Linked List")
            print("4. Back")
            choice = input("Choose an option: ")

            if choice == '1':
                self.singly_linked_list_operations()
            elif choice == '2':
                self.doubly_linked_list_operations()
            elif choice == '3':
                self.circular_linked_list_operations()
            elif choice == '4':
                break
            else:
                print("Invalid choice.")

    def singly_linked_list_operations(self):
        linked_list = SinglyLinkedList()
        while True:
            print("\nSingly Linked List Operations:")
            print("1. Add at Start")
            print("2. Add at End")
            print("3. Delete from Start")
            print("4. Delete from End")
            print("5. Display")
            print("6. Back")
            choice = input("Choose an option: ")

            if choice == '1':
                data = input("Enter data: ")
                linked_list.add_at_start(data)
            elif choice == '2':
                data = input("Enter data: ")
                linked_list.add_at_end(data)
            elif choice == '3':
                linked_list.delete_from_start()
            elif choice == '4':
                linked_list.delete_from_end()
            elif choice == '5':
                linked_list.display()
            elif choice == '6':
                break
            else:
                print("Invalid choice.")

    def doubly_linked_list_operations(self):
        # Implement operations for doubly linked list here
        pass

    def circular_linked_list_operations(self):
        # Implement operations for circular linked list here
        pass

    def stack_menu(self):
        stack = Stack()
        while True:
            print("\nStack Options:")
            print("1. Push")
            print("2. Pop")
            print("3. Peek")
            print("4. Check Empty")
            print("5. Back")
            choice = input("Choose an option: ")

            if choice == '1':
                data = input("Enter data: ")
                stack.push(data)
            elif choice == '2':
                print("Popped:", stack.pop())
            elif choice == '3':
                print("Top element:", stack.peek())
            elif choice == '4':
                print("Is stack empty?", stack.is_empty())
            elif choice == '5':
                break
            else:
                print("Invalid choice.")

    def queue_menu(self):
        while True:
            print("\nQueue Options:")
            print("1. Queue using List")
            print("2. Queue using Linked List")
            print("3. Deque")
            print("4. Back")
            choice = input("Choose an option: ")

            if choice == '1':
                self.queue_using_list()
            elif choice == '2':
                self.queue_using_linked_list()
            elif choice == '3':
                self.deque_operations()
            elif choice == '4':
                break
            else:
                print("Invalid choice.")

    def queue_using_list(self):
        queue = Queue()
        while True:
            print("\nList Queue Operations:")
            print("1. Enqueue")
            print("2. Dequeue")
            print("3. Check Empty")
            print("4. Back")
            choice = input("Choose an option: ")

            if choice == '1':
                data = input("Enter data: ")
                queue.enqueue(data)
            elif choice == '2':
                print("Dequeued:", queue.dequeue())
            elif choice == '3':
                print("Is queue empty?", queue.is_empty())
            elif choice == '4':
                break
            else:
                print("Invalid choice.")

    def queue_using_linked_list(self):
        linked_queue = SinglyLinkedList()
        while True:
            print("\nLinked List Queue Operations:")
            print("1. Enqueue")
            print("2. Dequeue")
            print("3. Check Empty")
            print("4. Back")
            choice = input("Choose an option: ")

            if choice == '1':
                data = input("Enter data: ")
                linked_queue.add_at_end(data)
            elif choice == '2':
                if linked_queue.head:
                    print("Dequeued:", linked_queue.head.data)
                    linked_queue.delete_from_start()
                else:
                    print("Queue is empty!")
            elif choice == '3':
                print("Is queue empty?", linked_queue.head is None)
            elif choice == '4':
                break
            else:
                print("Invalid choice.")

    def deque_operations(self):
        deque = Deque()
        while True:
            print("\nDeque Operations:")
            print("1. Add Front")
            print("2. Add Rear")
            print("3. Remove Front")
            print("4. Remove Rear")
            print("5. Check Empty")
            print("6. Back")
            choice = input("Choose an option: ")

            if choice == '1':
                data = input("Enter data: ")
                deque.add_front(data)
            elif choice == '2':
                data = input("Enter data: ")
                deque.add_rear(data)
            elif choice == '3':
                print("Removed from front:", deque.remove_front())
            elif choice == '4':
                print("Removed from rear:", deque.remove_rear())
            elif choice == '5':
                print("Is deque empty?", deque.is_empty())
            elif choice == '6':
                break
            else:
                print("Invalid choice.")

    def tree_menu(self):
        tree = BinaryTree()
        while True:
            print("\nBinary Tree Options:")
            print("1. Insert")
            print("2. Display Inorder")
            print("3. Back")
            choice = input("Choose an option: ")

            if choice == '1':
                data = int(input("Enter data: "))
                tree.insert(data)
            elif choice == '2':
                print("Inorder Traversal:")
                tree.inorder(tree.root)
                print()
            elif choice == '3':
                break
            else:
                print("Invalid choice.")

    def graph_menu(self):
        graph = Graph()
        while True:
            print("\nGraph Options:")
            print("1. Add Vertex")
            print("2. Add Edge")
            print("3. Display")
            print("4. Back")
            choice = input("Choose an option: ")

            if choice == '1':
                vertex = input("Enter vertex: ")
                graph.add_vertex(vertex)
            elif choice == '2':
                vertex = input("Enter vertex: ")
                edge = input("Enter edge: ")
                graph.add_edge(vertex, edge)
            elif choice == '3':
                graph.display()
            elif choice == '4':
                break
            else:
                print("Invalid choice.")

    def bubble_sort_menu(self):
        print("\nBubble Sort Menu:")
        data = input("Enter numbers separated by spaces: ")
        array = list(map(int, data.split()))
        self.bubble_sort(array)
        print("Sorted array:", array)

    def bubble_sort(self, arr):
        n = len(arr)
        for i in range(n):
            for j in range(0, n-i-1):
                if arr[j] > arr[j+1]:
                    arr[j], arr[j+1] = arr[j+1], arr[j]

if __name__ == "__main__":
    Menu()
