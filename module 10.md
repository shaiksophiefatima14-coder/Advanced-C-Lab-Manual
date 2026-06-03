EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

// 1. Define the structure for a node in a linked list.
struct Node {
    char data;
    struct Node* next;
};

// 2. Define the search function to find a specific character in the linked list.
int search(struct Node* head, char target) {
    struct Node* current = head;
    while (current != NULL) {
        if (current->data == target) {
            return 1; // Element found
        }
        current = current->next;
    }
    return 0; // Element not found
}

// Helper function to insert a node at the beginning
void insert(struct Node** head_ref, char new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = new_data;
    new_node->next = (*head_ref);
    (*head_ref) = new_node;
}

int main() {
    // 3. Initialize the head of the linked list as needed.
    struct Node* head = NULL;
    char target;

    insert(&head, 'D');
    insert(&head, 'C');
    insert(&head, 'B');
    insert(&head, 'A'); // List becomes: A -> B -> C -> D -> NULL

    printf("Enter a character to search: ");
    scanf(" %c", &target);

    // 4. Call the search function and perform other linked list operations as needed.
    if (search(head, target)) {
        printf("Element '%c' found in the linked list.\n", target);
    } else {
        printf("Element '%c' not found in the linked list.\n", target);
    }

    // Clean up memory
    struct Node* temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```
Output:

<img width="528" height="251" alt="image" src="https://github.com/user-attachments/assets/f0c67c4e-04e5-499a-affc-6b92b4460180" />




Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

// 1. Define the structure for a node in a linked list
struct Node {
    char data;
    struct Node* next;
};

// 2. Define the insert function to insert a new node with character data at the end of the linked list.
void insert(struct Node** head_ref, char new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head_ref;

    new_node->data = new_data;
    new_node->next = NULL;

    // If the Linked List is empty, then make the new node as head
    if (*head_ref == NULL) {
        *head_ref = new_node;
        return;
    }

    // Else traverse till the last node
    while (last->next != NULL) {
        last = last->next;
    }

    // Change the next of last node
    last->next = new_node;
}

// Helper function to print the linked list
void displayList(struct Node* node) {
    while (node != NULL) {
        printf("%c -> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

int main() {
    // 3. Initialize the head of the linked list as needed.
    struct Node* head = NULL;

    // 4. Call the insert function and perform other linked list operations as needed.
    insert(&head, 'A');
    insert(&head, 'B');
    insert(&head, 'C');
    insert(&head, 'D');

    printf("Linked List after insertion at the end:\n");
    displayList(head);

    // Clean up memory
    struct Node* temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```

Output:

<img width="472" height="147" alt="image" src="https://github.com/user-attachments/assets/16259e5d-63f3-4f75-aa60-9b84fb474c87" />


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
    struct Node* prev;
};

void traverse(struct Node* head) {
    // 1. Initialize a temporary pointer (temp) to the head of the list.
    struct Node* temp = head;

    printf("Doubly Linked List elements: ");
    // 2. Use a while loop to traverse the list until the end (temp == NULL) is reached.
    while (temp != NULL) {
        // 3. Inside the loop, print the data of the current node.
        printf("%c ", temp->data);

        // 4. Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
        temp = temp->next;
    }
    printf("\n");
}

// Helper function to insert a node at the end of the doubly linked list
void insertEnd(struct Node** head_ref, char new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head_ref;

    new_node->data = new_data;
    new_node->next = NULL;

    if (*head_ref == NULL) {
        new_node->prev = NULL;
        *head_ref = new_node;
        return;
    }

    while (last->next != NULL) {
        last = last->next;
    }

    last->next = new_node;
    new_node->prev = last;
}

int main() {
    struct Node* head = NULL;

    insertEnd(&head, 'A');
    insertEnd(&head, 'B');
    insertEnd(&head, 'C');
    insertEnd(&head, 'D');

    traverse(head);

    // Clean up memory
    struct Node* temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```

Output:

<img width="486" height="222" alt="image" src="https://github.com/user-attachments/assets/7d2df36b-4ab9-431f-bb97-f2ee3028ca14" />



Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};

void insertEnd(struct Node** head_ref, int new_data) {
    // 1. Create a new node (newNode) and allocate memory for it.
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    
    // 2. Set the data of the new node to the provided value.
    newNode->data = new_data;
    newNode->next = NULL;

    // 3. If the list is empty, set the new node as the head.
    if (*head_ref == NULL) {
        newNode->prev = NULL;
        *head_ref = newNode;
        return;
    }

    // 4. If the list is not empty, traverse the list to find the last node.
    struct Node* last = *head_ref;
    while (last->next != NULL) {
        last = last->next;
    }

    // 5. Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
    last->next = newNode;
    newNode->prev = last;
}

void displayList(struct Node* node) {
    printf("Doubly Linked List: ");
    while (node != NULL) {
        printf("%d ", node->data);
        node = node->next;
    }
    printf("\n");
}

int main() {
    struct Node* head = NULL;

    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);

    displayList(head);

    // Clean up memory
    struct Node* temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```

Output:
<img width="517" height="169" alt="image" src="https://github.com/user-attachments/assets/eb8328b0-5714-4de8-998f-9cdb6e8b0c50" />


Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

// Function to delete a given element from a linked list
void deleteElement(struct Node** head_ref, int key) {
    // 1. Check if the Linked List is Empty
    if (*head_ref == NULL) {
        printf("The list is empty.\n");
        return;
    }

    struct Node* current = *head_ref;
    struct Node* prev = NULL;

    // 3. Handle Deletion of the First Node
    if (current != NULL && current->data == key) {
        *head_ref = current->next; // Update head
        free(current);             // Free memory
        printf("Element %d deleted from the list.\n", key);
        return;
    }

    // 2 & 4. Traverse and Delete from the Middle or End
    while (current != NULL && current->data != key) {
        prev = current;
        current = current->next;
    }

    // 5. Handle the Case when the Element is Not Found
    if (current == NULL) {
        printf("Element %d is not present in the list.\n", key);
        return;
    }

    // Unlink the node from the linked list and free memory
    prev->next = current->next;
    free(current);
    printf("Element %d deleted from the list.\n", key);
}

// Helper function to insert a node at the beginning
void push(struct Node** head_ref, int new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = new_data;
    new_node->next = (*head_ref);
    (*head_ref) = new_node;
}

// Helper function to print the linked list
void displayList(struct Node* node) {
    while (node != NULL) {
        printf("%d -> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;

    push(&head, 40);
    push(&head, 30);
    push(&head, 20);
    push(&head, 10);

    printf("Original List: ");
    displayList(head);

    // Delete a middle element
    deleteElement(&head, 30);
    displayList(head);

    // Delete the head element
    deleteElement(&head, 10);
    displayList(head);

    // Try deleting an element that doesn't exist
    deleteElement(&head, 100);

    // Clean up remaining memory
    struct Node* temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```

Output:

<img width="522" height="269" alt="image" src="https://github.com/user-attachments/assets/557dd0f9-cf6f-4285-8520-e307bbb057a5" />






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





