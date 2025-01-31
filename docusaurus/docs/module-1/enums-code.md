---
sidebar_position: 2
title: Enums Code
---

In this section, we will see actual code for user-defined types based on enums. This will help us understand how enums work in practice.

### Declaring an Enum Type

Here is the declaration of an enum type:
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
- `enum` is the keyword.
- `Day` is the tag name for this type.
- The enumerators `SUNDAY`, `MONDAY`, `TUESDAY`, `WEDNESDAY`, `THURSDAY`, `FRIDAY`, `SATURDAY` are constants with values 0, 1, 2, 3, 4, 5, and 6 respectively.

### Using Enums in Functions

Enums can be used in functions to perform operations. Here’s an example function that prints the day of the week:
```c
#include <stdio.h>

enum Day {
    SUNDAY,
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY
};

void printDay(enum Day day) {
    switch(day) {
        case SUNDAY: printf("Sunday\n"); break;
        case MONDAY: printf("Monday\n"); break;
        case TUESDAY: printf("Tuesday\n"); break;
        case WEDNESDAY: printf("Wednesday\n"); break;
        case THURSDAY: printf("Thursday\n"); break;
        case FRIDAY: printf("Friday\n"); break;
        case SATURDAY: printf("Saturday\n"); break;
        default: printf("Error: Invalid day\n"); break;
    }
}
```
- The `switch` statement is used to determine the behavior based on the enumerator value.
- Each case corresponds to an enumerator and prints the corresponding day.

### Getting the Next Day

Here’s a function to get the next day:
```c
enum Day nextDay(enum Day day) {
    return (day + 1) % 7;
}
```
- This function returns the next day, using the modulo operator to wrap around from `SATURDAY` to `SUNDAY`.

### Main Function Example

Here’s how you can use the enum and functions in the `main` function:
```c
int main() {
    enum Day today = FRIDAY;
    printDay(today); // Prints "Friday"

    enum Day tomorrow = nextDay(today);
    printDay(tomorrow); // Prints "Saturday"

    return 0;
}
```
- The `main` function declares a variable `today` of type `enum Day` and initializes it to `FRIDAY`.
- It then prints the current day and the next day.

### Typedef for Enums

Using `typedef` can simplify the usage of enums:
```c
typedef enum Day {
    SUNDAY,
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY
} Day;

void printDay(Day day) {
    // Same function as before
}

Day nextDay(Day day) {
    // Same function as before
}

int main() {
    Day today = FRIDAY;
    printDay(today);
    Day tomorrow = nextDay(today);
    printDay(tomorrow);
    return 0;
}
```
- `typedef` allows us to use `Day` instead of `enum Day`, improving code clarity.

---

This concludes the section on enums code. Try adding more functions like `yesterday` or `tomorrow` to practice working with enums.