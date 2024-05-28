# Control Flow

## Conditional Expression

Conditional expression is a piece of code used to make a decision based on a conditions.

1. `If`
2. `When`

### If

__Syntax:__
```
if (condition) {
    fun1()
}
else {
    fun2()
}
```

* Single line if conditions are possible
Curly braces can be ignored if there is only one line of code per action

`println(if (condition) fun1() else fun2())`

### When

When is use where there is a conditional expression with multiple branches.
It can be used either as a statement or an expression.

__Syntax:__

* Place the condition in parentheses `()` and actions in curly braces `{}`
* Use `->` in each branch to seperate each condition from an action.

```
var obj == "Hello World!"

When (obj) {
    
    "1" -> println("One")
    "Hello" -> println("Hi")
    "Hello World!" -> println("Greetings")
    else -> println("Unknown")
}
// Greetings
```

* Branches are checked sequentially until one of them is satisfied. And only one branch is executed.

Example 2:
```
val obj = "Ohayo"

val result = When (obj) {
    
    "Good Morning" -> "Greetings"
    "Ohayo" -> "Konnichiwa"
    else -> "Speechless"
}

println(result)

//Konnichiwa
```

* When can also be used as an expression:
Else branch is mandatory if used as an expression, unless the compiler can detect that all possible cases are covered by branch conditions.

```
val temp = 18

val feels = When (temp) {

    temp < 0 -> "freezing"
    temp < 10 -> "very cold"
    temp < 20 -> "cold"
    temp < 30 -> "medium"
    temp < 40 -> "hot"
    else -> "very hot"
}

println(feels)
// cold
```


## Ranges

Ranges are used to generate a sequential set of numbers, probably to use with loops.

* `..` operator is used to create a range.
`a..b` is equivalent to a, a+1, a+2, ..., b-2, b-1, b.
Example: `3..8` is 3, 4, 5, 6, 7, 8

* To declare a range excluding the end value, use `..<` operator.
Example: `2..<5` is 2, 3, 4

* To declare a range in reverse order, use `downTo`
Example: `4 downTo 1` is 4, 3, 2, 1

* To declare a range with custom increment steps, use `step <value>`
Example: `1..9 step 2` is 1, 3, 5, 7, 9

_It is also possible to use range with `Char` ranges_

`'a'..'g'` is 'a', 'b', 'c', 'd', 'e', 'f', 'g'
`'z' downTo 's' step 2` is 'z', 'x', 'v', 't'


## Loops

1. For loop
2. While loop

### `For` loop

```
for (number in 1..5) {
    print(number)
}
// 12345
```

```
val cakes: List<String> = listOf("carrot", "cheese", "strawberry")

for (cake in cakes) {
    println("It's a ${cake} cake")
}

// It's a carrot cake
// It's a cheese cake
// It's a strawberry cake
```

### `While` loop

1. `while` is use to execute a code block when the conditional expression is true.
2. 'do-while' executes the code block first and then continues to if conditional expession is true.

#### While loop

```
while (condition) {
    function1()
}
```

#### Do-While

```
do {
    function1()
} while (condition)
```
