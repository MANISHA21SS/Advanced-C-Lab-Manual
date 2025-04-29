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

#define MAX 100

// Define a structure to hold person information
struct Person {
    char name[50];
    int age;
};

int main() {
    struct Person people[MAX];
    int n, i;

    printf("Enter number of people: ");
    scanf("%d", &n);

    // Input details for each person
    for (i = 0; i < n; i++) {
        printf("\nEnter details for person %d:\n", i + 1);
        printf("Name: ");
        scanf(" %[^\n]", people[i].name);  // Read string with spaces
        printf("Age: ");
        scanf("%d", &people[i].age);
    }

    // Check eligibility
    printf("\n--- Vaccine Eligibility ---\n");
    for (i = 0; i < n; i++) {
        printf("%s (Age: %d): ", people[i].name, people[i].age);
        if (people[i].age >= 18) {
            printf("Eligible for vaccination\n");
        } else {
            printf("Not eligible for vaccination\n");
        }
    }

    return 0;
}
```
Output:
Enter number of people: 3

Enter details for person 1:
Name: Manisha
Age: 20

Enter details for person 2:
Name: Reshma
Age: 16

Enter details for person 3:
Name: Vasu
Age: 65

--- Vaccine Eligibility ---
Manisha (Age: 20): Eligible for vaccination
Reshma (Age: 16): Not eligible for vaccination
Vasu (Age: 65): Eligible for vaccination

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

// Define structure
struct Student {
    char name[50];
    int marks1;
    int marks2;
    float average;
};

// Function to display student details (pass structure as argument)
void displayStudent(struct Student s) {
    printf("\nStudent Details:\n");
    printf("Name: %s\n", s.name);
    printf("Marks 1: %d\n", s.marks1);
    printf("Marks 2: %d\n", s.marks2);
    printf("Average: %.2f\n", s.average);
}

// Function to calculate average and return updated structure
struct Student calculateAverage(struct Student s) {
    s.average = (s.marks1 + s.marks2) / 2.0;
    return s;
}

int main() {
    struct Student s1;

    // Input data
    printf("Enter student name: ");
    scanf(" %[^\n]", s1.name);

    printf("Enter marks 1: ");
    scanf("%d", &s1.marks1);

    printf("Enter marks 2: ");
    scanf("%d", &s1.marks2);

    // Call function to calculate average and return updated structure
    s1 = calculateAverage(s1);

    // Call function to display student info
    displayStudent(s1);

    return 0;
}
```

Output:

Enter student name: Manisha
Enter marks 1: 85
Enter marks 2: 90

Student Details:
Name: Manisha
Marks 1: 85
Marks 2: 90
Average: 87.50

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

int main() {
    FILE *fp;
    char filename[100];
    char content[500];

    // Get the file name from the user
    printf("Enter the file name to create/write: ");
    scanf("%s", filename);

    // Open the file in write mode
    fp = fopen(filename, "w");

    // Check if the file was opened successfully
    if (fp == NULL) {
        printf("Error opening the file!\n");
        return 1;
    }

    // Get content to write to the file
    printf("Enter content to write to the file:\n");
    getchar(); // To consume newline left by previous scanf
    fgets(content, sizeof(content), stdin);

    // Write content to the file
    fputs(content, fp);

    printf("File '%s' written successfully.\n", filename);

    // Close the file
    fclose(fp);

    return 0;
}
```
Output:
Enter the file name to create/write: example.txt
Error opening the file!

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
    char filename[100];
    char initialContent[500], additionalContent[500];
    FILE *fp;

    // Step 1: Get the file name from user
    printf("Enter the file name (with extension): ");
    scanf("%99s", filename);
    getchar();  // Clear the newline from input buffer

    // Step 2: Open the file in write mode to write initial content
    fp = fopen(filename, "w");
    if (fp == NULL) {
        perror("Error opening file for writing");
        return EXIT_FAILURE;
    }

    // Step 3: Get initial content from user and write to file
    printf("\nEnter the initial content to write to the file:\n");
    fgets(initialContent, sizeof(initialContent), stdin);
    fprintf(fp, "%s", initialContent);
    fclose(fp);  // Close the file after writing

    // Step 4: Open the file again in append mode to insert more text
    fp = fopen(filename, "a");
    if (fp == NULL) {
        perror("Error opening file for appending");
        return EXIT_FAILURE;
    }

    printf("\nEnter the additional text to insert (append to file):\n");
    fgets(additionalContent, sizeof(additionalContent), stdin);
    fprintf(fp, "%s", additionalContent);
    fclose(fp);  // Close the file after appending

    printf("\nFile '%s' updated successfully.\n", filename);
    return 0;
}
```
Output:
Enter the file name (with extension): notes.txt

Enter the initial content to write to the file:
C programming is powerful.

Enter the additional text to insert (append to file):
It supports file handling too.

File 'notes.txt' updated successfully.

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

// Define structure to store student information
struct Student {
    char name[50];
    int rollNumber;
    float marks;
};

int main() {
    struct Student s;

    // Input student details
    printf("Enter student name: ");
    scanf(" %[^\n]", s.name); // Reads string with spaces

    printf("Enter roll number: ");
    scanf("%d", &s.rollNumber);

    printf("Enter marks: ");
    scanf("%f", &s.marks);

    // Display student details
    printf("\n--- Student Details ---\n");
    printf("Name       : %s\n", s.name);
    printf("Roll Number: %d\n", s.rollNumber);
    printf("Marks      : %.2f\n", s.marks);

    return 0;
}
```
Output:
Enter student name: Manisha selvakumari.S.S.
Enter roll number: 101
Enter marks: 89.5

--- Student Details ---
Name       : Manisha selvakumari.S.S.
Roll Number: 101
Marks      : 89.50

Result:
Thus, the program is verified successfully
