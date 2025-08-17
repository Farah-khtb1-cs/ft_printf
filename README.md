# ft_printf

**ft_printf** is a comprehensive implementation of the famous `printf()` function from the C standard library, designed as part of the 42 School curriculum. This project introduces variadic functions in C and teaches format string parsing, type conversion, and advanced C programming concepts.

## 🚀 Features

- **Variadic Functions**: Handle variable number of arguments using `va_start`, `va_arg`, `va_end`
- **Format Specifiers**: Support for `%c`, `%s`, `%d`, `%i`, `%u`, `%x`, `%X`, `%p`, `%%`
- **Return Value**: Returns number of characters printed (like original printf)
- **Memory Safe**: Proper memory management and error handling
- **Library Integration**: Compatible with libft and other 42 projects

## 📋 Requirements

- **Language**: C
- **Compilation**: `-Wall -Wextra -Werror`
- **Output**: `libftprintf.a` static library
- **Allowed Functions**: `malloc`, `free`, `write`, variadic function macros

## 📁 Project Structure

```
ft_printf/
├── Makefile
├── ft_printf.h
├── src/
│   ├── ft_printf.c
│   ├── ft_print_char.c
│   ├── ft_print_string.c
│   ├── ft_print_number.c
│   ├── ft_print_hex.c
│   └── ft_print_pointer.c
└── libftprintf.a
```

## 🎯 Supported Format Specifiers

| Specifier | Type | Description |
|-----------|------|-------------|
| `%c` | Character | Single character |
| `%s` | String | Null-terminated string |
| `%d` / `%i` | Integer | Signed decimal integer |
| `%u` | Unsigned | Unsigned decimal integer |
| `%x` / `%X` | Hex | Hexadecimal (lower/uppercase) |
| `%p` | Pointer | Pointer address in hex |
| `%%` | Literal | Percent sign |

## 🔧 Usage

```c
#include "ft_printf.h"

int main(void)
{
    ft_printf("Hello %s!\n", "World");
    ft_printf("Number: %d, Hex: %x\n", 42, 255);
    
    int x = 42;
    ft_printf("Address: %p\n", &x);
    
    return (0);
}
```

### Compilation
```bash
make
gcc -Wall -Wextra -Werror main.c -L. -lftprintf -o program
```

## 🎁 Bonus Features

- **Flags**: `-`, `0`, `#`, `+`, ` ` (space)
- **Field Width**: Minimum character width
- **Precision**: `.` precision specifier

```c
ft_printf("%-10d\n", 42);    // Left-aligned
ft_printf("%010d\n", 42);    // Zero-padded
ft_printf("%.5d\n", 42);     // Precision
```

## 🧪 Testing

```c
// Basic tests
ft_printf("%d %s %c\n", 42, "test", 'A');
ft_printf("%x %X %p\n", 255, 255, &var);

// Edge cases
ft_printf("%s\n", NULL);     // Handle NULL
ft_printf("%%\n");           // Literal %
```

## 🏗️ Implementation Notes

- Uses `write()` system call for output
- Handles edge cases (NULL pointers, INT_MIN/MAX)
- Modular design with separate handlers for each format
- No internal buffering (direct output)

## 📝 Learning Outcomes

- Mastery of variadic functions in C
- Understanding of format string processing
- Advanced memory management techniques
- Complex C project architecture
- Number base conversion algorithms

---

Part of the 42 School curriculum - a deep dive into one of C's most complex and essential functions.
