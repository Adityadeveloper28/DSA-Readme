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


---

## Full C++ Code Example

```cpp
// Online C++ compiler to run C++ program online
#include <iostream>
using namespace std;

struct Node {
    int data; //store value 
    Node* next; /// store next pointer value
    Node(int val) : data(val),next(nullptr){}
};

class SinglyLinkedList {
    private :
        Node* head;
    public:
        SinglyLinkedList():head(nullptr){}
        
        ///akhir me value insert karna
        void insertAtEnd(int val){
            Node* node = new Node(val);
            if(!head){
                head=node;
                return;
            }
            Node* cur = head;
            while(cur->next){
                cur= cur->next;
            }
            cur->next = node ;
        }
        
        //aage insert karna hai 
        void insertAtBegin(int val){
            Node* node = new Node(val); //node me value dala  
            node->next = head; //uske next to head banaya
            head = node; //new node head ban gaya 
        }
        
        ///insert at position
        void insertAtPosition(int pos,int val){
            if(pos<0){
                cout<<"invalid Positon\n";
                return;
            }
            if(pos==0){
                insertAtBegin(val);
                return;
            }
            Node* cur = head;
            for(int i=0;i<pos-1 && cur;++i){
                cur=cur->next;
            }
            if(!cur){
                cout<<"positon out of range";
                return;
            }
            Node* node = new Node(val);
            node->next = cur->next;
            cur->next=node;
        }
        
        void printList(){
            if(!head){
                cout<<"list is empty";return;
            }
            Node* cur = head;
            while(cur){
                cout<<cur->data;
                if(cur->next) cout<<"->";
                cur=cur->next;
            }
            cout<<"->Null\n";
        }
};

int main() {
   SinglyLinkedList list;
   int choice,val,pos;
   
   do{
        cout << "\n--- Singly Linked List Menu ---\n";
        cout << "1. Insert at Beginning\n";
        cout << "2. Insert at End\n";
        cout << "3. Insert at Position\n";
        cout << "4. Delete First\n";
        cout << "5. Delete Last\n";
        cout << "6. Delete at Position\n";
        cout << "7. Display List\n";
        cout << "8. Search Element\n";
        cout << "9. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;
        
        switch(choice){
            case 1:
                cout << "Enter value: ";
                cin >> val;
                list.insertAtBegin(val);
                break;
            case 2:
                cout << "Enter value: ";
                cin >> val;
                list.insertAtEnd(val);
                break;
            case 3:
                cout << "Enter position (0-based) and value: ";
                cin >> pos >> val;
                list.insertAtPosition(pos, val);
                break;
            case 7:
                list.printList();
                break;
             default:
                cout << "Invalid choice!\n";
        }
        
   }while(choice!=9);
   
   return 0;
}
```
