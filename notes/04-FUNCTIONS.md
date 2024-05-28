# Functions

Functions can be declared using the keyword `fun`.

```
fun functionA() {
    return println("Hello, World!")
}

fun main() {
    hello()
}
// Hello, World!
```

__Function requirements:__

1. Function parameters are inside parentheses `()`
2. Each parameter must have a type, and multiple parameters are seperated by a comma `,`
3. The return type is written after the functions parenthesis `()`, seperated by a colon `:`
4. Body of a function in curly braces `{}`
5. `return` keyword used to exit or return something from a function (can be omitted)


```
fun sum(x: Int, y: Int): Int {
    return (x+y)
}

fun main() {
    println(sum(1, 2))
}
// 3
```

In the above snippet:
1. `x: Int` and `y: Int` is declaring types for the parameter `x` and `y`.
2. `fun name(): Int` is declaring return type as `Int`.

### Named Arguments

```
fun division(x: Int, y: Int): Int {
    println($x divided by $y is: ${x/y})
}

fun main() {
    division(x=10, y=2)
}
// 5
```

String templates (`$`) can be used with parameter.

### Parameters with default values

```
fun defFunction(x: Int = 25, y: int = 5) {
    return (x/y)
}

fun main() {
    println(defFunction())
}
// 5
```

* Functions can be decalred without a return value. The return type is called `Unit` and the return value is `Unit`.

### Single Expression functions

```
fun sum(x: Int, y: Int): Int = x + y

fun main() {
    println(sum(3, 4))
}
// 7
```
