# Extensions

In addition to C11, several [GNU extensions] are implemented and more
may be implemented in the future.

## Implemented

### `__typeof__`

`__typeof__(E)` is a type specifier for the type of expression `E`. Arrays
and function designator expressions do not decay into pointers, just
like when used with `sizeof`.

### Built-in functions and types

- **`__builtin_alloca`**: Allocate memory on the stack.
- **`__builtin_constant_p`**: Test whether the argument is a constant expression.
- **`__builtin_inff`**: `float` positive infinity value.
- **`__builtin_nanf`**: `float` quiet NaN value.
- **[`__builtin_offsetof`]**: Return the offset of a member in a struct or union.
- **`__builtin_types_compatible_p`**: Test whether the two types are compatible.
- **`__builtin_va_arg`**: Built-in suitable for implementing the `va_arg` macro.
- **`__builtin_va_copy`**: Built-in suitible for implementing the `va_copy` macro.
- **`__builtin_va_end`**: Built-in suitible for implementing the `va_end` macro.
- **`__builtin_va_list`**: Built-in suitable for implementing the `va_list` type.
- **`__builtin_va_start`**: Built-in suitable for implementing the `va_start` macro.

## Missing

### Statement expressions

In GNU C, you may use a compound statement as expressions when they are
enclosed in parentheses. The last statement in the compound statement
must be an expression statement, whose value is used as the result of
the statement expression.

### Empty declarations

GNU C allows empty top-level declarations (i.e. `;`).

### Empty initializer list

GNU C allows empty initializer lists when initializing an object,
for example

```c
struct {
	int a, b;
} s = {};
```

This behaves exactly the same as `{0}`.

### Missing operand in conditional expression

GNU C allows you to omit the second operand in conditional expressions,
in which case the first operand is used. So `E1 ? : E2` behaves the same
as `E1 ? E1 : E2`, except that `E1` is evaluated only once.

[GNU extensions]: https://gcc.gnu.org/onlinedocs/gcc/C-Extensions.html
[`__builtin_offsetof`]: https://gcc.gnu.org/onlinedocs/gcc/Offsetof.html
