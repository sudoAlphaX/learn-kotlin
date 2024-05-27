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
