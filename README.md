# C Programming Notes

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
    - [Memorizing Real Numbers](#memorizing-real-numbers)
4. [Creating a C Program](#creating-a-c-program)
    - [Utilities](#utilities)
5. [Data Types](#data-types)
    - [Integer Types](#integer-types)
    - [Floating Types](#floating-types)
    - [Virtual Types](#virtual-types)
6. [Declaration and Definition](#declaration-and-definition)
7. [Constants](#constansts)
8. [Functions](#functions)

---

## History of the C Language

The C language was born as a by-product of the UNIX operating system. Ken Thompson developed the B language and programmed part of the UNIX operating system with B. In 1971, when it became clear that the B language was not suitable for the development of PDP-11 computers and the UNIX operating system, Dennis Ritchie began to create a further version of the B language. He first named this language NB (New B). But, this new language broke away from the B language and started to show different characteristics. That's why he later changed the name of this new language to C. In 1973, most of the UNIX operating system was rewritten in C language. C language became known and used by the masses thanks to the book "C Programming Language" written by Dennis Ritchie and Brain Kernighan in 1978.

The version of the C language used until the standardization process is called Traditional C. The C language was standardized by the American National Standards Institute (ANSI) in 1989. Its official name is American National Standard X3.159-1989, known as ANSI C for short. Then an international standard was established and accepted by ANSI. The commonly accepted standard is called Standard C or C89 for short. C95 and C99 standards are also available. Which version to use depends on the decision of the compiler to be developed and the portability level of the code.

## General Concepts and Terms

### Some features of C language

- C language is an intermediate programming language close to both machine perception and human perception.
- C language can be preferred directly to machine language for many applications from an efficiency point of view. Because it is much easier to write the same program in machine language and the loss of efficiency is less.
- The main programming area of the C language is systems programming.
- C is an algorithmic language.
- It has high portability and readability features.
- It is very flexible. It is efficient.
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

- If only zero and positive integers are shown, the binary number system used in this format is called the unsigned binary number system.
- The use of the binary number system to show negative integers is called the signed binary number system.

### MSD and LSD

- The leftmost bit of a number written in the unsigned binary number system adds the highest numerical value. This bit is called the Most Significant Digit.
- The rightmost bit of a number written in the unsigned binary number system adds the lowest numeric value. This bit is called the Least Significant Digit.

### One's and Two's Complements

- One's complement is the number obtained by inverting all bits of the number.
- 1 more than the one's complement of a number is the two's complement of the number. Or, Starting from the far right of the number, the same number is written until the 1st bit is seen for the first time, including the first 1 bit.

### Negative Number Representation

- The binary number system in which negative integers are also expressed is called a signed binary system.
- In binary, a negative number is the two's complement of a positive number of the same value.
- In the signed binary number system, a number whose all bits are 1 is -1. *( -1 = 1111 1111 )*

### Memorizing Real Numbers

- In most systems, the actual numbers are kept according to the IEEE (Institute of Electrical and Electronics Engineers) 754 standard.
- According to this standard, two different formats are determined for real numbers:
  1. *single precision format*
  2. *double precision format*

## Creating a C Program

- This is the compilation cycle of a .c file :
  - *file.c -> **Preprocessor** -> file.i -> **Compiler** -> file.s -> **Assembler** -> file.o -> **linker** -> file.exe*
- The preprocessor program makes some textual changes on the source file. The output of the preprocessor program is given to the compiler program.
- The extension of purpose files created on Unix/Linux systems is ".o". In DOS and Windows systems, purpose files have the ".obj" extension.

### Utilities

- **Text Helpers** : With such programs, search, cut and paste operations can be done within the source file. It can be ensured that the names are completed automatically without writing all the long names.
- **Logical Error Catchers** : There are special programs that try to catch programming errors that escape the logical warnings of compiler programs. The most used of these programs is a software called LINT.
- **Code Formatters** : They are programs that organize the general layout of the source code (styler).
- **Profiler Programs** : These programs are used to measure and evaluate the efficiency of a running program.

## Data Types

- C language has 12 predefined data types. 9 of these types are designed to hold integer data, and the remaining 3 are designed to hold real-number data. These types are integer types and floating types.

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

## Constants

## Functions
