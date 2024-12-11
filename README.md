class Node:
    def __init__(self, data=None):
        self.data = data
        self.next = None
class SLL:
    def __init__(self):
        self.head = None
    def append(self, data):
        new_node = Node(data)
        if self.head is None:
            self.head = new_node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node
    def display(self):
        current = self.head
        while current:
            print(current.data, end="  ")
            current = current.next
        print("")
    def reverse(self):
        prev = None
        current = self.head
        while current:
            next_node = current.next
            current.next = prev
            prev = current
            current = next_node
        self.head = prev
def main():
    sll = SLL()
    n = int(input("Enter the number of nodes: "))
    for _ in range(n):
        data = int(input("Enter the data for the node: "))
        sll.append(data)
    print("Original list:")
    sll.display()
    sll.reverse()
    print("Reversed list:")
    sll.display()
if __name__ == "__main__":
    main()
