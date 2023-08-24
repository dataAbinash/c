# Notes for Covered Topics

~ By Abinash, 2023-08-24

### Operator
An operator is a symbol that tells the compiler to perform specific operation. Operator requires some operands to perform the operation. For example, ```+``` is an operator to perform addition. ```2 + 3``` is an expression where ```2``` and ```3``` are operands and ```+``` is an operator.

### Operand
An operand is a quantity on which an operation is to be done. For example, in ```2 + 3```, ```2``` and ```3``` are operands.

### Expression
An expression is a combination of operators and operands that specifies a computation. Expressions can be evaluated to determine their value.

Example: ```2 + 3 * 4``` is an expression. The operators are ```+``` and ```*```, and the operands are ```2```, ```3```, and ```4```. The value of the expression is ```14```.

#### Truthy and Falsy Expressions(or Values)
In C, any non-zero value is considered as true and zero is considered as false.
The Falsy values in C language are ```0```, ```0.0```, ```NULL```, and ```'\0'```.

> `0`, `NULL`, `'\0'` are all equivalent. All are evaluated to `0`. Stored `0` in memory.

All other values are considered as truthy values.


### Types of Operators and Operator Precedence
https://www.geeksforgeeks.org/operators-in-c/


### Statement
A statement is a syntactic unit of a programming language that expresses some action to be carried out. Simply, a statement is complete part of code commanding a task.

Example: ```if (x > 0) { x = 0; }``` is a statement.


#### Ternary Operator
The ternary operator is the only operator that takes three operands.

```<condition> ? <expression1> : <expression2>```

Example : 
```result = (a > b) ? a : b;```





## Pointers
A pointer is a variable whose value is the address of another variable.

```c
int x = 10;
int *p; // Pointer Initialization, p is a pointer to an integer
p = &x; // Pointer Assignment, p contains the address of x
printf("%d", *p); // Dereferencing, using * operator to access
// the value of the variable pointed to by the pointer
```

### Pointer to Pointer
A pointer that points to another pointer is called pointer to pointer. 

```c
int x = 10;
int *p = &x; // p points to x
int **q = &p; // q points to p
```

### Types of Pointers

#### Wild Pointer
A pointer that has not been initialized to anything (not even `NULL`) is known as wild pointer.
```c
int *p; // p is a wild pointer
```
`p` contains some garbage address, accessing the value of p may crash the program. It is always a good practice to initialize a pointer to `NULL`.


#### Null Pointer
A pointer that is assigned `NULL`(or `0`) is called a null pointer.
```c
int *p = NULL; // p is a null pointer
int *q = 0; // q is a null pointer
```

#### Void Pointer
A void pointer is a pointer that has no associated data type with it. A void pointer can hold address of any type and can be typcasted to any type.

```c
int x = 10;
float y = 20.5;
void *p = &x;
void *q = &y;
```

#### Dangling Pointer
A pointer pointing to a memory location that has been deleted (or freed) is called dangling pointer.

```c
int *p = (int *)malloc(sizeof(int));
free(p);
// p is now a dangling pointer
// It is always a good practice to make a dangling pointer NULL.
p = NULL; // Like this
```


## Arrays & Pointers
An array is a collection of similar data items stored at contiguous memory locations. 

### Important Points to Remember
Consider the following example.

```c
int arr[5] = {1, 2, 3, 4, 5};
```

- ```arr``` is a pointer to the first element of the array.

- `arr` is a constant pointer, it cannot be reassigned to point to another array. We can change the value of the elements of the array, but we cannot change the value of `arr`.

- ```arr + 1``` points to the second element of the array, ```arr + 2``` points to the third element of the array, and so on.


#### Pointer to Array
A pointer that points to an array is called pointer to array.

```c
int arr[5] = {1, 2, 3, 4, 5};
int *p = arr;
// p now points to the first element of the array
```

#### Array of Pointers
An array of pointers is an array in which each element is a pointer to another variable.
```c
int x = 10, y = 20, z = 30;
int *arr[3] = {&x, &y, &z};
// arr is an array of pointers
// arr[0] points to x
// arr[1] points to y
// arr[2] points to z
```

### Pointer Arithmetic

Pointer arithmetic is the arithmetic operation on pointers. There are four arithmetic operators that can be used on pointers: ```++```, ```--```, ```+```, and ```-```.

- `Pointer + Integer` : Used to access the next memory location of the base address of the pointer, usually used in arrays.

- `Pointer - Integer` : Used to access the previous memory location of the base address of the pointer, usually used in arrays.

- `Integer + Pointer` : Similar to `Pointer + Integer`.

- `Integer - Pointer` : Not allowed, Makes no sense.

- `Pointer - Pointer` : Used to find the difference between two pointers. The difference is the number of elements between the two pointers.

- `Pointer + Pointer` : Not allowed, Makes no sense.

- `Pointer++` : Used to access the next memory location of the base address of the pointer, usually used in arrays.

- `Pointer--` : Used to access the previous memory location of the base address of the pointer, usually used in arrays.

- `++Pointer` : Almost same as `Pointer++`.

- `--Pointer` : Almost same as `Pointer--`.



### The Subscript Operator `[]`
Access array elements using the subscript operator ```[]```.

### *Important*
Consider `arr` is an array and `i` is an integer.

`arr[i]` and `*(arr + i)` are equivalent. Internally, the compiler converts `arr[i]` to `*(arr + i)`.



## Strings
In C, a string is an array of characters terminated by a null character `\0`.

```c
char str[6] = {'H', 'e', 'l', 'l', 'o', '\0'};
```

Better way to initialize a string is to use double quotes `""`.

```c
char str[6] = "Hello";
```


# Structures
A structure is a user-defined data type in C. A structure creates a data type that can be used to group items of possibly different types into a single type.

```c
struct Complex {
    int real;
    int imaginary;
};
```

### Accessing Structure Members
Structure members can be accessed using the dot operator `.`.

```c
struct Complex c;
c.real = 10;
c.imaginary = 20;
```

### Structure Initialization
```c
struct Complex c = {10, 20};
```




Happy Coding! 😉
