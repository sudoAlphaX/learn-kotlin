# Kotlin Notes

## Basic Syntax
```
fun main() {
    println("Your stuff goes here")
    //  This is a comment
}
```
* `fun` is used to declare a function
* `main()` is a function where the program starts from

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

## Collections

Collections is a type of variable which can be used to multiple data. It is commonly used to group data into structures.

Types of collections:

1. List: Ordered collection of items
2. Sets: Unique, unordered collections
3. Maps: Key, value pairs that are unique and map to only one value


### List

There are two types of lists:
1. `listOf()`: Read only list (`List`)
2. `mutableListOf()`: Mutable list (`MutableList`)

* To declare the type of list, use angled brackers <> after list declaration

```
val readOnlyShapes = listOf("triangle", "square", "circle")
// readOnlyShapes is a read only list of 3 elements

val shapes = mutableListOf("rectangle", "hexagon")
// shapes is a mutable list of 2 elements

val decShapes: MutableList<String> = mutableListOf("circle", "septagon")
// decShapes is a mutable list with explicit string declaration
```

__Casting__

Casting is a way to obtain read-only lists from a mutable list toprevent unwanted modifications.

```
val animals = MutableList<String> = mutableListOf("tiger", "zebra", "rabbit")
val animalsLocked: List<String> = animals
//animalsLocked is a read-only list of animals
```

#### Operations on a List

`val colors: List<String> = listOf("red", "blue", "aoi", "sora")`

1. Accessing an item:

`println("Item of index 0 is: ${colors[0]}")`
// Item of index 0 is red

`println("You can also use .first() to get the first item in a list: ${colors.first()}")`
// You can also use .first() to get the first item in a list: red

`println("To access the last element, use .last(): ${colors.last()}")`
// To aaccess the last element, use .last(): sora

2. Number of items:

`.count()`

`println("Number of items in colors is: ${colors.count()})`
// Number of items in colors is: 4

3. Check if an item is in a list:

`in` operator
returns boolean

println("pink" in colors)
// false

4. Add and remove items from a (mutable) list:

`val colorsrw: MutableList<String> = colors`

* `.add()` to add an element
`colorsrw.all("mauve")`

* `.remove() to remove an element`
`colorsrw.remove("sora")`
