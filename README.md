# ft_printf

<p align="center">
  <img src="https://github.com/ArenKae/ArenKae/blob/main/42%20badges/ft_printfe.png" alt="ft_printf 42 project badge"/>
</p>

This project's goal is to implement our own `printf()` function from the C standard library. To achieve that, we will need to learn more about variadic functions in order to use a variable number of arguments.

## Status
✅ Completed on: 03/02/2023
</br>
🏆 Grade: 100/100

## Usage

- Clone the repository and use ```make``` to compile.

- The resulting file is a static library archive. To use it in our future code, we must include its header and link the library during compilation.

```c
// test.c

# include "include/ft_printf.h"
# include <stdio.h>

int main(void)
{
	printf ("Original printf function:\n");
    printf("Hello world!\n");
	ft_printf ("My ft_printf function:\n");
    ft_printf("Hello world!\n");
    return (0);
}
```
Compile the ``test.c`` file with the ft_printf library and run the program:
```bash
gcc test.c libftprintf.a && ./a.out
```
Output should be:
```
Original printf function:
Hello world!
My ft_printf function:
Hello world!
```
## Supported options
Format Specifier | Description
|:-:|:-|
% | % followed by another % character writes % to the screen.
c | writes a single character.
s | writes a character string.
p | writes an implementation-defined character sequence defining a pointer address.
d or i | writes a signed integer to decimal representation.
u | writes an unsigned integer to decimal representation.
x or X | writes an unsigned integer to hexadecimal representation.

## About variadic functions

```c
# include <stdarg.h>

void variadic_function(int n, ...)
{
	// Data type that stores the informations needed to retrieve all arguments.
	va_list args;

	// Initialize va_list and give access to the stored arguments.
	va_start(args, n);

	// Returns the next argument from the va_list.
	va_arg(args, type);

	// Clean up the va_list to prevent leaks.
	va_end(args);
}
```
