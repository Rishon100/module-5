# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>
int main() {
    float length, width, area;
    float *ptr_length, *ptr_width, *ptr_area;

    ptr_length = &length;
    ptr_width = &width;
    ptr_area = &area;

    printf("Enter the length of the rectangle: ");
    scanf("%f", ptr_length);

    printf("Enter the width of the rectangle: ");
    scanf("%f", ptr_width);

    *ptr_area = (*ptr_length) * (*ptr_width);

    printf("The area of the rectangle is: %.2f\n", *ptr_area);

    return 0;
}
```
## OUTPUT
		       	
![Screenshot 2025-04-27 184839](https://github.com/user-attachments/assets/15875b2f-43df-4078-8788-451febe6c209)


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int main() {
    char *str;

    str = (char *)malloc(8 * sizeof(char));

    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    strcpy(str, "WELCOME");

    printf("%s\n", str);

    free(str);

    return 0;
}
```
## OUTPUT

![Screenshot 2025-04-27 184943](https://github.com/user-attachments/assets/36aff093-5ba1-43bf-85a7-f832bbc747f8)


## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>
struct Student {
    char name[50];
    int roll_no;
    float marks;
};

int main() {
    struct Student student;

    printf("Enter student name: ");
    fgets(student.name, sizeof(student.name), stdin);

    printf("Enter roll number: ");
    scanf("%d", &student.roll_no);

    printf("Enter marks: ");
    scanf("%f", &student.marks);

    printf("\nStudent Information:\n");
    printf("Name: %s", student.name);
    printf("Roll Number: %d\n", student.roll_no);
    printf("Marks: %.2f\n", student.marks);

    return 0;
}


```

## OUTPUT

![Screenshot 2025-04-27 185111](https://github.com/user-attachments/assets/c972fa3a-7291-43d3-95d6-49455354e5a0)

## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>
struct Employee {
    char name[50];
    int basic_salary;
    float gross_salary;
};

int main() {
    struct Employee employees[3];

    for (int i = 0; i < 3; i++) {
        printf("Enter name of Employee %d: ", i + 1);
        scanf("%s", employees[i].name);

        printf("Enter basic salary of Employee %d: ", i + 1);
        scanf("%d", &employees[i].basic_salary);

        employees[i].gross_salary = employees[i].basic_salary + (employees[i].basic_salary * 0.2) + (employees[i].basic_salary * 0.1);  // 20% HRA and 10% DA
    }

    for (int i = 0; i < 3; i++) {
        printf("\nEmployee %d:\n", i + 1);
        printf("Name: %s\n", employees[i].name);
        printf("Gross Salary: %.2f\n", employees[i].gross_salary);
    }

    return 0;
}

```

 ## OUTPUT

 ![Screenshot 2025-04-27 185340](https://github.com/user-attachments/assets/e82e0239-791c-4c57-acbf-6a97b37d6de0)


## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>
struct Student {
    char name[50];
    int marks[5];
    int total;
    float average;
};

int main() {
    struct Student student;

    printf("Enter student name: ");
    fgets(student.name, sizeof(student.name), stdin);

    student.total = 0;

    printf("Enter marks for 5 subjects:\n");
    for (int i = 0; i < 5; i++) {
        printf("Subject %d: ", i + 1);
        scanf("%d", &student.marks[i]);
        student.total += student.marks[i];
    }

    student.average = student.total / 5.0;

    printf("\nStudent Information:\n");
    printf("Name: %s", student.name);
    printf("Total Marks: %d\n", student.total);
    printf("Average Marks: %.2f\n", student.average);

    return 0;
}
```

## OUTPUT

 ![Screenshot 2025-04-27 185456](https://github.com/user-attachments/assets/5f03c949-5ba6-473d-805c-d8e6ecf967bc)


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


