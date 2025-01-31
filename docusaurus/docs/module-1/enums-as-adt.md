---
sidebar_position: 1
title: Enumerated Types as ADT
---

The ADT (Abstract Data Type) is a powerful concept in programming. It allows the creation of new types that are not native to the language.

## Understanding User-Defined Types

The first topic in this class is understanding user-defined types, starting with the simplest form: the enumeration type. This topic is covered in section 7.5 of *A Book on C*.

### Native Types in C

Critical to a programming language are its native types, which in C include:
- `int`
- `float`
- `double`
- `char`
- `short`
- `long`
- `pointer`

These types are useful for different kinds of problems. For example:
- Mathematical problems often use `int` and `double`.
- Data processing and screen processing problems use `char` and `pointer to char`.

### Type Extension

Languages can't have every type needed for specific problem domains. Modern languages like Java and C++ have powerful type extension abilities. C, being more primitive, was designed for system implementation tasks but became a general-purpose language due to its efficiency and convenience. Even in C, type extension is possible through enumerators.

### Enumerators

Enumerators allow the creation of user-defined types. For example, to represent days of the week:
```c
enum Day {
    SUNDAY,
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY
};
```
This defines a new type `enum Day` with values `SUNDAY` through `SATURDAY`. Enumerators are assigned integer values starting from 0 by default.

### Type Checking

Type checking at the compiler level makes debugging easier. Although C is a weakly typed language compared to Java, type safety is still useful. For example, C uses zero or non-zero to represent Boolean values, and compilers often warn about common errors like using `=` instead of `==`.

### Type Conversion

C allows loose type conversion, which can be convenient but also prone to errors. For example, dividing two integers results in an integer, which might not be the intended result. Using type casting can help achieve the correct result.

### Creating Enumerated Types

To create an enumerated type:
```c
enum Day {
    SUNDAY,
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY
};
```
This announces to the compiler that `enum Day` is an enumerated type with values `SUNDAY` through `SATURDAY`. These values are small integer constants starting from 0.

### Custom Values

Enumerators can be assigned custom values:
```c
enum Day {
    SUNDAY = 1,
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY
};
```
This assigns `SUNDAY` the value 1, and the rest follow sequentially.

### Summary

Enumerated types in C are a form of integer type, providing a way to create user-defined types that enhance program clarity and type safety.

---

Next, we will write some code to test this idea.
