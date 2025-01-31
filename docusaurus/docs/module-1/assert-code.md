---
sidebar_position: 5
title: Assert Code
---

This section demonstrates the use of `assert` in C with simple test programs.

### Basic Assert Example

First, we include the assert header file and use a basic assert:
```c
#include <assert.h>
#include <stdio.h>

int main() {
    assert(0); // This will always fail
    printf("My program runs\n");
    return 0;
}
```
- `assert(0)` will fail because `0` means false.
- When the assertion fails, it prints an error message and aborts the program.

### Running the Program

When compiled and run, the output will show:
```
assert failed: function main, file assert_test1.c, line 16
```
- This indicates where the assertion failed.

### Using NDEBUG to Disable Asserts

By defining `NDEBUG`, we can disable asserts:
```c
#define NDEBUG
#include <assert.h>
#include <stdio.h>

int main() {
    assert(0); // This will be ignored
    printf("My program runs\n");
    return 0;
}
```
- With `NDEBUG` defined, the assert is ignored, and the program runs normally.

### Math Program with Asserts

Here’s a simple math program using asserts:
```c
#include <assert.h>
#include <stdio.h>

int main() {
    double x, y;
    while (1) {
        printf("Enter two floats: ");
        scanf("%lf %lf", &x, &y);
        assert(y != 0); // Ensure y is not zero
        printf("%f / %f = %f\n", x, y, x / y);
    }
    return 0;
}
```
- This program reads two floats and asserts that `y` is not zero to avoid division by zero.

### Running the Math Program

When run, the program will:
- Prompt for two floats.
- Print the division result.
- Fail with an assertion if `y` is zero.

### Disabling Asserts with NDEBUG

Compile the program with `-DNDEBUG` to disable asserts:
```sh
gcc -DNDEBUG -o math_program math_program.c
```
- With asserts disabled, dividing by zero will result in `inf` or `NaN` instead of an assertion failure.

### Summary

Using `assert` helps in checking preconditions and postconditions in your code, making it more robust and easier to debug. Disabling asserts with `NDEBUG` can be useful once the code is verified to be correct.

---

This concludes the section on assert code. Experiment with the code and try adding more assertions to understand their impact.
```

Feel free to adjust this as needed for your documentation. If you need any more help, just let me know!