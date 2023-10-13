---
layout: ../../layouts/en/ArticleLayout.astro
titulo: Calculator with Python
autor: Darío O.
fotoDelAutor: /images/autores/dario-o.webp
portada: /images/contenido/calculadora-con-python/portada.webp
portadaAlt: Some lines of code in Python.
descripcion: Face the challenge of creating your own calculator today using the famous Python programming language step by step.
ciencia: coding
fechaMostrar: 1 October, 2022
fechaOrdenar: Oct 1, 2022
duracion: 5
url: /en/calculator-with-python
---

# Creating a Calculator with Python

In this challenge, we will create a calculator using [Python](https://python.org/). The difficulty level of this challenge is **low**.

It is important that if you want to take on the challenge, you read the statements of each challenge and avoid reading the solution to try each challenge on your own.

## Collecting 2 Numbers in the Calculator

### Statement

The first step for our Python calculator will be to **collect two numbers** that will be used in the operation we want to perform.

### Solution

We will declare two variables, named 'a' and 'b'. 'a' will hold the first number, and 'b' will hold the second number. We will use 'input' to collect the user's input. It would look like this:

![Python code snippet](/images/contenido/calculadora-con-python/fragmento-1.webp)

Let's review what each line of code does:

1. Declares a variable called 'a,' which will be equal to the 'int' (integer) of what the user enters in the 'input("Number 1: ")'.
2. Declares a variable called 'b,' which will be equal to the 'int' (integer) of what the user enters in the 'input("Number 2:")'.

// Number 1: 18

// Number 2: 8

In this example, 18 and 8 would be what the user enters.

## Collecting the Operation Type in the Calculator

### Statement

The next step of the challenge is to **collect the type of operation that the user selects**.

### Solution

This step of the challenge is solved in the same way as the previous step. We start by declaring a variable, which we'll call 'op' (for operation), and it will be equal to the user's input.

![Python code snippet](/images/contenido/calculadora-con-python/fragmento-2.webp)

Let's explain what the line of code does:

Declares a variable named 'op,' which is equal to 'input("Operation: ")', i.e., what the user responds to the text 'Operation.'
The console output would look like this:

// Operation: +

Just like in the previous case, what is in bold is what is already written by the program, and what is not is what the user writes.

## Reading the Operation Type

### Statement

At this point, we need to make the program identify what the user has entered to determine what operation to perform.

**HINT**: We will have the operations of addition (+), subtraction (-), multiplication (*), and division (/).

To accomplish this step, we will build upon what we have already written in previous steps, which is:

a = int(input("Number 1: "))
b = int(input("Number 2: "))
op = input("Operation: ")

The goal of this step of the challenge is to have the program output **what operation the user entered in the following way**:

- If the user entered '+,' it should say: 'You have entered addition.'
- If the user entered '-,' it should say: 'You have entered subtraction.'
- If the user entered '*,' it should say: 'You have entered multiplication.'
- If the user entered '/,' it should say: 'You have entered division.'
- If the user did not enter one of these signs, it should indicate that the sign entered is not valid.

### Solution

This step is a bit more complicated than the previous two, as we will add conditional statements (if-else).

The code after this step would look like this:

![Python code snippet](/images/contenido/calculadora-con-python/fragmento-3.webp)

Now, let's explain each line of code:

1. Declares a variable named 'a,' which will be equal to the 'int' (integer) of what the user enters in the 'input("Number 1: ")'.
2. Declares a variable named 'b,' which will be equal to the 'int' (integer) of what the user enters in the 'input("Number 2:")'.
3. Declares a variable named 'op,' which is equal to 'input("Operation: ")', i.e., what the user responds to the text 'Operation.'
4. Compares the variable 'op' with the string '+'. If they are equal, it executes line 5; otherwise, it executes the next line, i.e., line 6.
5. Prints in the console 'You have entered addition.'
6. Compares the variable 'op' with the string '-', and if they are equal, it executes line 7; otherwise, it executes the following line, i.e., line 8.
7. Prints in the console 'You have entered subtraction.'
8. Compares the variable 'op' with the string '*', and if they are equal, it executes line 9; otherwise, it executes the next line, i.e., line 10.
9. Prints in the console 'You have entered multiplication.'
10. Compares the variable 'op' with the string '/', and if they are equal, it executes line 11; otherwise, it executes the following line, i.e., line 12.
11. Prints in the console 'You have entered division.'
12. If none of the above comparisons are true (True), it proceeds to line 13. If any of them were true, this is not taken into account.
13. Prints in the console 'The sign you used is not valid.'

This would be the console output for now:

// Number 1: 18

// Number 2: 8

// Operation: +

You have entered addition.

## Performing the Operations

### Statement

With the first three steps, the user has been able to enter the numbers they want to operate with, and the program has determined the operator the user has entered using conditionals.

The next step is to **perform the operation using the entered numbers and operator**.

**HINT**: The conditionals will help you.

### Solution

If we have the code from the previous steps well established, this step is a piece of cake. All we have to do is perform the operation within each conditional with the operator specified in that conditional, like this:

![Python code snippet](/images/contenido/calculadora-con-python/fragmento-4.webp)

Let's see what each line does:

1. Declares a variable named 'a,' which will be equal to the 'int' (integer) of what the user enters in the 'input("Number 1: ")'.
2. Declares a variable named 'b,' which will be equal to the 'int' (integer) of what the user enters in the 'input("Number 2:")'.
3. Declares a variable named 'op,' which is equal to 'input("Operation: ")', i.e., what the user responds to the text 'Operation.'
4. Compares the variable 'op' with the string '+'. If they are equal, it executes line 5; otherwise, it executes the next line, i.e., line 6.
5. Prints in the console the result of the sum of number 1 (variable a) and number 2 (variable b).
6. Compares the variable 'op' with the string '-', and if they are equal, it executes line 7; otherwise, it executes the following line, i.e., line 8.
7. Prints in the console the result of subtracting number 1 (variable a) from number 2 (variable b).
8. Compares the variable 'op' with the string '*', and if they are equal, it executes line 9; otherwise, it executes the next line, i.e., line 10.
9. Prints in the console the result of multiplying number 1 (variable a) by number 2 (variable b).
10. Compares the variable 'op' with the string '/', and if they are equal, it executes line 11; otherwise, it executes the following line, i.e., line 12.
11. Prints in the console the result of dividing number 1 (variable a) by number 2 (variable b).
12. If none of the above comparisons are true (True), it proceeds to line 13. If any of them were true, this is not taken into account.
13. Prints in the console 'The sign you used is not valid.'

This would be the console output:

// Number 1: 18

// Number 2: 8

// Operation: +

// 26

And this would be another possible console output:

// Number 1: 2

// Number 2: 50

// Operation: p

// The sign you entered is not valid.

## Conclusions about the Python Calculator

With this last step of the challenge, we would have completed the challenge, as we now have a calculator created in Python that calculates the result of one of these four operations (+, -, *, /) with two numbers.

Due to the low difficulty of this challenge, I haven't extended the program further, but you could make it repeat the program as many times as you want, allow the entry of more than two numbers, add powers...