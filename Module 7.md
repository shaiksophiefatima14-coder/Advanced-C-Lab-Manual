EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
```
#include <stdio.h>

// 1. Declare structure eligible with age (integer) and n (character array)
struct eligible {
    int age;
    char n[50];
};

int main() {
    struct eligible e;
    printf("Enter name: ");
    scanf("%s", e.n);
    printf("Enter age: ");
    scanf("%d", &e.age);
    if (e.age <= 6) {
        printf("Vaccine Eligibility: No\n");
    } else {
        printf("Vaccine Eligibility: Yes\n");
    }
    printf("Name: %s\n", e.n);
    printf("Age: %d\n", e.age);
    return 0;
}
```


Output:

<img width="487" height="242" alt="image" src="https://github.com/user-attachments/assets/62becfc7-4cf8-44a7-bbac-7b9984405a72" />



Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:
```
#include <stdio.h>

struct numbers {
    int a;
    int b;
    int sum;
};

struct numbers add(struct numbers num);

int main() {
    struct numbers n;

    printf("Enter value for a: ");
    scanf("%d", &n.a);

    printf("Enter value for b: ");
    scanf("%d", &n.b);

    struct numbers result = add(n);
    printf("The sum of %d and %d is: %d\n", result.a, result.b, result.sum);

    return 0;
}

struct numbers add(struct numbers num) {
    struct numbers temp;
    temp.a = num.a;
    temp.b = num.b;
    temp.sum = num.a + num.b;
    
    return temp;
}
```




Output:


<img width="422" height="207" alt="image" src="https://github.com/user-attachments/assets/61cd9fc3-a6a3-4203-9564-10b9e514ab97" />





Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *p;
    char name[100];

    printf("Enter the file name: ");
    scanf("%s", name);

    printf("The file with the name '%s' has been created successfully.\n", name);

    p = fopen(name, "w");

    if (p == NULL) {
        printf("Error opening the file!\n");
        exit(1);
    }

    printf("The file has been opened successfully.\n");

    fclose(p);

    printf("The file has been closed.\n");

    return 0;
}
```




Output:


<img width="578" height="226" alt="image" src="https://github.com/user-attachments/assets/c47b7f73-4734-4b6f-b409-7fd8e1710215" />



Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *p;
    char name[100];
    char text[200];
    int num;

    printf("Enter file name: ");
    scanf("%s", name);
    printf("Enter number of strings: ");
    scanf("%d", &num);

    p = fopen(name, "w");

    if (p == NULL) {
        printf("Error opening the file!\n");
        exit(1);
    }

    printf("The file has been opened successfully.\n");

    for (int i = 0; i < num; i++) {
        printf("Enter string %d: ", i + 1);
        scanf("%s", text);
        fputs(text, p);
        fputs("\n", p);
    }

    fclose(p);

    printf("Data has been added successfully.\n");

    return 0;
}
```




Output:


<img width="521" height="213" alt="image" src="https://github.com/user-attachments/assets/0fa00900-c6d6-4853-8634-4e3511dbff33" />







Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:

```
#include <stdio.h>
#include <stdlib.h>

struct subject {
    char name[50];
    int marks;
};

int main() {
    int n;

    printf("Enter number of subjects: ");
    scanf("%d", &n);

    struct subject *s = (struct subject *)malloc(n * sizeof(struct subject));

    if (s == NULL) {
        printf("Memory allocation failed!\n");
        exit(1);
    }

    for (int i = 0; i < n; i++) {
        printf("Enter name for subject %d: ", i + 1);
        scanf("%s", s[i].name);
        printf("Enter marks for subject %d: ", i + 1);
        scanf("%d", &s[i].marks);
    }

    printf("\nSubject Details:\n");
    for (int i = 0; i < n; i++) {
        printf("Subject %d - Name: %s, Marks: %d\n", i + 1, s[i].name, s[i].marks);
    }

    free(s);

    return 0;
}
```


Output:


<img width="552" height="324" alt="image" src="https://github.com/user-attachments/assets/45a248c2-2093-42f6-b28f-72d31d0bc23f" />






Result:
Thus, the program is verified successfully
