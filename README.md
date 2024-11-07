# C Language Crash Course for 42 Heilbronn Piscine Preparation

Welcome to your C language crash course! This guide is designed to help you prepare for the 42 Heilbronn Piscine by covering essential C programming concepts. We'll start by setting up your development environment and then dive into fundamental topics, each accompanied by examples you can run on your own computer using Visual Studio Code.

## Table of Contents

1. [Setting Up Your Development Environment](#setting-up-your-development-environment)
2. [Basic Syntax and Structure](#basic-syntax-and-structure)
3. [Variables and Data Types](#variables-and-data-types)
4. [Operators](#operators)
5. [Control Flow Statements](#control-flow-statements)
6. [Functions](#functions)
7. [Arrays](#arrays)
8. [Pointers](#pointers)
9. [Strings](#strings)
10. [Structures](#structures)
11. [Dynamic Memory Allocation](#dynamic-memory-allocation)
12. [File Input/Output](#file-inputoutput)
13. [Practice Exercises](#practice-exercises)

## Setting Up Your Development Environment

### Install Visual Studio Code

- Download VS Code: Visit the official website and download the installer for your operating system.
- Install: Run the installer and follow the on-screen instructions.

### Install C/C++ Extension

- Open VS Code.
- Go to Extensions: Click on the Extensions icon on the left sidebar.
- Search: Type C/C++ in the search bar.
- Install: Click on the official Microsoft C/C++ extension and install it.

### Install a C Compiler

#### For Windows

- Download MinGW: Go to MinGW-w64 and download the installer.
- Install: Follow the installation instructions and add MinGW to your system's PATH environment variable.

#### For macOS

- Install Xcode Command Line Tools by running `xcode-select      --install` in Terminal.

#### For Linux

- Install GCC by running `sudo apt-get install build-essential` in Terminal.

### Configure VS Code

- Create a New Folder: This will be your workspace.
- Open Folder in VS Code: Go to ``File`` > `Open Folder`.
- Create a New File: Right-click in the Explorer sidebar and select ``New File``, name it ``main.c``.
- Write a Test Program: You can use the Hello World program from the next section.
- Build and Run: Use the terminal in VS Code to compile your program:

        gcc main.c -o main
        ./main   # Use `.\main` on Windows

## Basic Syntax and Structure

Every C program consists of functions and declarations. The main function is the entry point of any C program.

### Example: Hello World

        #include <stdio.h>

        int main() {
            printf("Hello, World!\n");
            return 0;
        }

#### Explanation

- ``#include <stdio.h>``: Includes the Standard Input Output library.
- ``int main()``: The main function where execution starts.
- ``printf(...)``: Function to print text to the console.
- ``return 0;``: Indicates successful program termination.

## Variables and Data Types

Variables store data for processing. C has several basic data types:

- ``int``: Integer numbers.
- ``float``: Floating-point numbers.
- ``double``: Double-precision floating-point numbers.
- ``char``: Single characters.

### Example: Variable Declaration and Initialization

        #include <stdio.h>

        int main() {
            int age = 25;
            float height = 175.5;
            char initial = 'A';

            printf("Age: %d\n", age);
            printf("Height: %.1f cm\n", height);
            printf("Initial: %c\n", initial);

            return 0;
        }

## Operators

Operators perform operations on variables and values.

- Arithmetic Operators: ``+``, ``-``, ``*``, ``/``, ``%``
- Assignment Operators: ``=``, ``+=``, ``-=``, etc.
- Comparison Operators: ``==``, ``!=``, ``>``, ``<``, ``>=``, ``<=``
- Logical Operators: ``&&``, ``||``, ``!``

### Example: Arithmetic Operations

        #include <stdio.h>

        int main() {
            int a = 10, b = 3;
            int sum = a + b;
            int remainder = a % b;

            printf("Sum: %d\n", sum);
            printf("Remainder: %d\n", remainder);

            return 0;
        }

## Control Flow Statements

Control the flow of execution using conditional statements and loops.

### If-Else Statement

        if (condition) {
            // code if condition is true
        } else {
            // code if condition is false
        }

### Example: If-Else

        #include <stdio.h>

        int main() {
            int number = 7;

            if (number % 2 == 0) {
                printf("%d is even.\n", number);
            } else {
                printf("%d is odd.\n", number);
            }

            return 0;
        }

### Loops

#### For Loop

        for (initialization; condition; increment) {
            // code to be executed
        }

#### While Loop

        while (condition) {
            // code to be executed
        }

### Example: For Loop

        #include <stdio.h>

        int main() {
            for (int i = 1; i <= 5; i++) {
                printf("Iteration %d\n", i);
            }
            return 0;
        }

## Functions

Functions are reusable blocks of code.

### Syntax

        return_type function_name(parameter_list) {
            // function body
        }

### Example: Functions

        #include <stdio.h>

        int add(int x, int y) {
            return x + y;
        }

        int main() {
            int sum = add(5, 3);
            printf("Sum: %d\n", sum);
            return 0;
        }

## Arrays

Arrays store multiple values of the same type.

### Example: Arrays

        #include <stdio.h>

        int main() {
            int numbers[5] = {10, 20, 30, 40, 50};

            for (int i = 0; i < 5; i++) {
                printf("Element %d: %d\n", i, numbers[i]);
            }

            return 0;
        }

## Pointers

Pointers store memory addresses of variables.

### Example: Pointers

        #include <stdio.h>

        int main() {
            int num = 10;
            int *p = &num;

            printf("Value of num: %d\n", num);
            printf("Address of num: %p\n", p);
            printf("Value at address p: %d\n", *p);

            return 0;
        }

#### Pointers Explanation

- ``int *p``: Declares a pointer to an integer.
- ``&num``: Gets the address of num.
- ``*p``: Dereferences the pointer to get the value at the address.

## Strings

Strings are arrays of characters terminated by a null character ``'\0'``.

### Example: Strings

        #include <stdio.h>

        int main() {
            char name[] = "Alice";
            printf("Name: %s\n", name);

            return 0;
        }

## Structures

Structures (`struct`) are user-defined data types that group related variables.

### Example: Structures

        #include <stdio.h>

        struct Person {
            char name[50];
            int age;
        };

        int main() {
            struct Person person1;

            // Assigning values
            strcpy(person1.name, "Bob");
            person1.age = 30;

            printf("Name: %s\n", person1.name);
            printf("Age: %d\n", person1.age);

            return 0;
        }

## Dynamic Memory Allocation

Allocate memory at runtime using malloc, calloc, realloc, and free it using free.

### Example: Dynamic Memory Allocation

        #include <stdio.h>
        #include <stdlib.h>

        int main() {
            int *ptr;
            int n = 5;

            // Allocate memory
            ptr = (int *)malloc(n * sizeof(int));

            // Check if allocation was successful
            if (ptr == NULL) {
                printf("Memory not allocated.\n");
                exit(0);
            }

            // Assign values
            for (int i = 0; i < n; i++) {
                ptr[i] = i + 1;
            }

            // Print values
            for (int i = 0; i < n; i++) {
                printf("%d ", ptr[i]);
            }

            // Free memory
            free(ptr);

            return 0;
        }

## File Input/Output

Read from and write to files using FILE pointers.

### Example: File I/O

        #include <stdio.h>

        int main() {
            FILE *fp;
            fp = fopen("example.txt", "w");

            if (fp == NULL) {
                printf("Error opening file.\n");
                return 1;
            }

            fprintf(fp, "Hello, File!\n");
            fclose(fp);

            return 0;
        }

## Practice Exercises

### Exercise 1: Fibonacci Sequence

Write a program that prints the first 10 numbers of the Fibonacci sequence.

#### Fibonacci Sequence Solution

        #include <stdio.h>

        int main() {
            int n1 = 0, n2 = 1, n3, count = 10;

            printf("Fibonacci Series: %d %d ", n1, n2);

            for (int i = 2; i < count; ++i) {
                n3 = n1 + n2;
                printf("%d ", n3);

                n1 = n2;
                n2 = n3;
            }

            return 0;
        }

### Exercise 2: Factorial of a Number

Write a function to calculate the factorial of a given number.

#### Factorial of a Number Solution

        #include <stdio.h>

        int factorial(int n) {
            if (n == 0 || n == 1)
                return 1;
            else
                return n * factorial(n - 1);
        }

        int main() {
            int num = 5;

            printf("Factorial of %d is %d\n", num, factorial(num));

            return 0;
        }

### Exercise 3: Reverse a String

Write a program to reverse a string without using library functions.

#### Reverse a String Solution

        #include <stdio.h>
        #include <string.h>

        int main() {
            char str[100], temp;
            int i, length;

            printf("Enter a string: ");
            scanf("%s", str);

            length = strlen(str);

            for (i = 0; i < length / 2; i++) {
                // Swap characters
                temp = str[i];
                str[i] = str[length - i - 1];
                str[length - i - 1] = temp;
            }

            printf("Reversed String: %s\n", str);

            return 0;
        }

## Conclusion

By working through this crash course, you've covered the foundational concepts of C programming that will be crucial for the 42 Heilbronn Piscine. Make sure to practice by writing and running these examples on your own. Experiment with modifying the code to deepen your understanding.

## Additional Tips

- Read Error Messages Carefully: They often provide hints on what's wrong.
- Practice Debugging: Use breakpoints and step through your code.
- Understand Memory Management: Especially pointers and dynamic allocation.

Good luck with your preparation, and have a great time at the Piscine!

## Appendix: Setting Up a Git Repository

Version control is essential for managing your code and collaborating with others. Here's a quick guide to setting up a Git repository using GitHub.

### Create a Repository on GitHub

- Sign In: Go to GitHub and log in to your account.
- New Repository:
    1. Click the `+` icon in the top-right corner and select New repository.
    2. Repository Name: Enter a name for your repository (e.g., `c-crash-course`).
    3. Description (optional): Add a brief description.
    4. Public or Private: Choose the visibility of your repository.
    5. Initialize: Do not initialize with a README (since you'll be pushing an existing project).
    6. Click Create repository.

### Clone the Repository to Your Local Machine

- Copy the URL: On your new repository page, click the Code button and copy the HTTPS URL.
- Open Terminal: Navigate to the directory where you want to store your project.
- Clone Repository:

    ``git clone https://github.com/your-username/your-repo-name.git``

    Replace ``your-username`` and ``your-repo-name`` with your GitHub username and repository name.

### Add Files to the Repository

- Navigate to the Repository Folder:

    cd your-repo-name
- Copy Your Project Files: Place all your project files into this directory.
- Stage the Files:

    ``git add .``

### Commit and Push Changes

- Commit Changes:

    ``git commit -m "Initial commit"``
- Push to GitHub:

    ``git push origin main``
