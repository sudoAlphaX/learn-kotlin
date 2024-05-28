# Lambda Expressions

A lambda expression is used to write concise code for functions

For example:

```
fun ucString(str: String): String {
    return str.uppercase()
}

fun main() {
    println(uppercaseString("hello"))
}
// HELLO
```

Can be written as:

```
fun main() {
    println({ str: String -> str.uppercase() }("hello"))
}
// HELLO
```

## Syntax

1. Lambda expressions are written withing curly braces `{}`
2. The parameters are followed by an `->`
3. The function body is after the `->`

* In a lambda function without parametrs `->` can be ignored.


## Use of Lambda expressions

1. Assign a lambda to a variable to invoke it later.
2. Pass a lambda expression as a param to another function.
3. Return a lambda expression from a function.
4. Invoke a lambda expression on its own.


### Assign a lambda to a variable

```
fun main() {
    val ucStr = { str: String -> str.uppercase() }
    println(ucStr("hello, world!"))
}
// HELLO, WORLD!
```

### Pass to another function

Example: Using the `.filter()` function which accepts a lambda expression:
* { x -> x > 0 } takes each element of the list and returns only those that are positive
* { x -> x < 0 } takes each element of the list and returns only those that are negative

```
val numbers = -5..5
val positives = numbers.filter { x -> x < 0 }
val negatives = numbers.filter { x -> x > 0 }
```

* If a lambda expression is the only function parameter, `()` can be dropped. It is called trailing lambda.
