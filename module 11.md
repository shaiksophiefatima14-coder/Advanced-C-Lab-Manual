

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```
#include <stdio.h>

// 2. Use a series of if and else if statements to compare the values and return the maximum among them.
int max_of_four(int a, int b, int c, int d) {
    if (a >= b && a >= c && a >= d) {
        return a;
    } else if (b >= a && b >= c && b >= d) {
        return b;
    } else if (c >= a && c >= b && c >= d) {
        return c;
    } else {
        return d;
    }
}

int main() {
    // 3. Declare variables n1, n2, n3, n4, and greater to store user input and the result.
    int n1, n2, n3, n4, greater;

    // 4. Use scanf to take four integers as input.
    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    // 5. Call the max_of_four function with the input integers and store the result in the greater variable
    greater = max_of_four(n1, n2, n3, n4);

    printf("The greatest number is: %d\n", greater);

    return 0;
}
```

Output:
<img width="539" height="230" alt="image" src="https://github.com/user-attachments/assets/1825bce1-fcb2-4091-a123-ee505acbf398" />


Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
```
#include <stdio.h>

// 1. Define a function calculate_the_max that takes two integers n and k as parameters.
void calculate_the_max(int n, int k) {
    // 2. Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
    int a = 0, o = 0, x = 0;

    // 3. Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and_res = i & j;
            int or_res = i | j;
            int xor_res = i ^ j;

            // 4. Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
            // The maximum values must be strictly less than k.
            if (and_res > a && and_res < k) {
                a = and_res;
            }
            if (or_res > o && or_res < k) {
                o = or_res;
            }
            if (xor_res > x && xor_res < k) {
                x = xor_res;
            }
        }
    }

    // Print the maximum values found
    printf("%d\n", a);
    printf("%d\n", o);
    printf("%d\n", x);
}

int main() {
    // 5. Declare variables n and k to store user input.
    int n, k;

    // 6. Use scanf to take two integers as input.
    printf("Enter values for n and k: ");
    scanf("%d %d", &n, &k);

    // 7. Call the calculate_the_max function with input values.
    calculate_the_max(n, k);

    return 0;
}
```

Output:
<img width="495" height="261" alt="image" src="https://github.com/user-attachments/assets/64c07ebd-36a5-4bca-96e5-e9280930bc28" />


Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    // 1. Declare variables noshel and noque
    int noshel, noque;

    // 2. Use scanf to take two integers as input for shelves and queries
    if (scanf("%d %d", &noshel, &noque) != 2) {
        return 1;
    }

    // 3. Declare a 2D array (shelarr) and a 1D array (nobookarr) dynamically
    // nobookarr stores the count of books on each shelf, initialized to 0
    int* nobookarr = (int*)calloc(noshel, sizeof(int));
    
    // shelarr points to arrays of integers representing page numbers of books on shelves
    int** shelarr = (int**)malloc(noshel * sizeof(int*));
    for (int i = 0; i < noshel; i++) {
        shelarr[i] = NULL; 
    }

    // 4. Declare variables k and c (and query_type) to keep track of operations
    int query_type;
    int k, c; // k can represent shelf index, c can represent pages/book details

    // 5. Use a for loop to iterate over the queries
    for (int i = 0; i < noque; i++) {
        scanf("%d", &query_type);
        
        if (query_type == 1) {
            /* Type 1: Insert a book with 'c' pages at shelf 'k'
               Input format: 1 k c
            */
            scanf("%d %d", &k, &c);
            
            // Increment the book count for shelf k
            nobookarr[k]++;
            
            // Reallocate memory for this shelf to accommodate the new book
            shelarr[k] = (int*)realloc(shelarr[k], nobookarr[k] * sizeof(int));
            
            // Insert the book pages at the last index of that shelf
            shelarr[k][nobookarr[k] - 1] = c;
            
        } else if (query_type == 2) {
            /* Type 2: Print the number of pages of the 'c'-th book on shelf 'k'
               Input format: 2 k c
            */
            scanf("%d %d", &k, &c);
            printf("%d\n", shelarr[k][c]);
            
        } else if (query_type == 3) {
            /* Type 3: Print the total number of books on shelf 'k'
               Input format: 3 k
            */
            scanf("%d", &k);
            printf("%d\n", nobookarr[k]);
        }
    }

    // Free the dynamically allocated memory before exit
    for (int i = 0; i < noshel; i++) {
        if (shelarr[i] != NULL) {
            free(shelarr[i]);
        }
    }
    free(shelarr);
    free(nobookarr);

    return 0;
}
```

Output:
<img width="494" height="102" alt="image" src="https://github.com/user-attachments/assets/b5668adf-a93b-435d-804d-2913ec3b3c48" />



Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
```
#include <stdio.h>

int main() {
    // 1. Declare a variable n to store the number of integers.
    int n;

    // 2. Use scanf to take an integer n as input.
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    // 3. Declare an array a of size n to store the integers.
    int a[n];

    // 4. Declare a variable sum and initialize it to zero.
    int sum = 0;

    // 5. Use a for loop to iterate n times:
    printf("Enter %d integers: ", n);
    for (int i = 0; i < n; i++) {
        // 6. Use scanf to input each integer and add it to the sum.
        scanf("%d", &a[i]);
        sum += a[i];
    }

    // 7. Print the final sum using printf.
    printf("Sum of the integers in the array: %d\n", sum);

    return 0;
}
```

Output:
<img width="453" height="224" alt="image" src="https://github.com/user-attachments/assets/6332e7d4-9d7e-4033-9cda-3fbc55041e8b" />


 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
```
#include <stdio.h>

int main() {
    char sentence[1000];
    int word_count = 0;
    int i = 0;
    int in_word = 0; // Flags whether we are currently inside a word

    // 1. Input the sentence: Take a sentence from the user.
    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    // 2. Initialize a counter variable and 3. Process each character of the sentence
    while (sentence[i] != '\0') {
        // 4. Handle spaces, newlines, and punctuation tabs as separators
        if (sentence[i] == ' ' || sentence[i] == '\n' || sentence[i] == '\t') {
            in_word = 0; 
        } 
        // If the character is not a space/separator
        else if (in_word == 0) {
            in_word = 1;
            word_count++; // Increment the word count at the first non-space character of a word
        }
        i++;
    }

    // 5. Display the result
    printf("Total number of words: %d\n", word_count);

    return 0;
}
```

Output:
<img width="447" height="183" alt="image" src="https://github.com/user-attachments/assets/1454b2b7-a660-4bc3-b1b4-0b6172e09375" />




Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
