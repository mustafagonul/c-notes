# C Programming Notes

*This content was created by using [Necati Ergin's](https://github.com/necatiergin) C Programming Language Course notes.*

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
11. [Calling Conventions](#calling-conventions)
12. [Control Statement](#control-statement)
    - [Executable Statement Groups](#executable-statement-groups)
    - [if](#if)
13. [Function Declarations](#function-declarations)
14. [Type Conversions](#type-conversions)
15. [Conditional Operator (Ternary Operator)](#conditional-operator-ternary-operator)
16. [Loop Statement](#loop-statement)
    - [while](#while)
    - [do while](#do-while)
    - [for](#for)
    - [break](#break)
    - [continue](#continue)
17. [Preprocessor Commands](#preprocessor-commands)
18. [switch Statement](#switch-statement)
19. [Random Number Generation](#random-number-generation)
20. [Arrays](#arrays)
21. [Pointer](#pointer)
22. [void Type Pointer](#void-type-pointer)
23. [Strings](#strings)
24. [Pointer Arrays](#pointer-arrays)
25. []()
---

## History of the C Language

The C language was born as a by-product of the UNIX operating system. Ken Thompson developed the B language and programmed part of the UNIX operating system with B. In 1971, when it became clear that the B language was not suitable for the development of PDP-11 computers and the UNIX operating system, Dennis Ritchie began to create a further version of the B language. He first named this language NB (New B). But, this new language broke away from the B language and started to show different characteristics. That's why he later changed the name of this new language to C. In 1973, most of the UNIX operating system was rewritten in C language. C language became known and used by the masses thanks to the book "C Programming Language" written by Dennis Ritchie and Brain Kernighan in 1978.

The version of the C language used until the standardization process is called Traditional C. The C language was standardized by the American National Standards Institute (ANSI) in 1989. Its official name is American National Standard X3.159-1989, known as ANSI C for short. Then an international standard was established and accepted by ANSI. The commonly accepted standard is called Standard C or C89 for short. C95 and C99 standards are also available. Which version to use depends on the decision of the compiler to be developed and the portability level of the code.

**[Go to Top](#contents)**

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

### L value (left value)

- Expressions that represent objects are called "left value" (lvalue).
- Variables are always left values. Constants cannot be left values.
- When GNU C language extensions are enabled, compound expressions, conditional expressions, and casts are allowed as lvalues, if their operands are lvalues.
- A conditional expression can be a valid lvalue if its type is not void and both of its branches for true and false are valid lvalues. Casts are valid lvalues if the operand is an lvalue. The primary restriction is that you cannot take the address of an lvalue cast. (Reference : [IBM XL C/C++ for AIX](https://www.ibm.com/docs/en/xl-c-and-cpp-aix/13.1.2?topic=operators-lvalues-rvalues))

### R value (right value)

- Expressions that do not show objects are called "right value" (R value).
- “Right value” is often used to emphasize that an expression does not indicate an object.
- A function call is always an rvalue.

### Function Designator (C99 Standard)

- C defines a function designator as an expression that has function type. A function designator is distinct from an object type or an lvalue. It can be the name of a function or the result of dereferencing a function pointer. The C language also differentiates between its treatment of a function pointer and an object pointer.

### Increment

- **a++** Postincrement, first the variable a is used, then the value a is incremented by one. 
- **++a** Preincrement, first the variable a is incremented by one, then the new value a is used.
- **a--** Postdecrement, first the variable a is used, then the value a is decremented by one.
- **--a** Predecrement, first the variable a is decremented by one, then the new value a is used.

- There is a restriction on the use of the **++** or **--** operator, such that the term of the operator is an expression that denotes an object. If the expression with the term does not correspond to an object, that is, if it is not a left-hand side value, the written expression is invalid.

### Expression

- Combinations of variables, operators, and constants are called expressions.

### Statement

- The sentences of the C language are called statements. In C, statements are terminated with a semicolon.
- Some statements are written only to inform the compiler. (declaration statement)
- Some statements allow the compiler to generate code that does an operation. (executable statement)

**[Go to Top](#contents)**

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

**[Go to Top](#contents)**

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

**[Go to Top](#contents)**

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

**[Go to Top](#contents)**

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

**[Go to Top](#contents)**

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

**[Go to Top](#contents)**

### Real Number Constants

- Constants that contain periods, suffixed with 'f' or 'F', are of float type.
- Constants without the suffix 'f' ,'F', l, L, containing periods, and constants that exceed the float type limit or precision are treated as double-type constants.
- Constants of the long double type are obtained by adding 'l' or 'L' to the end of dotted or exponential numbers.
- Real number constants can be written in exponential form (scientific notation). For this, 'e' or 'E' suffix is added to the end of the word.

**[Go to Top](#contents)**

## Functions

- A function is a piece of program that can be run independently.
- Function inputs are called "actual parameters" or "arguments", and their outputs are called "return values".
- In C language, another function cannot be defined within a function definition.
- Functions in C can only produce a single return value.
- Functions can only be called from within defined functions. Functions cannot be called from outside of blocks.
- The linking process between the calling function and the called function is done by the linker at the linking stage.
- Even if an undefined function is called within a defined function, an error will not occur during the compilation phase. The error occurs during the linker phase.
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

**[Go to Top](#contents)**

### Function Definition 

- Function definition syntax in C : `[Type_of_return_value] <function_name> ([parameters]) { /***/ }`

**void**

- Functions that do not produce a return value are called void functions.
- Functions with no return value defined are assumed by the compiler to have a return value of type int.

**return**

- The return values of functions in C language are created with return statement.
- In functions that do not produce a return value, the return keyword can also be used on its own without a statement.
- Failure to produce a return value with the return statement will not cause a compile-time error. In this case, the function's execution ends when the end of the function's main block is reached. The function passes a garbage value to where it is called.
- In void functions, the return keyword can also be used alone, without an accompanying statement. In this case, the return statement terminates the function it is in without generating a return value.

**main**

- The execution of C programs starts with the function called main.
- A source file that does not have a main function can be compiled. However, when the linker sees that there is no main function at the linking stage, it cannot perform the linking operation.
- The main function can be defined as a void function. However, although it is not a syntax error, it is not considered correct to define the main function as a void function.
- Most compilers generate a logical warning message if the main function does not produce a return value.

**[Go to Top](#contents)**

### Defining Function Parameter Variables

- A function's formal parameters, or parameter variables, are variables that hold inputs from functions that call them. 
- Information such as the number of parameters of a function and the types of those parameters are reported to the compiler when functions are defined. The values of the argument expressions sent with the function call are copied to the corresponding parameter variables of the function.
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

**[Go to Top](#contents)**

### Copying Arguments to Parameter Variables

```
void func(int a) 
{
   /***/ 
 }

int main() 
{ 
 
  int x = 10; 
  /***/ 
  func(x); 
 
  return 0; 
 }
```
- The function call causes the program's flow to jump to where the code for the **func** function is located, at program runtime.
- **A memory space is reserved for the parameter variable a in the *func* function.** The value of the expression, that is, the value of the variable **x**, is passed to the parameter variable **a**.

**[Go to Top](#contents)**

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

**[Go to Top](#contents)**

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
- Operators within the expression produce values in order of precedence. The generated values are passed as terms to the less precedence operators in the expression.
- When an operator changes the value of an object with a term, it is called a **side effect** of the operator.
- Classification of Operators
    - Arithmetic operators
    - Relational operators
    - Logical operators
    - Pointer operators
    - Bitwise operators
    - Assignment operators
    - Special purpose operators

**[Go to Top](#contents)**

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

**[Go to Top](#contents)**

### Some Important Terms Used in the C Standards

- **Behavior :** The way a compiler interprets and makes sense of a particular piece of code is called a compiler.
- **Undefined behavior :** It can lead to interpretation differences that may vary from compiler to compiler but are not explicitly stated in the standards. 
- **Unspecified behavior :** Situations where the source code can be interpreted differently by the compiler, but the options are limited in this regard.
- **Implementation dependent behavior :** Some features of the C language are left to the choices of those who write compilers in the standards in order to provide flexibility. For example, what the length of the int type is, whether the default char type is signed or unsigned, whether nested interpretations are accepted or not is entirely up to the compiler writers.
- **Diagnostic message :** In the standards, the compiler's notification of the problem to the programmer is called a "diagnostic message".

## Scope and Storage Duration

- Three very important properties of objects in terms of C language are "scope", "storage duration" and "linkage".

**[Go to Top](#contents)**

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

**[Go to Top](#contents)**

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

**[Go to Top](#contents)**

## Calling Conventions

- Calling conventions describe the interface of called code:
    - The order in which atomic (scalar) parameters, or individual parts of a complex parameter,are allocated
    - How parameters are passed (pushed on the stack, placed in registers, or a mix of both)
    - Which registers the called function must preserve for the caller (also known as: callee-savedregisters or non-volatile registers)
    - How the task of preparing the stack for, and restoring after, a function call is divided between the caller and the callee

- Calling conventions, **type representations**, and **name mangling** are all part of what is known as an **application binary interface** (ABI).

**NOT : There are subtle differences in how various compilers implement these conventions, so it is often difficult to interface code which is compiled by different compilers. On the other hand, conventions which are used as an API standard (such as stdcall) are very uniformly implemented.**

**[Go to Top](#contents)**

### cdecl (C declaration) 

- The cdecl is a calling convention that originates from Microsoft's compiler for the C programming language and is used by many C compilers for the x86 architecture.
- In cdecl, subroutine arguments are passed on the stack. Integer values and memory addresses are returned in the EAX register, floating point values in the ST0 x87 register.
- Registers EAX, ECX, and EDX are caller-saved, and the rest are callee-saved.
    - **Caller-saved registers** (aka volatile registers, or call-clobbered) are used to hold temporary quantities that need not be preserved across calls.
    - **Callee-saved registers** (aka non-volatile registers, or call-preserved) are used to hold long-lived values that should be preserved across calls.
- The x87 floating point registers ST0 to ST7 must be empty (popped or freed) when calling a new function, and ST1 to ST7 must be empty on exiting a function.
- ST0 must also be empty when not used for returning a value.
- In the context of the C programming language, function arguments are pushed on the stack in the right-to-left order, i.e. the last argument is pushed first.
- The cdecl calling convention is usually the default calling convention for x86 C compilers, although many compilers provide options to automatically change the calling conventions used.

**[Go to Top](#contents)**

**Reference for Calling Conventions**

- [x86 calling conventions](https://en.wikipedia.org/wiki/X86_calling_conventions)
- [Stack organization; C-calling-convention functions](https://staffwww.fullcoll.edu/aclifton/cs241/lecture-stack-c-functions.html)
- [Processor register](https://en.wikipedia.org/wiki/Processor_register)
- [Calling Conventions](https://docs.microsoft.com/en-us/cpp/cpp/calling-conventions?redirectedfrom=MSDN&view=msvc-170)
- [x64 calling convention](https://docs.microsoft.com/en-us/cpp/build/x64-calling-convention?view=msvc-170)
- [Name mangling](https://en.wikipedia.org/wiki/Name_mangling)
- [Application binary interface](https://en.wikipedia.org/wiki/Application_binary_interface)
- [What are callee and caller saved registers?](https://stackoverflow.com/questions/9268586/what-are-callee-and-caller-saved-registers)
- [x86](https://en.wikipedia.org/wiki/X86)

## Control Statement

### Executable Statement Groups

- **Simple Statement :** Statements formed by terminating a statement with a terminating atom are called simple statements.
- **Null Statement :** A stand-alone terminating atom `;` in C language creates a statement of its own.
- **Compound Statement :** The structure formed by one or more statements enclosed in a block is called a "compound statement".
- **Control Statement :** Control statements are statements that can change the flow of the program. These statements follow some predetermined syntax rules.

### if

- It is the statement that controls the flow of the program.
- Syntax :

```
if (conditional expression)
  statements;
```

- The statement that makes up the correct part of the if statement can be a simple statement, a null statement, a compound statement, or another control statement.
- **else** : The if control statement can also contain the else keyword. Such an if statement is called an if statement with a false part.
- Syntax with **else**:3

```
if (conditional expression)
  statements1;
else
  statements2;
```

- The conditional expression of the if statement is logically interpreted as **true** or **false**. In the above expression, if the condition is true, statement1 is made, if it is interpreted as false, statement2 is made.

**[Go to Top](#contents)**

**Using the assignment operator in a conditional expression**

- The assignment operator is often used in the condition expression of an if statement. Thus, the value produced by the assignment operator is used.
- Example :

```
if ((x = getval()) > 5) 
 	func1(x); 
 else 
 	func2(x);
```

- Codes can also be written differently. But pattern code makes it easier to write more complex statements.
- Example :

```
if ((y = getval()) > 5 && isPrime(y)) 
 	func1(y);	
```

**Nested *if* Statements**

- Example :

```
if (expression1) 
	if (expression2) 
		statements1;
else 
	statements2;	
```

- In the above example, although the else part looks like it should belong to the first if statement due to the syntax, the else part belongs to the second if statement. The else keyword, in such cases, belongs to the near if statement (dangling else).
- If you want the **else** keyword to belong to the first **if statement**, the correct part of the first **if statement** should be blocked.
- Example :

```
if (expression1) { 
	if (expression2) 
		statements1; 
} else 
	statements2;	
```

**[Go to Top](#contents)**

**else if**

- It is used to condition multiple possibilities.
- If the conditional expression of any if statement evaluates to true, the program flow will never come to another if statement. This structure is called a cascaded if / else if ladder.
- Example :

```
if (expression1) 
	statements1; 
else if (expression2) 
	statements2; 
else if (expression3) 
	statements3; 
else if (expression4) 
	statements4; 
else 
	statements5;	
```

- The false part of the if statement at the very end of its ladder has special significance. In the example above, statement5 is in the else part of the last if statement of the ladder. If the condition statement of any if statement inside the ladder is not true, the false part of the last if statement is made.
- Conditions with a higher probability or frequency should be shifted higher on the else if ladder, both for readability and efficiency.

**Some Common Mistakes**

- Example 1 :

```
if (10 < x < 20) 
		func();	
```

- Because the lesser operator has a left-to-right precedence direction, the left-further lesser operator produces a value first. You know that the value the operator produces is either 1 or 0. The value 1 or 0 produced becomes the term for the right-hand less than operator. Since the value 20 is greater than 1 or 0, the expression is always true.

- Example 2 :

```
if (func) 
 		m = 12;	
```

- Another dangerous mistake is to forget the function call operator if the expression in the if brace is a function call statement.
- This does not generate a syntax error. In this case, the correct part of the if statement is always executed. In C, a function name is treated as an address equivalent to the memory location of that function's code. Since this address information is always a non-zero value, the condition expression always evaluates to true.

**Test Functions**

- The common agreement for the return values of test functions is as follows: If the function answers the question asked correctly or positively, it returns any value other than 0. If the result of the question asked or the test performed is negative or false, the function returns 0.
- **isupper :** It is a standard function that tests whether the character to which the code number is sent is uppercase.

**Standard Character Test Functions**

- Character test functions are functions that provide information about characters.
- In most compilers these functions are also defined as macros within the **ctype.h** header file.
- The return values are unreliable if used for Turkish characters.

|Function|return Value|
|--------|------------|
|**isalpha**|True if it's an alphabetic character, false otherwise.|
|**isupper**|True if uppercase, false otherwise.|
|**islower**|True if lowercase, false otherwise.|
|**isdigit**|True if it is a numeric character, false otherwise.|
|**isxdigit**|True if it is a character representing one of the hexadecimal digit symbols, ie 0123456789ABCDEFabcdef, false otherwise.|
|**isalnum**|True if it is an alphabetic or numeric character, false otherwise.|
|**isspace**|True if one of the space characters (space, carriage return, new line, horizontal tab, vertical tab, form feed) is false, otherwise false.|
|**ispunct**|True if it is one of the punctuation characters, that is, characters other than control characters, alphanumeric characters, and space characters, otherwise false.|
|**isprint**|True if it is a character that can be seen on the screen, that is, printable (including the space character), otherwise false.|
|**isgraph**|True if it is a visible character on the screen (not including the space character), false otherwise.|
|**iscntrl**|True if it is a control character or a delete character (the first 32 characters of the ASCII set or the number 127 character), otherwise false.|

- Converting from lowercase to uppercase or uppercase to lowercase is a common operation. The standard **toupper** and **tolower** functions are used for this purpose.

**[Go to Top](#contents)**

## Function Declarations

- **What is a function declaration?** : A function declaration is a statement that tells the compiler about a function. The compiler generates the code for the function call using the information it receives from the function declaration.
- Before a function can be called, its return value must be known to the compiler.
- The type of return value of a function determines from which CPU registers the return value is received. Obtaining this information at compile time is essential for the program to work correctly.
- When the C compiler encounters a function call expression, it assumes that the return value of that function is of type int if it has not yet learned about the return value type of the function.

**General format of function declarations**

- Syntax :

```
	[return value] <function name> ([type1], [type2].....);
```

- If the return value of the function is not specified in the function declarations, the compiler assumes that the declaration is made for an int return value.
- With function declarations, only the compiler is informed. Therefore, as a result of the notification, the compiler does not allocate a place in memory for the runtime of the program.
- If the function does not have a parameter variable, the keyword **void** must be written inside the parameter separator in the declaration.

**Writing names for parameter variables in declarations**

- In function declarations, parameter variables can also be named after their types.
- Names used within the function declaration bracket are known only within that bracket. These names are not known when left out of this bracket. This reputation zone rule is called **function prototype scope**.
- Those who read only the declarations of the functions without seeing the definitions of the functions will have an idea of the parameter variable names used in the declarations and what information they expect from the function calls of these variables.

**Location of function declarations**

- In general, function declarations are made at the top of the source file or inside one of the programmer-defined header files.

**Declarations of standard C functions**

- The programmer does not write the declaration of a standard C function in applications, but adds the header file containing this declaration to his/her own source code with the **#include** preprocessor command.

**Failure to declare function**

- In C, the compiler generates the target file by accepting the return value of a function that it does not see declared as int.
- There is no problem if the return value of the function is not used in the source code, or if the return value of the called function is indeed of type int. However, if the return value of the function is used and the return value is not of type int, there is a runtime error.

**[Go to Top](#contents)**

## Type Conversions

- For processors to perform an arithmetic operation, generally the terms that are processed must have the same length, that is, the number of bits must be the same and they must be expressed in the same format in memory.
- The C language allows different types to be in the same expression. That is, an integer type variable, a float type literal, or a char variable can be included in a single expression.
- In this case, the C compiler does the appropriate type conversions so that the computer hardware can evaluate the expression before processing them.
- Such conversions are performed automatically without the need for the programmer to write any code. Such conversions are called **implicit type conversions**.
- The C language also allows the programmer to treat any expression as another type using an operator. Such type conversions done by the programmer are called **explicit type conversions/type casts**.

**In which cases type conversion is done?**

1. If the terms of an arithmetic or logical expression are not of the same type
2. If the type of expression to the right of the assignment operator and the expression to the left of the assignment operator are not the same when the assignment operator is used
3. If the type of an argument passed to a function in a function call is not the same as the type of the function's corresponding parameter variable
4. If the type of a return statement is not the same as the type of the corresponding function's return value

**Automatic type conversions before processing**

- Pre-operation automatic type conversions are applied when the types of terms differ in expressions with binomial operators. As a result of automatic type conversion, the case of two different types is eliminated, ensuring that the types of both terms are the same.
- Generally, the smaller type term is expressed in the type of the larger type term to avoid data loss.
- Situations that may occur:
    1. If one of the terms belongs to one of the real number types:
        - If one of the terms is of type **long double** and the other is of a different type, the other term is expressed as type **long double**. The operation is done in type **long double**.
        - If one of the terms is of type **double** and the other is of a different type, the other term is expressed as a **double**. The operation is done in **double** type.
        - If one of the terms is of **float** type and the other is of a different type, the other term is expressed as **float**. The operation is done in **float** type.
    2. If none of the terms are real number types:
        - If any of the terms in the expression are of type signed char, unsigned char, signed short int or unsigned short int, these types are converted to int before the following conditions are applied. This conversion is called **integral promotion**.
        - The following rules are then applied:
            - If one of the terms is of type **unsigned long** and the other is of a different type, the other term is expressed in type **unsigned long** and the operation is done in type **unsigned long**.
            - If one of the terms is of **signed long** type and the other is of a different type, the other term is expressed as **signed long** and the transaction is made in the type of **signed long**.
            - If one of the terms is of type **unsigned int** and the other is of a different type, the other term is expressed as type **unsigned int** and the operation is done of type **unsigned int**.
        - Exceptions:
            - If one of the terms is **signed long** int and the other is **unsigned int** and the lengths of these types are the same in the system used (as in UNIX and Win 32 systems), both terms are converted to **unsigned long** int type.
            - If one of the terms is of type **signed int** and the other is of type **unsigned short** int and the lengths of these types are the same in the system used (as in the DOS operating system), both terms are converted to type **unsigned int**.

**[Go to Top](#contents)**

**Assignment Type Conversions**

- Before assignment, the expression to the right of the assignment operator is expressed in the type of the object to the left of the assignment operator.
- There is no loss of information in converting small species into large ones.

```
/*...*/

double leftx; 
int righty = 5; 

leftx = righty;

/*...*/
```

- When a negative integer is converted from small to large, the high-significant bits of the number are fed with bit 1 to preserve negativity.
- In assignment type conversions made by the compiler, information loss may occur if the large type is converted to the small type before the assignment.
- If the right term of the assignment operator is of a **real number** type (float, double, long double) and the left term is of an **integer** type, the decimal part of the real number value is lost first. If the integer part obtained from the real number cannot be expressed from the integer type to which the assignment is made, this is **undefined behavior**.

**Integral Promotion**

- Integral promotion means that the types char, signed char, unsigned char, short, unsigned short contained in an expression are automatically converted to int before the expression is evaluated by the compiler.
- The general rule is: If the value of the term to be converted can be expressed as int, it is converted to int, otherwise unsigned int.

**Type conversion in function calls**

- If the called function is defined before the calling function, the compiler determines the type of parameter variables from the function's definition.
- If the function is declared, the compiler knows ahead of time about the type of parameter variables.
- Arguments of type char or short are increased to integers (integral promotion). Arguments of type float are converted to type double. No type conversion is performed for arguments of other types.

**Type conversion operator**

- With the typecast operator, an expression can be expressed from another type before it is processed. The type conversion operator is a monomial operator in the prefix position. The operator consists of a parenthesis and a type information enclosed in the parenthesis.
- Syntax:

```
/*...*/

(double)x

/*...*/
```

**Int to Char casting**

- You can use **itoa()** function to convert the integer to a string.
- You can use strcat() function to append characters in a string at the end of another string.
- Note that since characters are smaller in size than integer, this casting may cause a loss of data. It's better to declare the character variable as unsigned in this case (though you may still lose data).

**[Go to Top](#contents)**

## Conditional Operator (Ternary Operator)

- The conditional operator is the only ternary operator of the C language.
- For readability, it may be preferable to enclose the first term of the conditional operator in parentheses.
- Syntax:

```
expression1 ? expression2 : expression3 
```

**Conditions using the Conditional Operator**

- There are typical situations where it is recommended to use the conditional operator. In these cases, the general idea is to use the value produced by the conditional operator in the same expression and pass this value somewhere.
    1. The value produced by the condition operator can be assigned to an object.
        - Example:
          ```
          p = (x == 5) ? 10 : 20;
          ```
    2. A function can return the value produced by the condition operator.
        - Example:
          ```
          int max(int a, int b) 
			    { 
				    return a > b ? a : b; 
			    }
          ```
    3. A function can be called with the value produced by the condition operator.
        - Example:
          ```
          func(a == b ? x : y); /* At the end of this operation, func(x) or func(y) is called.*/
          ```
    4. The value produced by the condition operator can also be used as part of the control expression of a control statement.
        - Example:
          ```
          if (y == (x > 5 ? 10 : 20)) func();
          ```
- If the value produced by the condition operator is not to be directly used, the if control statement should be preferred instead of the condition operator.
- The precedence direction of the condition operator is right to left. If there is more than one condition operator in an expression, the rightmost is evaluated first.

**[Go to Top](#contents)**

## Loop Statement

- Control statements that make a program part run recursively are called "loop statements".

### while

- Syntax:

```
while (expression) 
	statement;
```

- The expression in parentheses following the while keyword is called a **"control expression"**. The first statement following the while separator is called the **"loop body"**.
- In a **while** loop statement, it is not guaranteed that the statement in the loop body is executed at least once.
- Since the control statement is handled first, if the control statement is false on the first entry into the loop, the statement in the loop body will not be executed at all.

### break

- A **break** statement is used to exit a loop.
- When a **break** statement is encountered during the execution of a loop statement, the loop is exited and the program continues with the first statement outside the loop body.
- The **break** statement can only be used in the body of a **loop statement** or **switch statement**.

### continue

- When the flow of the program comes to the **continue statement** within a loop statement, it is passed to the next round of the loop, as if the loop had finished.
- The continue statement can only be used in the body of a **loop statement**. It is not valid to be used anywhere other than a loop.

### do while

- Syntax:

```
do
  statement;
while (expression);
```

- It is not guaranteed that the statement in the body of the loop is executed at least once in a while loop. However, since the control is done at the end in the do while loop, the statement in the body is made at least once.

**[Go to Top](#contents)**

### for

- Syntax:

```
for (expression1; expression2; expression3) 
		statement;
```

- The first statement after closing the for brace creates the loop body.
- The expression that forms the second part of the **for** brace is called the **control expression**.
- As for the flow of the program, the for statement is evaluated in the first part of the for brace. The expression in the first part is usually used to initialize the loop variable.
- The statement in the third part of the for brace is handled after the statement or statements in the loop body have been executed, before the control statement is retested.

**Using the comma operator inside the for brace**

- It is common to use the comma operator in the first and third part of for loops.
- Example:

```
for (i = 1, k = 3; i * k < 12500; i += 2, k += 3)
```

- The initialization of the loop variable can be taken out of the for loop from the first part of the for brace.
- Increment or decrement of the loop variable can be performed inside the loop body instead of inside the for brace.
- Any code that can be written with **while loops** can also be written with a **for loop**.
- An infinite loop with for can be achieved with an expressionless for loop. Example:

```
for (;;) 
{ 
	if (i == 100) 
		break; 
	printf("%d ", i++); 
}

```

- When the continue statement is encountered within the body of the for loop, the flow of the program comes to the third statement of the for brace and this statement is handled.

**Nested Loops**

- Another loop statement can form the body of a loop. Loops created in this way are called **nested loops**.
- Using the **break statement** in the body of an inner loop only exits the inner loop.
- If you want to exit all of the nested loops, not just the inner one, then the **goto** control statement should be used.

**Exit states from loops**

1. With the control expression being false
2. with the **return** statement
3. with the **break** statement
4. with the **goto** statement
5. With a function call that terminates the program

**[Go to Top](#contents)**

## Preprocessor Commands

- A preprocessor is a pre-program that makes some edits and changes to the source file.
- The input of the preprocessor is the source file itself. The output of the preprocessor program is the input of the compilation module.
- All lines starting with `#` in C programming language are directives given to the preprocessor program.
- The preprocessor program doesn't do any work of generating intent code; makes some textual edits in the source code.

**`#include` Preprocessor Command**

- Syntax:

    `#include <file_name>`

- With the `#include` preprocessor command, the name of the file to be added to the source file can be specified in two different ways:
    1. in angular bracket

      `#include <stdio.h>`

    2. in double quote

      `#include "stdio.h"`

- In most systems, when the file name is written in double quotes, the relevant file is first searched in the current directory by the preprocessor program. If the searched file cannot be found here, this time the search is done in the default directory.
- Header files created by the programmers themselves are usually included in the source code in double quotes because they are not in the system's directory.
- The file name to be added to the source code with the #include preprocessor command may also contain the path.
- The codes that will provide general service (server codes) are generally written in two separate files. The function definitions are in the file with the global variable definitions extension .c. This file is called the implementation file. Notifications concerning client codes are kept in another file. This file is called header file. A header file is the interface of a module. The module establishes its relationship with the outside through its interface.

**`#define` Preprocessor Command**

- The function of the #define preprocessor command can be compared to the "find - replace" feature in text editor programs. This command is used to replace a text in the source code with another text.
- Often a name is replaced by a numeric value using the #define preprocessor command. A name that is replaced with a numeric value is called a "symbolic constant" (manifest constant).
- Names defined with the #define preprocessor command are also called "simple macros".
- New names can be given to C's native data types with the #define preprocessor command.
- The #define command can be used anywhere in the source file. However, it takes effect in the region from where it is defined to the end of the source file.

**[Go to Top](#contents)**

**Simple macros for standard C operators**

```
#define and       && 
#define and_eq    &= 
#define bitand    & 
#define bitor     | 
#define compl     ~ 
#define not       ! 
#define not_eq    != 
#define or        || 
#define or_eq     |= 
#define xor       ^ 
#define xor_eq    ^=
```

## **switch** Statement

- The switch statement is used to do different things for different values of an integer expression.

```
switch (expression) {

 case expression1 : 
 case expression2 : 
 case expression3 : 
 ....... 
 case expression_n: 
 default: 

}
```

- switch, case, and default are keywords of the C language.
- If the appropriate case statement is found, only the statement related to this statement is requested to be executed, the break statement is used. Using the break statement exits the switch statement as well as loops. In applications, a break statement is often used for each case statement in the switch statement.
- Performing the same operations for more than one case statement can be achieved as follows:

```
case 1: 
case 2: 
case 3: 
	statement1; 
	statement2; 
	break;
case 4:
```

- Character literals can also be used as case statements.

**[Go to Top](#contents)**

### goto Statement

- The flow of the program in C language can be redirected to another point in the source code without being bound by a condition.

```
	<goto label;> 
	.... 
	<label:>
	<statement;>
```

- goto labels are traditionally capitalized, based on the first column.
- goto labels can be placed anywhere within a function, before a statement. That is, the label can be placed above or below the goto keyword, provided it is within the same function.

## Random Number Generation

**rand Function**

- The standard `rand` function generates a random number. The rand function's declaration is in a standard header file, stdlib.h.

**srand Function**

- The standard `srand` function serves to change the seed value of the random number generator. The declaration of the srand function in the stdlib.h header file is as follows:

```
void srand (unsigned int seed);
```

### Random Real Number Generation

- There is no standard C function that generates random real numbers.
- With the (double)rand() / RAND_MAX statement, a random real number in the range of 0 – 1 can be generated.

**[Go to Top](#contents)**

## Arrays

**What is data structure?**

- Arrangements for storing data in a logical relationship about a subject in memory is called a data structure. Data structures allow accessing data kept in a certain order in memory and performing some operations on these data effectively.

**What is Array?**

- A data structure made up of objects of the same type that are contiguous in memory is called an array. The most important feature of the array data structure is that data of the same type in a logical relationship is kept contiguous in memory.
- Regardless of the number of elements in the array, the access time to an element whose position is known is the same.

**Arrays in C Language**

- By defining an array in C, multiple objects can be created with a single statement.
- It is ensured that all objects that are members of the array are contiguous in memory.

**Arrays Initializing**

- The general format of array definitions is as follows:

```
// <type> <array_name> [<element_number>];
//type : A word or words that indicate the type of array elements.
//array_name : It is any name to be given in accordance with the naming conventions.
//element_number : Indicates how many elements the array has.

int a[20] = {0}; // In this case, if it is desired to give the value 0 to all elements of an array, it is the shortest way.

```

- The expression specifying the number of elements must be a constant expression of an integer type.
- The n-index element of an array is (n+1) of that array. element.
- Array overflows are not checked at compile time. Such errors are related to the runtime of the program.
- It is mandatory to use constant expressions to initialize array elements.
- Array size may not be specified in initialization. In this case, the compiler calculates the string length by counting the given initial values. It assumes that the directory is opened in that size.
- In the case of a general array, the array elements are initialized with the value 0 if the array elements are not given a value. But in the case of local arrays, objects that are array elements have block scope and automatic storage class in terms of lifetime. Unassigned local array elements contain garbage values.
- Array elements are objects. However, an entire array cannot be treated as an object.

```
	int a[SIZE], b[SIZE];
	a = b; /* Invalid */

	for (i = 0; i < SIZE; ++i) 
		a[i] = b[i];
```

**[Go to Top](#contents)**

### Sorting Arrays

- **Binary Search** : It is an algorithm for finding a specific value in an ordered array. At each step in this technique, it is checked whether the sought value is equal to the middle value of the array.
- **Bubble Sort** : It is based on the logic of comparing two items with each other each time while continuously moving over the array to be sorted, and swapping the compared items if they are in the wrong order.
- **Insertion Sort** : It is a sorting algorithm that builds an ordered array, item by item, at each step.
- **Selection Sort** : Simply find where the smallest number in the array is at each step. By replacing this number with the number at the beginning of the array, the smallest numbers are selected and it is thrown to the beginning.

**Arrays and strings of char type**

- Strings are no different from other string types, except for some additional features. Arrays of type char are more often defined to hold text in them.
- In C language, the concept of "terminator character" (null character) is used to perform operations on characters quickly and effectively. The terminating character is the zero-numbered character ('\x0' or '\0') of the ASCII table or the character set used in the system.
- There must be a terminating character at the end of a text. All standard functions of C that work with texts assume that there is a terminating character at the end of the text they are processing.

**Initializing arrays of type char**

- Array size may not be specified when initializing array elements. In this case, the compiler determines the array size by counting the given initial values. The compiler assumes the array is opened at this size.
- It is illegal to initialize more elements than the number of elements in the array. There is an exception to this situation. This is valid if the number of elements in the array is initialized in double quotes. In this case, the compiler does not place the terminating character at the end of the string.

  `char name[3] = "Ali"; /* in C valid, in C++ invalid */`

**[Go to Top](#contents)**

**gets Function**

- gets is a standard C function used to get a string of characters from the keyboard. The user must press enter after entering characters from the keyboard.
- Array names actually specify an address information.
- It places the terminating character ('\0') at the end of the string after inserting the characters entered from the keyboard into the array.

```
char s[6];
gets(s); 
```

- code is written, the compiler allocates 6 bytes of memory for this array (s[0] ...s[5]).
- if "bardak" is entered in the keyboard for the above code, then the gets function writes the character '\0' to a memory cell that the compiler has not reserved for the array. Such cases are called "off by one".
- The errors that will occur with the overflow condition are run time, not compile time.

**scanf Function**

- While processing character input with scanf, the insertion process ends with the first space character taken from the keyboard.
- The '_' character can be used as a space character. In this way, different arrays can be written to the same scanf call.

**puts Function**

- puts is a standard C function.
- It is used to print the text held in a character string to the screen.
- The puts function puts the cursor at the beginning of the next line after writing the string to the screen.

**[Go to Top](#contents)**

**sizeof Operator**

- The sizeof operator in the prefix position produces the value of how many bytes an object of a given type occupies in memory.
- The value this operator produces is a literal expression for the compiler at compile time.
- The sizeof operator has three distinct uses:
    1. As a term, words denoting genre can be used. In this case, the term must be enclosed in parentheses:

        ```
        sizeof(int)
        sizeof(double)
        sizeof(long)
        ```

    2. Any expression can be used as a term. In this case, it is not necessary to enclose the term in parentheses. However, most programmers prefer to put the term in parentheses for readability:

        ```
        double x;
        sizeof(x)
        sizeof(17.8)
        sizeof(func())
        ```

    3. When the sizeof operator takes the name of an array as a term, it produces the value of how many bytes the array occupies in memory, that is, the length of the array in bytes.

        ```
        double x[10];
        sizeof(x)
        ```

**The precedence of the sizeof operator**

- sizeof is also a second-level operator.

**[Go to Top](#contents)**

**The type of value produced by the sizeof operator**

- The value produced by the sizeof operator is of type unsigned int.
- When the value produced by the operator is processed with a negative number of type signed int, the type conversion is done in the unsigned direction.
- In fact, the value produced by the sizeof operator is of the standard typedef type size_t.

**Side-effect of the expression, which is the term of the sizeof operator**

- The expression that is the term of the sizeof operator is not evaluated. The compiler treats this information as type information at compile time.

**The value produced by the sizeof operator is a literal expression**

- The value produced by the sizeof operator is obtained at compile time. So this value can be used wherever a "literal expression" is required.


## Pointer

- The address of an object is information that indicates the location of that object in memory.
- Syntax: `<type> *<pointer_name>;`
- The length of the places that compilers reserve for pointers depends on the hardware and may vary from system to system.
- It can be 2 bytes or 4 bytes. In DOS, pointers with a length of 2 bytes are called near pointers, and pointers with a length of 4 bytes are called far pointers.

**Address Constants**

- The hexadecimal number system is traditionally used for writing address constants.

**Type Compatibility Related to Pointers**

|Operator|Name                                 |
|-|--------------------------------------------|
|*|indirection operator(dereferencing operator)|
|&|address of operator|
|[]|index/subscript operator|
|->|arrow operator|

**`&` address operator**

- The value this operator produces is the address of the object with the term.
- If the argument mapped to the `%p` format conversion characters is an address information, the printf function prints only the numeric component of the corresponding address information in hexadecimal number system.

**Pointer Arithmetic**

- When the value of a char type pointer is increased by 1, the numeric component of the address increases by 1, when an int type pointer is increased by 1, the numeric component of the address increases by 4, and when a double type pointer is increased by 1, the numeric component of the address increases by 8.
- Two addresses on the same block can be compared with comparison operators.

**`[]` index/subscript operator**

- The first term of the operator comes before the bracket. This term becomes an address information.
- The first term of the `[ ]` operator does not have to be the array name.
- Initialization of pointers should be done with an address information of the pointer type.

**[Go to Top](#contents)**

**Functions with Return Value of Address Type**

- In the definition of such a function, an address type is written where the type of the function's return value is to be written.
- If the calling code gets the value of an object from the function, it cannot change the object with that value. However, if it gets the address of an object from the function, it can change the address of the retrieved object.

**Returning with Addresses of Local Objects**

- A function that returns an address should never return the address of an auto-lived local object.
- Returning addresses of auto-lived local objects is a typical programming error.
- A function returning an address should not return the address of a local variable or the starting address of a local array.

**`NULL` Pointer**

```
int x = 10; 
int *ptr = &x;
```

- We can define the above statement with the following sentences:
    - The pointer variable `ptr` holds the address of object `x`.
    - The `ptr` pointer variable points to the object `x`.
    - The `*ptr` object is the object `ptr` points to.
    - `*ptr` is the object `x` itself.

- `NULL` is a symbolic literal. This symbolic literal is defined in the standard header files stdio.h, string.h and stddef.h.
- The `NULL` address can be assigned to any pointer variable.
- When a pointer variable is assigned a value of `0` of any type, the pre-assignment value `0` is automatically converted to `NULL`.
- If a function returning an address fails, the function can report its failure by returning a `NULL` address.
- It is a very common convention in C that a function that returns an address should return a `NULL` address on failure.
- Before a pointer has expired, the object it points to may expire. In this case, the address with the value of the pointer is not a reliable address.

**Pointers Warnings and Possible Pointer Errors**

- Assigning a different type of address to a pointer
    - When a pointer variable is assigned a different type of address, most C compilers are suspicious of the situation, giving a logical warning message.
- Assigning a non-address value to a pointer variable

**[Go to Top](#contents)**

**Locations of Objects in Memory**

- The memory layout of variables larger than one byte may vary depending on the microprocessor used. Therefore, the appearance of variables in memory is not portable information.
    1. Low-significant byte values to be found at the low-numbered address of memory. Such a layout is called little endian. Intel processors use this layout.
    2. A second form of location is to place the low-significant byte at the high numeric address. Such a layout is called big endian. Motorola processors use this layout.

**`strlen` Function**

- It is used to obtain the character length of a text, that is, how many characters the text consists of.
- Syntax : `size_t strlen(const char *str);`

**`strchr` Functions**

- The strchr function is a standard C function to search for a specific character in a string.
- Syntax: `char *strchr(const char *ptr, int ch);`
- This function searches for the second parameter, `ch`, starting with the first parameter, `ptr`, until it sees the terminating character.
- If the `ch` character is not found in the text, the function returns `NULL`.

**`strrchr` Function**

- This standard function searches for a character in a text like the `strchr` function. The search is done starting from the end of the text.
- Syntax: `char *strrchr(const char *ptr, int ch);`
- If there is no `ch` character in the text, the return value of the function is `NULL`.

**`strstr` Function**

- This function searches another text within a text.
- Syntax: `char *strstr(const char *p1, const char *p2);`
- If text at address p1 contains text at address p2, the function returns the address of the text's location. If not, the return value of the function is `NULL`.

**`strcspn` Function**

- With this function, the index of the first character in another text in a text is found.
- Syntax: `size_t strcspn(const char *p1, const char *p2);`

**`strpbrk` Function**

- The standard `strpbrk` function searches for any of the characters of another text in a text.
- Syntax: `char *mStrpbrk(const char *s1, const char *s2)`
- If the text at address s1 contains any of the characters of the text at address s2, the function returns the address of that character. If none of the characters of the text s2 are present in the text s1 the function returns `NULL`.

**`strcpy` Function**

- The function writes all characters in sequence, starting with the address held in the first parameter, including the terminating character, starting with the address held in its second parameter, until it sees the terminating character.
- Syntax: `char *strcpy(char *dest, const char *source);`

**`strcat` Function**

- The `strcat` function is used to copy another text to the end of a text.
- Syntax: `char *strcat(char *s1, const char *s2);`

**`strcmp` Function**

- The function is used to compare two strings of characters. Comparison is querying the priority or equality of text in two strings, taking into account the character set table used.
- Syntax: `int strcmp(const char *s1, const char *s2);`
- The function compares the text with the start address in the first parameter variable with the text with the start address in the second parameter variable.
- The return value of the function is:
    1. is a positive value if the first text is larger than the second text
    2. is a negative value if the first text is smaller than the second text,
    3.If the first text and the second text are equal, it is 0.

**`strncpy` Function**

- The function is used to copy the first n characters of a text (character string) to another location.
- Syntax: `char *strncpy(char *dest, const char *source, size_t n);`

**`strncat` Function**

- It is used to copy a certain number of characters from another text to the end of a text.
- Syntax: `char *strncat(char *s1, const char *s2, size_t n);,`
- The function copies the character string whose start address is given in the first parameter variable to the end of the text whose start address is given in the second parameter, as many as the number of integer characters held in the third parameter.
- The return value of the function is the starting address of the text to be appended to.

**`strncmp` Function**

- It is similar to the `strcmp` function, except that it is used to compare a certain number of characters, rather than all of the two texts.

**`strset` Function**

- This non-standard function is available in most compilers. The name of the function comes from the words string and set. It is used to fill a string of characters with a specific character.
- Syntax: `char *strset(char *str, int ch);`
- The function fills the text with the starting address in the first parameter variable with the character held in the second parameter variable until it sees the terminating character. It does not touch the terminating character at the end of the text.

**`strrev` Function**

- This non-standard function is also available in most compilers.
- The function is used to reverse a text.
- Syntax: `char *strrev(char *ptr);`
- Inverts the text whose start address is held in the function parameter variable. The return value of the function is the starting address of the reversed text.

**`strupr` and `strlwr`Functions**

- Although these functions are not standard, they are available in almost every compiler.
- These functions perform uppercase conversion for all characters of a text.

**[Go to Top](#contents)**

**Typical situations that generate a pointer error**

1. Errors caused by uninitialized pointers
  -Where the data is transferred, there may be code from the operating system, compiler, or other program (memory resident) that remains in memory. In some systems, the program's own code can also be found where the data is transferred.
2. Pointer errors caused by unsafe initial values
3. Pointer errors due to array overflows
  - During the compilation process, when the compiler program sees that an array has been defined, it allocates memory for the array. C compilers do not check at compile time whether a directory has been moved.

## void Type Pointer

- `void` pointers have no type information. Only numeric components of addresses are stored in `void` pointers.
- A pointer variable of type void can be assigned an address of any type.
- An address of type `void` can also be assigned to a pointer variable of a certain type.

```
char *ptr; 
void *vp; 

/***/ 

ptr = vp; /* Invalid */ 
vp = ptr; /* Invalid */
```

- Some operations on pointers with type information cannot be applied to pointers of type void:
  1. It is illegal for void type pointers to be terms for the * or [ ] operators. These operators require type information to access an object.
  2. Adding an integer with an address of type void or subtracting an integer from an address of type void is illegal.
  3. Similarly, two addresses of type void cannot be inferred from each other. For other types of addresses, subtracting two addresses for two objects in the same block is perfectly valid.

- They can also be found in the form of parameter variables in functions where type-independent address operations are performed.
- Functions in C can also return void addresses. Assigning addresses of type void to a pointer variable of any type is valid.

**void ** Type**

- An object of type `void **` is not an object that can hold the address of a pointer variable of any type.
- Type `void **` is the type of information that can be the address of an object of type `void *`. An object of type `void **` must only be assigned the address of an object of type `void *`.

**[Go to Top](#contents)**

## Strings

- When C compilers encounter a string during compilation, they first generate code that places the characters that make up the string into a safe area of memory, with the terminating character at the end.
- The memory space of strings is determined by the compiler at compile time.

**Passing Strings as Arguments to Functions**

- From the point of view of compilers, it is perfectly natural to call a function whose parameter variable is a pointer of type char, with a string.

**Strings are Read Only**

- Strings can be kept in read-only memory areas. So it is wrong to change the contents of a string within the source code.
- Codes that modify strings show undefined behavior.

**Identical String**

- C compilers can only store one copy of identical strings in memory.
- How identical strings are stored is left to the compiler's choice. Many compilers allow the programmer to choose how identical strings are kept in memory.

**Comparing Strings**

- Direct comparison of the strings is a false process.

**Life of Strings**

- Strings are static duration entities.
- Strings are written to the .obj module by the compiler and to the .exe file by the linker program. They earn life with the installation of the program.

**Returning a function with a String**

- A pointer error is when a function returning an address returns the address of a local variable or a local array.
- A function returning an address of type char may return a string.

**Concatenating Strings**

- Because strings are treated as a single atom, they must be written one line at a time.
- To allow fragmentation of long strings, strings with no characters other than a space character between them are concatenated by the compiler and treated as a single string.

```
ptr = "Necati Ergin'in C Ders "
"Notlarını okuyorsunuz";
```

- For the compiler to concatenate two strings, there must be no characters other than white space between the strings.
- It is possible to pass the next line by ending the string with a backslash character without closing it.

**[Go to Top](#contents)**

**Using backslash character literals in Strings**

- Escape sequences can also be used within strings.
- Double quotes or backslash characters cannot be used directly in string expressions.
- Backslash character literals in a string can also be expressed in the octal number system.

**Empty Strings**

- A string can be empty (null string) thats mean it may not contain any characters.
- Empty strings also specify an address in memory. When the compiler sees an empty string, it only places the terminating character in a safe place in memory.

**Initializing pointer variables with Strings**

- Pointer variables of type char can be initialized with strings.

```
char *p = "Hasan";
char s[10] = "Hasan";
```

- The two designations above are different from each other. 
-After the string is placed in memory, the starting address is assigned to the pointer variable. Whereas, in arrays, space is reserved for the array first, then the characters are placed in the array elements one by one.

**strlen function and sizeof operator**

- **sizeof** is an operator that is handled at compile time.
- **strlen** is a standard C function. Of course, the return value of this function is obtained during the execution of the program.
- The return value of the **strlen** function is the length of the received text.

**Where should strings be used?**

- When using texts whose content does not change dynamically at program runtime.
- When texts to be used for reading-only purposes are used in the source code.

## Pointer Arrays

- The '*' atom is used in the declarations of pointer arrays, unlike normal array declarations.
- `char *pStrArray[100];`
  - **pStrArray** is a 100-element char array of pointers. That is, each element of the array is an object of type char *. Each element of the array is a pointer.

**Initializing Arrays of Pointers**

```
int *p[] = { 

     (int *) 0x1FC0, 
     (int *) 0x1FC4, 
     (int *) 0x1FC8, 
     (int *) 0x1FCC, 
     (int *) 0x1FD0 

 }
```

- It is not uncommon to initialize arrays of pointers other than char arrays. Generally, arrays of char type pointers are initialized with string expressions.

**Pointer Arrays of Type Char**

- The most common char type pointer arrays in applications.
- Strings are automatically converted to char array addresses by the C compiler.
- Elements of a char array can be initialized with strings.

**Themes for Using Pointer Arrays of Type char**

- It is a common theme that the frequently used texts in the program are stored in the elements of a pointer array instead of being written as a string each time in the source code.
- In order to test whether a text exists within a certain number of text groups, char type pointer arrays are often used.
- If the array is public, the value of all array elements is `NULL` when the array starts life. Inside a local pointer array are garbage values.
- To avoid causing a pointer error, it is necessary to set safe addresses to the elements of the pointer array first.
- Strings are static-lived entities.

**Pointer to Pointer**

- Pointer variables are objects that contain address information.
- The `&p` expression is a type that can be the address of an object of type `int *`. This type is represented as `int **` type in C language.

**Functions that Change the Value of a Local Pointer Variable**

- In a function to change the value of a local pointer variable, it must take the address of the local pointer, not its value!

**Functions that Operate on an Array of Pointers**

- The function that operates on an array needs to get the start address of the array and the size of the array.
- From a compiler's point of view, `a` is equivalent to `&a[0]`.

**[Go to Top](#contents)**