# C Programming Notes

*This content was created by using [Necati Ergin's](https://github.com/necatiergin) C lecture notes.*

**Creation Date :** 21.03.2022 - **Author :** Hasan Guzelmansur

---

## Contents

1. [History of the C Language](#history-of-the-c-language)
2. [General Concepts and Terms](#general-concepts-and-terms)
    - [Some features of C language](#some-features-of-c-language)
    - [Keywords - reserved words](#keywords---reserved-words)
    - [Names](#names)
    - [Punctuators](#punctuators)
    - [Constant](#constant)
    - [String](#string)
    - [Expression](#expression)
    - [Statement](#statement)
3. [Number systems](#number-systems)
    - [Bits](#bits)
    - [Binary](#binary)
    - [MSD and LSD](#msd-and-lsd)
    - [One's and Two's Complements](#ones-and-twos-complements)
    - [Negative Number Representation](#negative-number-representation)
    - [Keeping Real Numbers in Memory](#keeping-real-numbers-in-memory)
4. [Creating a C Program](#creating-a-c-program)
    - [Utilities](#utilities)
5. [Data Types](#data-types)
    - [Integer Types](#integer-types)
    - [Floating Types](#floating-types)
    - [Virtual Types](#virtual-types)
6. [Declaration and Definition](#declaration-and-definition)
7. [Constant Types](#constant-types)
    - [Integer Constants](#integer-constants)
    - [Character Constants](#character-constants)
    - [Escape Sequences](#escape-sequences)
    - [Real Number Constants](#real-number-constants)
8. [Functions](#functions)
    - [Function Definition](#functions-definition)
    - [Defining Function Parameter Variables](#defining-function-parameter-variables)
    - [Standard C Functions](#standard-c-functions)
9. [Operators](#operators)
    - [Operand](#operand)
    - [C Language Operator Precedence Table](#c-language-operator-precedence-table)
10. [Scope and Storage Duration](#scope-and-storage-duration)
    - [Scope](#scope)
    - [Storage Duration / Lifespan](#storage-duration--lifespan)

---

## History of the C Language

The C language was born as a by-product of the UNIX operating system. Ken Thompson developed the B language and programmed part of the UNIX operating system with B. In 1971, when it became clear that the B language was not suitable for the development of PDP-11 computers and the UNIX operating system, Dennis Ritchie began to create a further version of the B language. He first named this language NB (New B). But, this new language broke away from the B language and started to show different characteristics. That's why he later changed the name of this new language to C. In 1973, most of the UNIX operating system was rewritten in C language. C language became known and used by the masses thanks to the book "C Programming Language" written by Dennis Ritchie and Brain Kernighan in 1978.

The version of the C language used until the standardization process is called Traditional C. The C language was standardized by the American National Standards Institute (ANSI) in 1989. Its official name is American National Standard X3.159-1989, known as ANSI C for short. Then an international standard was established and accepted by ANSI. The commonly accepted standard is called Standard C or C89 for short. C95 and C99 standards are also available. Which version to use depends on the decision of the compiler to be developed and the portability level of the code.

## General Concepts and Terms

### Some features of C language

- C language is an intermediate programming language close to both machine perception and human perception.
- C language can be preferred directly to machine language for many applications from an efficiency point of view. Because it is much easier and less efficient than writing the same program in machine language.
- The main programming area of the C language is systems programming.
- C is an algorithmic language.
- It has high portability and readability features.
- It is very flexible and efficient.
- It is integrated with the UNIX operating system.

### Keywords - reserved words

- Keywords cannot be used as variable names.
- There are 32 keywords in the standard ANSI C (C89) language.
- With the C99 standards, 5 more keywords have been added to the language.

### Names

- Software entities such as variables, functions, macros, and constants are given names, provided that the rules set by the programming language are followed.

### Punctuators

- Punctuators are semantic tokens. Punctuators can act as operators or separators. Some are related to the preprocessor program.
- There are 45 different operators in the C language.

### Constant

- Constants are dynamically changeable information-free tokens that are processed directly.

### String

- Expressions in double quotes are called strings.

### Object

- Areas that occupy memory and whose contents can be accessed for reading or writing are called objects.
- For an expression to be an object, it must specify a location in memory.
- The values of objects are the information they hold in them.
- The type of the object gives the compiler some information about that object. Like a place to keep in memory.
- There are two different types. Default types and user defined types.
- Scope is the program area in which a name can be recognized by the language's compiler or interpreter.
- The lifetime is the portion of time the object remains in existence at program runtime.
- Linkage is the ability of objects to be recognized in other modules that make up the program.

### Expression

- Combinations of variables, operators, and constants are called expressions.

### Statement

- The sentences of the C language are called statements. In C, statements are terminated with a semicolon.
- Some statements are written only to inform the compiler. (declaration statement)
- Some statements allow the compiler to generate code that does an operation. (executable statement)

## Number systems

### Bits

- In binary, each digit is called 1 bit. The word bit is derived from the words binary digit.
  - *example : 0010 -> 4 Bits*
- An 8-bit size is called a byte.

Names and bits of some minor units

| Bit | Name |
|--|--|
| 8 Bits | 1 byte |
| 16 Bits | 1 word |
| 32 Bits | 1 double word |
| 64 Bits | 1 quadro word |

### Binary

- If only zero and positive integers are shown, the binary number system used in this format is called the **unsigned binary** number system.
- The use of the binary number system to show negative integers is called the **signed binary** number system.

### MSD and LSD

- The leftmost bit of a number written in the unsigned binary number system adds the highest numerical value. This bit is called the Most Significant Digit.
- The rightmost bit of a number written in the unsigned binary number system adds the lowest numeric value. This bit is called the Least Significant Digit.

### One's and Two's Complements

- One's complement is the number obtained by inverting all bits of the number.
- 1 more than the one's complement of a number is the two's complement of the number. Or, Starting from the far right of the number, the same number is written until the 1st bit is seen for the first time, including the first 1 bit. For the remaining digits, the reverse of the digit is written.

### Negative Number Representation

- The binary number system in which negative integers are also expressed is called a signed binary system.
- In binary, a negative number is the two's complement of a positive number of the same value.
- In the signed binary number system, a number whose all bits are 1 is -1. *( -1 = 1111 1111 )*

### Keeping Real Numbers in Memory

- In most systems, the actual numbers are kept according to the IEEE (Institute of Electrical and Electronics Engineers) 754 standard.
- According to this standard, two different formats are determined for real numbers:
  1. *single precision format*
  2. *double precision format*

## Creating a C Program

- This is the compilation cycle of **file.c** file :
  - *file.c -> **Preprocessor** -> file.i -> **Compiler** -> file.s -> **Assembler** -> file.o -> **linker** -> file.exe*
- The preprocessor program makes some textual changes on the source file. The output of the preprocessor program is given to the compiler program.
- The extension of purpose files created on Unix/Linux systems is ".o". In DOS and Windows systems, purpose files have the ".obj" extension.

### Utilities

- **Text Helpers** : With such programs, search, cut and paste operations can be done within the source file. It can be ensured that the names are completed automatically without writing all the long names.
- **Logical Error Catchers** : There are special programs that try to catch programming errors that escape the logical warnings of compiler programs. The most used of these programs is a software called LINT.
- **Code Formatters** : They are programs that organize the general layout of the source code (styler).
- **Profiler Programs** : These programs are used to measure and evaluate the efficiency of a running program.

## Data Types

- C language has 12 default data types. 9 of these types are designed to hold integer data, and the remaining 3 are designed to hold real-number data. These types are integer types and floating types.

### Integer Types

- There are a total of 9 different integer data types in C. Signed integer types can hold positive and negative integer values, while unsigned integer types cannot hold negative integer values.
- **Character Types :** Char, signed char, unsigned char are character types. These types are 1 byte long in each system. The signed char type is the signed character type. When 1 byte memory area is signed, integer values between -128 / 127 can be stored in this area. The unsigned char type is the unsigned character type. When the 1 byte memory area is used unsigned, values between 0 / 255 can be stored in this area. The char type is the type of character that is left to the compiler's choice, to be used as signed or unsigned.
- **Bool Types :** It is the "logical data" type that has been added to the language with the C99 standards. It holds the values 0 and 1.
- **Short Int Types :** There are two types of short integers, signed and unsigned. How many bytes of memory a short integer object will occupy may vary from system to system. On most systems this type is 2 bytes long.
- **Int Types :** How many bytes an int type object will occupy in memory may vary from system to system. Usually, int data takes up 2 bytes on 16-bit systems and 4 bytes on 32-bit systems.
- **Long Int Types :** There are four types of long integers, two signed and two unsigned. signed long int is type of signed long integer. unsigned long int is an unsigned long integer type. On most systems these types are 4 bytes long.

### Floating Types

- Three different data types are defined to hold real number values. These are the float, double and long double types, respectively.
- All real number types are signed. Keeping real numbers in memory may contain properties that may vary from system to system. However, most systems comply with the IEEE 754 standard.
- In almost all systems, an object of the float data type takes up 4 bytes of memory.
- An object of type double is encoded in 8 bytes of memory in most systems.
- In the IEEE 754 standard, the 4-byte real number format is called "single precision", and the 8 byte real number format is called "double precision".

### Virtual Types

- These types have been added to the language with the C99 standards. There are three different types of virtual numbers.
- In **float _Complex** type, the real and imaginary parts of the complex number are kept in float type.
- In type **double _Complex**, the real and imaginary parts of the complex number are kept as double.
- In type **long double _Complex**, the real and imaginary parts of the complex number are kept in type long double.

## Declaration and Definition

- **Declaration :** They are statements made to give information to the compiler that it will use at compile time.
- **Definition :** Declarative statements that allow the compiler to allocate memory.
- **Variable declaration format :** *<typed_words> <variable_name> <;>*
- Only 63 characters can be used in identifying. Lowercase and uppercase letters in the English alphabet, numbers, and underscore.
- Variable names have no length limit in C, but the compiler must consider the first 31 characters of the variable name.
- The words signed and unsigned can be used alone without type keywords. In this case, it is assumed that a variable of type int has been declared.
- If there is more than one type keyword in the declaration statement, the order of their spelling is not important. But in terms of readability, it has become a tradition to use the keyword indicating the sign first and then the keyword indicating the type.
- When a variable is defined, it can be initialized.

**Points to consider when determining variable names:**

1. The names chosen should be meaningful.
2. Names should not be chosen as the name of the group to which variables with different properties belong.
3. There should be linguistic integrity in naming.
4. In C, variable names are traditionally chosen lowercase.

## Constant Types

**Constant :** Non-object data entered directly by the programmer as a numeric quantity.

### Integer Constants

- Integer constants values are integers. *Example : signed int, unsigned long etc.*
- An integer constant can take the suffixes u, U, l, or L, no matter what number system it is written in.
- The suffix u or U determines that the integer constant is of unsigned integer type. The suffixes l or L determine that the integer constant is of type long.

### Character Constants

- Character constants are typically assigned to objects of type char.
- If the image of a character is written in a "single quote", it is treated as a direct character constant by the compiler.
- In C, character constants are treated as int and processed.

### Escape Sequences

- Escape Sequences are backslash character constants
- Other spellings of character constants use single quotes with a backslash followed by other characters.

#### Default Escape Sequences

|  | Definition | ASCII NO |
|--|--|--|
| '\a' | alert | 7 |
| '\b' | back space | 8 |
| '\t' | tab | 9 |
| '\n' | new line | 10 |
| '\v' | vertical tab | 11 |
| '\f' | form feed | 12 |
| '\r' | carriage return | 13 |

### Real Number Constants

- Constants that contain periods, suffixed with 'f' or 'F', are of float type.
- Constants without the suffix 'f' ,'F', l, L, containing periods, and constants that exceed the float type limit or precision are treated as double-type constants.
- Constants of the long double type are obtained by adding 'l' or 'L' to the end of dotted or exponential numbers.
- Real number constants can be written in exponential form (scientific notation). For this, 'e' or 'E' suffix is added to the end of the word.

## Functions

- A function is a piece of program that can be run independently.
- Function inputs are called "actual parameters" or "arguments", and their outputs are called "return values".
- In C language, another function cannot be defined within a function definition.
- Functions in C can only produce a single return value.
- Functions can only be called from within defined functions. Functions cannot be called from outside of blocks.
- The linking process between the calling function and the called function is done by the linker at the linking stage.
- Even if an undefined function is called within a defined function, an error will not occur during the compilation phase. The error occurs during the binding phase.
- It is not mandatory to use the values produced by the functions that produce the return value.
- The return value obtained by calling a function can be used as an argument in a call to another function.
- A function that calls itself is called a recursive function.

**Benefits of using functions :**

- The source code of the program becomes smaller.
- The readability of the source file increases.
- Debugging in the program is carried out more easily.
- Functions written can be used in other projects as well.

**The main purpose of the function :**

- A function accomplishes certain purposes by performing certain operations during its operation.
- A function can send a value that it will produce at the end of its execution to the calling function.

**The purpose of using the return values of the functions :**

- Functions can be defined to obtain a single value, to calculate a single value.
- Functions, on the other hand, can respond to a question asked of them when they are called.
- Functions can both accomplish a certain purpose and in addition produce a return value that completes their purpose.
- The purpose of non-return functions is sometimes just to perform a job, the success of the job is guaranteed.
- Non-return functions can pass a value to the outside. However, passing the value is done using another tool, not "return".

### Function Definition 

- Function definition syntax in C : `[Type_of_return_value] <function_name> ([parameters]) { /***/ }`

**void**

- Functions that do not produce a return value are called void functions.
- Functions with no return value defined are assumed by the compiler to have a return value of type int.

**return**

- The return values of functions in C language are created with return statement.
- In functions that do not produce a return value, the return keyword can also be used on its own without a statement.

**main**

- The execution of C programs starts with the function called main.
- A source file that does not have a main function can be compiled. However, when the linker sees that there is no main function at the linking stage, it cannot perform the linking operation.
- The main function can be defined as a void function. However, although it is not a syntax error, it is not considered correct to define the main function as a void function.
- Most compilers generate a logical warning message if the main function does not produce a return value.


### Defining Function Parameter Variables

- There are two different style, old and new.
- Old Style : Only the names of the function's parameter variables are written within the function parameter braces.

```
//Syntax for old style

int func (a, b, c)
int a;
double b;
long c;
{ 
  /***/	
}
```

- New Style : The declaration of function parameter variables is done only once inside the function brackets.

```
//Syntax for new style

int func(int x, int y) 
{ 
  /***/	
}
```

### Standard C Functions

- Standard C functions are functions that have been made mandatory in every compiler after the standardization of the C language.
- Within the header files, that is, the files with the .h extension, there are standard C function declarations.
- Libraries consist of compiled files. In the DOS operating system, the extension of the library files is .lib, in the UNIX operating system it is .a (archive). Dynamic libraries with extension .dll are also available under WINDOWS.

**printf**

- With the printf function, a text can be printed to the screen, as well as the value of an expression.
- The printf function interprets the % characters in the string with a certain number of characters next to them as conversion specifiers.
  - *Example usage :*  `printf("x = %d\npi = %lf\n", x, pi);`

| Format character | Meaning |
|------------------|---------|
|%d|It interprets the int type and writes it in the decimal number system.|
|%ld|It interprets the long type and writes it in the decimal number system.|
|%x|It interprets the unsigned int type and writes it in the hexadecimal number system. Use Lowercase.|
|%X|It interprets the unsigned int type and writes it in the hexadecimal number system. Use Uppercase.|
|%lx|It interprets the unsigned long type and writes it in the hexadecimal number system.|
|%u|It interprets the unsigned int type and writes it in the decimal number system.|
|%o|It interprets the unsigned int type and writes it in the octal number system.|
|%f|Writes the values of the expressions of float and double types in decimal number system.|
|%lf|Writes the values of the expressions of double and long double types in decimal number system.|
|%e|Writes real numbers in exponential form.|
|%c|It interprets a char or int type expression as a sequence number of a character and prints the image of the corresponding character to the screen.|
|%s|It prints the text at the given address to the screen.|

- %% is used as the format character to print the percent character itself to the screen.
  - *Example :* `printf("%%25\n");`

**scanf**

- The scanf function is a standard C function that allows input of any information from the keyboard.
  - *Example usage :* `scanf("%d%d", &x, &y);`
- Other arguments to the scanf function are used with the "&" address operator. “&” is a pointer operator.

**C functions that take characters from the keyboard**

- There are three different C functions that receive data from the keyboard. One is standard C function, the others not.

*getchar*

- The return value of the function is an int value that represents the sequence number of the character in the character set table used.
- The getchar function needs the enter key to get characters from the keyboard.
  - *Parametric structure :* `int getchar(void);`
- getchar is defined as a macro within the stdio.h header file in most compilers.

*getch*

- Differences with getchar :
  - The pressed key does not appear on the screen
  - Most systems don't need the enter key.
- The conio.h header file should be added to the source code for getch function.

*getche*

- It is abbreviated from the words get char echo.
- Don't need the enter key.
- The received character appears on the screen.

**C functions that print characters to the screen**

*putchar*

- putchar is a standard C function.
- Writes the character with the parameter to the cursor position on the screen.
- It is located in the stdio.h header file.

```
//Example usage

 	#include <stdio.h> 

	int main() 
	{ 
		char ch; 
		ch = getchar(); 
		putchar (ch); 
		return 0; 
	}
```

*putch*

- It is not a standard C function.
- When '\n' is used, it moves to the next line without changing the column where the cursor is located. Other than that, there is no difference with putchar.

**Comment lines**

- Comment lines start with /* and end with */.
- With the C99 standard, an explanation can be made with double backslash( // ). 


## Operators

- Operators are tokens that enable predefined operations on objects or literals.
- Operators enable the microprocessor to produce a value by performing an operation.
- Each operator defined in programming languages corresponds to at least one machine instruction.

### Operand

- Objects or literals that operators manipulate are called operands.
- Operators in C can be divided into three groups according to the number of terms they take:
    - Unary operators
    - Binary operators
    - Ternary operator or conditional operator
- Operators can also be grouped according to their position:
    - Postfix operators
    - Prefix operators
    - Infix operators
- When an operator changes the value of an object with a term, it is called a side effect of the operator.
- Classification of Operators
    - Arithmetic operators
    - Relational operators
    - Logical operators
    - Pointer operators
    - Bitwise operators
    - Assignment operators
    - Special purpose operators

### C Language Operator Precedence Table

|Level|Operator|Definition|Associativity|
|-----|--------|----------|-------------|
|1|()|precedence and function call|left associative|
|1|[]|subscript|left associative|
|1|.|structure access with object|left associative|
|1|->|structure access with pointer|left associative|
|2|+|unary sign|right associative|
|2|-|unary sign|right associative|
|2|++|increment|right associative|
|2|--|decrement|right associative|
|2|~|bitwise not|right associative|
|2|!|logical not|right associative|
|2|*|indirection|right associative|
|2|&|address of|right associative|
|2|sizeof|size|right associative|
|2|(type)|type cast operator|right associative|
|3|*|multiplication|left associative|
|3|/|division|left associative|
|3|%|modulus|left associative|
|4|+|addition|left associative|
|4|-|subtraction|left associative|
|5|<<|bitwise shift left|left associative|
|5|>>|bitwise shift right|left associative|
|6|<|less than|left associative|
|6|>|greater than|left associative|
|6|<=|less than or equal|left associative|
|6|>=|greater than or equal|left associative|
|7|==|equal|left associative|
|7|!=|not equal to|left associative|
|8|&|bitwise and|left associative|
|9|^|bitwise exor|left associative|
|10|\||bitwise or|left associative|
|11|&&|logical and|left associative|
|12|\|\||logical or|left associative|
|13|?:|conditional|right associative|
|14|=|assignment|right associative|
|14|+=|assignment with addition|right associative|
|14|-=|assignment with subtraction|right associative|
|14|*=|assignment with multiplication|right associative|
|14|/=|assignment with division|right associative|
|14|%=|assignment with modulus|right associative|
|14|<<=|assignment with bitwise left shift|right associative|
|14|>>=|assignment with bitwise right shift|right associative|
|14|&=|assignment with bitwise right and|right associative|
|14|\|=|assignment with bitwise or|right associative|
|14|^=|assignment with bitwise exor|right associative|
|15|,|comma|left associative|

## Scope and Storage Duration

- Three very important properties of objects in terms of C language are "scope", "storage duration" and "linkage".

### Scope

- The scope is the program range in which a name can be recognized.
- Recognition areas are divided into 4 groups by C standards:
    - *File scope* : After a name is declared, it is known within the entire source file, that is, within all defined functions.
    - *Block scope* : A name is known only within one block after it has been declared.
    - *Function scope* : A name is known only within a function after it has been declared.
    - *Function Prototype Scope* : A definition that includes names used in function declarations, within the function parameter separator.
- **Local variables :** Variables defined inside blocks or within the parameter separators of functions are "local variables".
    - A local variable cannot be defined after an executable statement.
    - Local variables can be declared inside the main block of a function, or they can be declared inside an internal block (nested block). According to C99 standards, a local variable can be defined anywhere in a block.
- **Global variables  :** Variables defined outside of blocks are called "global variables".
    - Global variables are known everywhere from the point they are defined to the end of the source file.
- **Name lookup :** When the compiler encounters the use of a name, it tries to find out which software entity that name belongs to. This process is called "name lookup".
    - *Name lookup* is done from the narrow area to the wide awareness area.

### Storage Duration / Lifespan

- Storage duration / lifespan is the term used to describe how long objects occupy memory during program runtime.
- Objects used in programs can be divided into three groups in terms of their lifetime:
    - Static duration or Static storage class
        - Static objects take their place in memory when the program starts running.
        - These entities persist until the program finishes running. Static objects are usually written in object code (.obj). There are three distinct groups of statically-lived entities in the C language :
            - Global variables
            - Strings
            - Static local variables
    - Automatic storage class
        - Auto-lived objects are objects that are created at a certain time of the program's execution, discharged from memory after a certain period of activity, that is, they complete their lifetime.
    - Dynamic storage class
        - Objects allocated by dynamic memory functions have dynamic lifetimes.
- Local variables should be preferred to global variables, and global variables should only be used in imperative situations.
- Global variables can cause the following problems:
    1. Global variables with a static lifetime remain in memory until the end of the program. Thus, they cause more inefficient use of memory.
    2. Because global variables are shared by all functions, source files where global variables are used frequently are more difficult to read.
    3. Searching for errors and making changes is more difficult in a source file where global variables are frequently used.
    4. Functions that use global variables cannot be easily reused in other projects.
    5. Global variables belonging to external links pollute the global namespace.