EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

#define MAX 5

int stack[MAX];
int top = -1;

void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
        return;
    }
    printf("Stack elements from top to bottom:\n");
    for (int i = top; i >= 0; i--) {
        printf("%d\n", stack[i]);
    }
}

void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %d\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("Pushed %d onto the stack.\n", value);
    }
}

int main() {
    push(10);
    push(20);
    push(30);

    display();

    return 0;
}
```

Output:

<img width="497" height="306" alt="image" src="https://github.com/user-attachments/assets/4c809385-a9e0-4700-92aa-254ede7a4d3b" />




Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:

```
#include <stdio.h>

#define MAX 5

float stack[MAX];
int top = -1;

void push(float value) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %.2f\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("Pushed %.2f onto the stack.\n", value);
    }
}

int main() {
    push(10.5);
    push(20.3);
    push(30.8);

    return 0;
}
```

Output:

<img width="460" height="198" alt="image" src="https://github.com/user-attachments/assets/9340fd45-9b0e-4293-94b9-ab4893ab65e7" />





Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

```
#include <stdio.h>

#define MAX 5

int queue[MAX];
int front = 0;
int rear = -1;
int i; 

void display() {
    if (front > rear) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Queue elements: ");
    for (i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
}

int main() {
    rear++;
    queue[rear] = 10;
    rear++;
    queue[rear] = 20;
    rear++;
    queue[rear] = 30;

    display();

    return 0;
}
```

Output:

<img width="565" height="163" alt="image" src="https://github.com/user-attachments/assets/3c4e43b7-2814-46af-9a46-bbf0dcb74735" />



Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

```
#include <stdio.h>

#define SIZE 5

float queue[SIZE];
int front = -1;
int rear = -1;

void enqueue(float value) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow! Cannot insert %.2f\n", value);
        return;
    }
    if (front == -1) {
        front = 0;
    }
    rear++;
    queue[rear] = value;
    printf("Inserted %.2f into the queue.\n", value);
}

int main() {
    enqueue(10.5);
    enqueue(20.3);
    enqueue(30.8);

    return 0;
}
```

Output:

<img width="448" height="207" alt="image" src="https://github.com/user-attachments/assets/85461d60-ad77-4f0a-b120-32413128b10a" />


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

```
#include <stdio.h>

#define SIZE 5

float queue[SIZE] = {10.5, 20.3, 30.8};
int front = 0;
int rear = 2;

void dequeue() {
    // 1. Check if the Queue is Empty
    if (front == -1) {
        printf("Queue is empty.\n");
        return;
    }

    // 2. Delete the Front Element
    float deleted_element = queue[front];
    printf("Deleted element: %.2f\n", deleted_element);
    front++;

    // 3. Check if the Queue Becomes Empty After Deletion
    if (front > rear) {
        front = -1;
        rear = -1;
    }
}

int main() {
    dequeue();
    dequeue();
    dequeue();
    dequeue();

    return 0;
}
```

Output:

<img width="438" height="237" alt="image" src="https://github.com/user-attachments/assets/029bb379-7681-4a03-ba62-37558ed12e61" />



Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
