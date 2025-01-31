---
sidebar_position: 1
title: Introduction to Structs
---

In this module, we will explore a significant topic in C programming: structs. Structs allow you to create complex data types that group different types of data together. This is essential for solving more complex problems that involve multiple related data elements.

### Abstract Data Types

We've already discussed abstract data types (ADTs) with enums. Structs are another form of ADT, allowing you to define custom data types that can represent more complex entities.

### Native Types

C provides several native types such as `int`, `char`, `float`, and various pointer types. These types are useful for solving many problems, especially those involving text and mathematical operations.

### Example: Playing Cards

Consider a scenario where you need to represent playing cards for a game. A playing card has two main components:
- **Pips Value**: Represented as an integer from 1 to 13 (Ace to King).
- **Suit**: Represented as a character (`C` for clubs, `D` for diamonds, `H` for hearts, `S` for spades).

### Defining a Struct

We can define a struct to represent a playing card:
```c
struct Card {
    int pips; // Pips value (1-13)
    char suit; // Suit ('C', 'D', 'H', 'S')
};
```
- `struct` is the keyword.
- `Card` is the tag name.
- The struct contains two members: `pips` and `suit`.

### Using the Struct

You can declare variables of this struct type:
```c
struct Card deck[52]; // Array of 52 cards
```
- This creates an array of 52 `Card` structs, representing a standard deck of playing cards.

### Simplifying Declarations with `typedef`

To simplify declarations, you can use the `typedef` keyword:
```c
typedef struct {
    int pips;
    char suit;
} Card;
```
- Now, you can declare variables using `Card` instead of `struct Card`:
```c
Card deck[52];
```

### Summary

Structs are a powerful feature in C that allow you to create custom data types. They are essential for representing complex entities and solving more sophisticated problems. In this module, we will delve deeper into how to use structs effectively in your programs.

---

Let's get started with structs and see how they can be used to build more complex and useful data types in C.