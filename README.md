# ft_printf

<p align="center">
  <img src="https://github.com/ArenKae/ArenKae/blob/main/42%20badges/ft_printfe.png" alt="ft_printf 42 project badge"/>
</p>

This project's goal is to implement our own `printf()` function from the C standard library. To achieve that, we will need to learn more about variadic functions in order to use a variable number of arguments.

## Status
✅ Completed on: 02/03/2023
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
<table>
    <thead>
        <tr>
            <th>Format Specifier</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
	</thead>
        <tr>
            <td align="center">%</td>
            <td>% followed by another % character writes % to the screen.</td>
        </tr>
        <tr>
            <td align="center">c</td>
            <td>writes a single character.</td>
        </tr>
        <tr>
            <td align="center">s</td>
            <td>writes a character string.</td>
        </tr>
        <tr>
            <td align="center">p</td>
            <td>writes an implementation-defined character sequence defining a pointer address.</td>
        </tr>
        <tr>
            <td align="center">d or i</td>
            <td>writes a signed integer to decimal representation.</td>
        </tr>
        <tr>
            <td align="center">u</td>
            <td>writes an unsigned integer to decimal representation.</td>
        </tr>
        <tr>
            <td align="center">x or X</td>
            <td>writes an unsigned integer to hexadecimal representation.</td>
        </tr>
    </tbody>
</table>

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
