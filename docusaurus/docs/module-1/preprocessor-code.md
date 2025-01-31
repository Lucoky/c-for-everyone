---
sidebar_position: 4
title: Preprocessor Code
---

This section demonstrates the use of the preprocessor in C with a code example that generates random weights for a thousand male southern elephant seals.

### Including Standard Libraries

We start by including standard libraries:
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
```
- These libraries provide functions for input/output, random number generation, and time management.

### Defining Constants and Macros

We define constants and macros using `#define`:
```c
#define MAX_WEIGHT 8800
#define MIN_WEIGHT 4400
#define RANGE (MAX_WEIGHT - MIN_WEIGHT)
#define POPULATION 1000

#define RANDOM_WEIGHT (rand() % RANGE + MIN_WEIGHT)
```
- `MAX_WEIGHT` and `MIN_WEIGHT` define the weight range for male southern elephant seals.
- `RANGE` calculates the difference between maximum and minimum weights.
- `POPULATION` defines the number of samples.
- `RANDOM_WEIGHT` generates a random weight within the specified range.

### Multi-line Macro

We use a multi-line macro to fill an array with random weights:
```c
#define FILL_POPULATION(data) \
    for (int i = 0; i < POPULATION; i++) { \
        data[i] = RANDOM_WEIGHT; \
    }
```
- The backslash (`\`) character allows the macro to span multiple lines.

### Printing the Data

We define a function to print the data:
```c
void printData(int data[], int size) {
    for (int i = 0; i < size; i++) {
        printf("%d\t", data[i]);
        if ((i + 1) % 10 == 0) {
            printf("\n");
        }
    }
}
```
- This function prints the array values, ten per line.

### Main Function

The `main` function ties everything together:
```c
int main() {
    int data[POPULATION];
    srand(time(NULL)); // Seed the random number generator

    FILL_POPULATION(data);
    printData(data, POPULATION);

    return 0;
}
```
- `srand(time(NULL))` seeds the random number generator with the current time to ensure different results on each run.
- `FILL_POPULATION(data)` fills the array with random weights.
- `printData(data, POPULATION)` prints the generated weights.

### Summary

This example demonstrates the power of macros in C. However, modern C and C++ programming practices rely less on macros for code segments, favoring compiler optimizations and inline functions for safer and more maintainable code.

---

This concludes the section on preprocessor code. Experiment with the code and try modifying the macros to understand their impact.