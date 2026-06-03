EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

```
#include <stdio.h>

int main() {
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    switch(n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 13:
            printf("seventy three\n");
            break;
        default:
            printf("Greater than 13\n");
            break;
    }

    return 0;
}
```




Output:


<img width="453" height="179" alt="image" src="https://github.com/user-attachments/assets/e7d5c793-7b23-44a2-98f3-1fb709abf806" />







Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
```
#include <stdio.h>
#include <string.h>

int main() {
    char a[50];
    int c;

    printf("Enter the string: ");
    scanf("%s", a);

    for (int h = 0; h <= 3; h++) {
        c = 0;
        for (int i = 0; a[i] != '\0'; i++) {
            if (a[i] == (h + '0')) {
                c++;
            }
        }
        printf("%d ", c);
    }
    printf("\n");

    return 0;
}

```


Output:


<img width="505" height="186" alt="image" src="https://github.com/user-attachments/assets/4febc636-f244-419c-b6f3-b46b879b851d" />







Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int next_permutation(char **s, int n) {
    for (int i = n - 2; i >= 0; i--) {
        if (strcmp(s[i], s[i + 1]) < 0) {
            for (int j = n - 1; j > i; j--) {
                if (strcmp(s[j], s[i]) > 0) {
                    char *tmp = s[i];
                    s[i] = s[j];
                    s[j] = tmp;
                    int reverse_start = i + 1;
                    int reverse_end = n - 1;
                    while (reverse_start < reverse_end) {
                        tmp = s[reverse_start];
                        s[reverse_start] = s[reverse_end];
                        s[reverse_end] = tmp;
                        reverse_start++;
                        reverse_end--;
                    }
                    return 1;
                }
            }
        }
    }
    return 0;
}

int main() {
    // 2. Declare variables s and n
    char **s;
    int n;

    // 4. Input the number of strings
    printf("Enter number of strings: ");
    if (scanf("%d", &n) != 1) return 1;

    // 3. Memory Allocation for array of strings
    s = (char **)malloc(n * sizeof(char *));
    if (s == NULL) return 1;

    // 4. Dynamically allocate memory for each string and take input
    for (int i = 0; i < n; i++) {
        s[i] = (char *)malloc(11 * sizeof(char)); // Allocating space for max 10 chars
        printf("Enter string %d: ", i + 1);
        scanf("%s", s[i]);
    }

    // Sorting strings initially to ensure strict lexicographical starting point
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (strcmp(s[i], s[j]) > 0) {
                char *tmp = s[i];
                s[i] = s[j];
                s[j] = tmp;
            }
        }
    }

    printf("\nPermutations:\n");
    // 5. Permutation Generation Loop
    do {
        for (int i = 0; i < n; i++) {
            printf("%s%c", s[i], i == n - 1 ? '\n' : ' ');
        }
    } while (next_permutation(s, n));

    // 6. Memory Deallocation
    for (int i = 0; i < n; i++) {
        free(s[i]);
    }
    free(s);

    // 7. End
    return 0;
}
```




Output:


<img width="506" height="291" alt="image" src="https://github.com/user-attachments/assets/1e771d12-5f44-40ca-ad51-5aa3187d0c28" />







Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

```
#include <stdio.h>

int main() {
    // 2. Declare integer variables n, i, j, min
    int n, i, j, min;
    int len;

    // 3. Read the value of n from the user
    printf("Enter the value of n: ");
    scanf("%d", &n);

    // 4. Calculate the length of the side of the square matrix
    len = n * 2 - 1;

    // 5. Matrix Generation Loop
    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            // 6. Calculate min as the minimum distance to the borders
            min = i < j ? i : j;
            min = min < len - i ? min : len - i - 1;
            min = min < len - j ? min : len - j - 1;

            // Print the corresponding value based on minimum distance
            printf("%d ", n - min);
        }
        printf("\n");
    }

    // 7. End
    return 0;
}
```




Output:


<img width="549" height="356" alt="image" src="https://github.com/user-attachments/assets/28e503a2-e47d-4b05-9973-3acb867d879c" />







Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

```
#include <stdio.h>

int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main() {
    int result = square();
    printf("The square of the number is: %d\n", result);
    return 0;
}
```
Output:


<img width="471" height="183" alt="image" src="https://github.com/user-attachments/assets/b1b4afb3-63f3-4325-ad16-ba81173a7714" />


Result:
Thus, the program is verified successfully




