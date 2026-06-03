

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

// 1. Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
struct Node {
    int data;
    struct Node* next;
};

// 2. Declare a global variable head representing the starting node of the linked list.
struct Node* head = NULL;

// 3. Define a function display to print the elements of the linked list.
void display() {
    // 4. Declare a pointer p and initialize it with the head of the linked list.
    struct Node* p = head;

    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements (Top to Bottom):\n");
    // 5. Use a while loop to traverse the linked list:
    while (p != NULL) {
        // 6. Print the data of the current node.
        printf("%d\n", p->data);

        // 7. Move to the next node using the next pointer.
        p = p->next;
    }
}

// Helper function to push elements onto the stack
void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Stack Overflow.\n");
        return;
    }
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

int main() {
    // Pushing elements to demonstrate the display function
    push(10);
    push(20);
    push(30);

    // Call the display function
    display();

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

<img width="416" height="233" alt="image" src="https://github.com/user-attachments/assets/96bc122b-79ba-437e-90ee-c340871f4912" />



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

// Function to pop an element from the stack matching the algorithm
void pop() {
    // 1. Check for Empty Stack
    // 2. If head is equal to NULL, Print "Stack is empty."
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    
    // 3. Else Proceed to the next step.
    struct Node* temp = head;
    printf("Popped element: %d\n", temp->data);
    
    // 4. Set head to point to the next node in the stack.
    head = head->next;
    
    // Free the memory of the popped node
    free(temp);
}

// Helper function to push elements onto the stack
void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Stack Overflow.\n");
        return;
    }
    newNode->data = value;
    newNode->next = head;
    head = newNode;
    printf("Pushed %d onto the stack.\n", value);
}

int main() {
    push(10);
    push(20);
    push(30);

    pop();
    pop();
    pop();
    pop(); // Attempt to pop from an empty stack

    return 0;
}
```

Output:

<img width="457" height="325" alt="image" src="https://github.com/user-attachments/assets/71193b9c-7893-4ee1-ad92-b228dec3072e" />




Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

// Global pointers for the queue
struct Node* front = NULL;
struct Node* rear = NULL;

// Function to display queue elements matching the algorithm
void display() {
    // 1. Check if Queue is Empty
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }

    // 2. Display Queue Elements
    // Using a temporary pointer to traverse so we don't lose the actual front of the queue
    struct Node* current = front; 
    
    printf("Queue elements: ");
    while (current != NULL) {
        // 3. Print the data of the current node pointed to by front (current)
        printf("%d ", current->data);

        // 4. Update front (current) to point to the next node.
        current = current->next;
    }
    printf("\n");
    // 5. End the display function.
}

// Helper function to insert elements into the queue
void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Queue Overflow.\n");
        return;
    }
    newNode->data = value;
    newNode->next = NULL;

    if (front == NULL && rear == NULL) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    // Call the display function
    display();

    // Clean up memory
    struct Node* temp;
    while (front != NULL) {
        temp = front;
        front = front->next;
        free(temp);
    }

    return 0;
}
```

Output:

<img width="434" height="210" alt="image" src="https://github.com/user-attachments/assets/7e15b777-b083-4f99-bb48-5e6038b80c06" />


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

// Global pointers for the queue
struct Node* front = NULL;
struct Node* rear = NULL;

// Function to insert elements in a queue using a linked list
void enqueue(int value) {
    // 1. Allocate Memory for New Node
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    if (p == NULL) {
        printf("Queue Overflow.\n");
        return;
    }

    // 2. Set Data and Next Pointer
    p->data = value;
    p->next = NULL;

    // 3. Check if Queue is Empty
    if (front == NULL && rear == NULL) {
        // 4. Set both front and rear to point to the new node p.
        front = rear = p;
    } else {
        // 5. Set the next pointer of the current rear to point to the new node p.
        rear->next = p;
        rear = p; // Move rear to the new node
    }
    
    printf("Inserted %d into the queue.\n", value);
    // 6. End of Enqueue Operation
}

// Helper function to display the queue
void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    struct Node* temp = front;
    printf("Queue elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    // Perform enqueue operations
    enqueue(10);
    enqueue(20);
    enqueue(30);

    // Display queue contents
    display();

    // Clean up memory
    struct Node* temp;
    while (front != NULL) {
        temp = front;
        front = front->next;
        free(temp);
    }

    return 0;
}
```

Output:

<img width="470" height="314" alt="image" src="https://github.com/user-attachments/assets/500c116e-313a-4254-8d26-8aa1572c24bf" />


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

// Global pointers for the queue
struct Node* front = NULL;
struct Node* rear = NULL;

// Function to retrieve the "peek" element matching the algorithm
int peek() {
    // 1. Check if the queue is empty:
    // If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
    if (front == NULL) {
        printf("Queue is empty. Cannot peek.\n");
        return -1; // Returning -1 as an error indicator
    }

    // 2. Access the front element:
    // If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).
    return front->data;
}

// Helper function to insert elements into the queue
void enqueue(int value) {
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    if (p == NULL) {
        printf("Queue Overflow.\n");
        return;
    }
    p->data = value;
    p->next = NULL;

    if (front == NULL && rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

int main() {
    // Attempting to peek at an empty queue
    int val1 = peek();

    // Adding elements to the queue
    enqueue(10);
    enqueue(20);
    enqueue(30);

    // Peeking at the front element
    int val2 = peek();
    if (val2 != -1) {
        printf("The front element (peek) is: %d\n", val2);
    }

    // Clean up memory
    struct Node* temp;
    while (front != NULL) {
        temp = front;
        front = front->next;
        free(temp);
    }

    return 0;
}

```

Output:

<img width="426" height="204" alt="image" src="https://github.com/user-attachments/assets/5d90ba00-ac84-42bd-90b6-7c4f0672f982" />




Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


