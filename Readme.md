Dynamic String in C
===================

Write a C program that implements a dynamically sized string called `my_string`. The structure of `my_string` should contain a character array and a `size_t` integer to store the string's current length. Write functions to initialize the structure with a given string, resize the string when needed, append a character to the string, concatenate another string, and free the memory allocated for the string. You must implement the functions in the `my_string.c` file. You cannot use any string manipulation functions from the standard library to implement this project. You must create your own `Makefile` to build the code and the test program.

## Functionality to Implement

1. Initialize the structure with a given string (`my_string_init`).
2. Resize the string when needed (`my_string_resize`).
3. Append a character to the string (`my_string_append_char`).
4. Concatenate another string to our string (`my_string_concat`).
5. Free the memory allocated for the string (`my_string_free`).

## Definitions

The string's header should have the following definitions:

```c
#include <stddef.h>

typedef struct {
    char* data;
    size_t length;
} my_string;

void my_string_init(my_string* str, const char* input);
void my_string_resize(my_string* str, size_t new_size); // called by `my_string_append_char` and `my_string_concat`
void my_string_append_char(my_string* str, char c);
void my_string_concat(my_string* str, const char* input);
void my_string_free(my_string* str);
```

## Test Code

Here is an example C code with the `main` function to test our string:

```c
int main(void)
{
    my_string str;

    // Initialize the structure with a given string
    my_string_init(&str, "hello");

    // Append a character to the string
    my_string_append_char(&str, ' ');

    // Concatenate another string
    my_string_concat(&str, "world");

    // Print the resulting string and its length
    printf("String: %s\n", str.data);
    printf("Length: %d\n", str.length);

    // Free the memory allocated for the string
    my_string_free(&str);

    return 0;
}
```

Here is the directory structure with the names of the files that you must create:

```
<Your private GitHub repository>
...previous works
project
├── Makefile
├── my_string.c
├── my_string.h
└── proj.c
```

Ensure not to submit any binary files (object files and executables). Your grade will be lowered for that. You will get a zero for a late submission. In addition, you will get zero if the auto-grading script cannot parse your commit, clone your repository, check out the commit, find your source files under the specific names the instructor was using during the class, build the sources, and run your programs. You will also get zero if your programs' output format is different from that outlined in the samples.

## Documentation

    man gcc
    man gdb
    man make

## Links

* [Beej's Guide to C Programming](https://beej.us/guide/bgc)

## Books

* C Programming: A Modern Approach, 2nd Edition by K. N. King
