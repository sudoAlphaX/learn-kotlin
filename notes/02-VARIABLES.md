### Variables

There are 2 types of variable declaration

1. `val`: read-only variable
2. `var`: mutable (editable) variable

To assign a value to a variable, use assignment operator `=`.

```
val a = 8
var b = 7

//  Change the value of b
b = 8
```

#### String Templates

You can insert a variable into a string using curly braces `{var}`.

```
val name = "John"

print("The name is {name}")
// Output: The name is John
```

### Variable Types

Every Kotlin variable has a type. If not specified explicitly, Kotlin will automatically infer a variable type.

Example:
```
var customers = 10
// Kotlin has inferred the variable customers to be an int
// Hence, you can perform mathematical operations with the variable

customers = 8
customers += 2
customers -= 6
customers *= 5
```

__Basic Types of Variables__

1. Integers: Byte, Short, Int, Long
2. Unsigned integer: UByte, UShort, UInt, ULong
3. Float: Floar, Double
4. Bool: Boolean
5. Characters: Char
6. Strings: String

```
val a = 3
// Variable a inferred as int

val b: Int = 4
// Variable b explicitly set as int

val c: Int
// Empty variable declared as an int
```
