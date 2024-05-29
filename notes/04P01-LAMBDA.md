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


### Return lambda expression from a function

---
#### Function Types

It is recommended to specify the function types.

##### Function type syntax
1. Each parameter type is written within parenthesis `()` and seperated by comma `,`
2. The return type is written after `->`

`val var1: (inputType) -> returnType = { inputVar -> fun1() }`

* If the lambda expression has no parameters, then parenthesis `()` is left empty.

`val var1: () -> Unit = { fun1() }`

---

A lambda expression can be returned from a function. A functio type has to be declared for that expression.

```
fun toSeconds(time: String): (Int) -> Int = when (time) {
    "hour" -> { value -> value * 60 * 60 }
    "minute" -> { value -> value * 60 }
    "second" -> { value -> value }
    else -> { value -> value }
}

fun main() {
    val timesInMinutes = listOf(2, 10, 15, 1)
    val min2sec = toSeconds("minute")
    val timeInSec = timesInMinutes.ma(min2sec).sum()
    println("Total time is $timeInSec secs")
}
// Total time is 1680 secs
```


### Invoke Seperately

To invoke a lambda function on their on, add parenthesis `()` after curly braces `{}`, with the parameters.

`println({ text -> text.uppercase() }("hello"))`

---
### Trailing lambdas

If the lambda expression is the only function parameter, the function parenthesis `()` can be dropped.
If the lambda expression is passed as the last expression of a function, then the expression can be written outside the function parenthesis `()`.
This syntax is called trailing lambda.

`println(listOf(1, 2, 3).fold(0, { x, item -> x + item }))`

is equivalent to:

`println(listOf(1, 2, 3).fold() { x, item -> x + item })`

---
