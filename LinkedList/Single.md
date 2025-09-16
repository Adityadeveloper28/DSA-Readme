# Singly Linked List in C++

This document provides an overview and explanation of the Singly Linked List implementation in C++ as provided in `Single.md`.

## Features
- Insert at the beginning
- Insert at the end
- Insert at a specific position
- Print the list
- (Menu structure for delete/search, but not implemented in the code above)

## Data Structures

### Node Structure
```cpp
struct Node {
    int data; // store value
    Node* next; // store next pointer value
    Node(int val) : data(val), next(nullptr) {}
};
```

### SinglyLinkedList Class
- `insertAtEnd(int val)`: Inserts a value at the end of the list.
- `insertAtBegin(int val)`: Inserts a value at the beginning of the list.
- `insertAtPosition(int pos, int val)`: Inserts a value at a specific position (0-based).
- `printList()`: Prints the entire list.

## Example Usage

```cpp
SinglyLinkedList list;
list.insertAtBegin(10);
list.insertAtEnd(20);
list.insertAtPosition(1, 15); // List: 10 -> 15 -> 20 -> Null
list.printList();
```

## Menu-Driven Program
The `main()` function provides a menu-driven interface for interacting with the linked list:

- Insert at Beginning
- Insert at End
- Insert at Position
- Display List

Other options (delete/search) are shown in the menu but not implemented in the code above.

## Sample Output
```
--- Singly Linked List Menu ---
1. Insert at Beginning
2. Insert at End
3. Insert at Position
4. Delete First
5. Delete Last
6. Delete at Position
7. Display List
8. Search Element
9. Exit
Enter your choice: 1
Enter value: 10
--- Singly Linked List Menu ---
...
```

## Notes
- The code uses basic C++ features and is suitable for beginners.
- Error handling is included for invalid positions.
- The delete and search functionalities are listed in the menu but not implemented in the provided code.

---

For more details, see the code in `LinkedList/Single.md`.
