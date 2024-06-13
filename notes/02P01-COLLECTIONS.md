# Collections

Collections is a type of variable which can be used to multiple data. It is commonly used to group data into structures.

Types of collections:

1. List: Ordered collection of items
2. Sets: Unique, unordered collections
3. Maps: Key, value pairs that are unique and map to only one value


## List

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

### Operations on a List

`val colors: List<String> = listOf("red", "blue", "aoi", "sora")`

1. Accessing an item:

`println("Item of index 0 is: ${colors[0]}")`
// Item of index 0 is red

`println("You can also use .first() to get the first item in a list: ${colors.first()}")`
// You can also use .first() to get the first item in a list: red

`println("To access the last element, use .last(): ${colors.last()}")`
// To access the last element, use .last(): sora

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
`colorsrw.add("mauve")`

* `.remove()` to remove an element
`colorsrw.remove("sora")`


## Set

1. `setOf()`: Read-only set (`Set`)
2. `mutableSetOf()`: Mutable set (`MutableSet`)

```
val readOnlyFruit = setOf("apple", "banana", "cherry")

val fruit: MutableSet<String> = mutableSetOf("apple", "banana", "banana", "tomato")

println(fruit)
// ["apple", "banana", "cherry"]
// Only one banana item is present because set contains only unique elements
```

* Casting can be done to sets too

```
val fruits: MutableSet<String> = mutableSetOf("tomato", "apple", "cherry")
val lockedFruits: Set<String> = fruits
```

* Since sets are unordered, items cannot be accessed using an index

### Operations on a set

`val fruits: Set<String> = setOf("apple", "cherry", "tomato")`

1. `.count()` to get the number of items in a set

`println("Number of elements in set fruits: ${fruits.count()}")`

2. `in` operator to check if item is in set

`println("banana" in fruits)`
// false

3. `.add()` and `.remove()` to add or remove elements from a set

```
fruit.add("dragonfruit")
fruit.remove("cherry")
println(fruits)
// ["tomato", "apple", "dragonfruit"]
```


## Map

Maps can be used to store key-value pairs.
Items in a map must be accessed by referencing the key.

1. `mapOf()`: Read-only map (`Map`)
2. 'mutableMapOf()': Mutable map (`MutableMap`)

```
val readOnlyMenu = mapOf("apple" to 100, "banana" to 200, "orange" to 175)

val menu: MutableMap<String, Int> = readOnlyMenu
println(menu)
// {apple=100, banana=200, orange=175}
```

To explicitly declare the type of a map, use maptype followed by the type of both the variables seperated by a comma (,) in the angle brackets <>

`val menu: Map<String, Int> = mapof("apple" to 140, "pineapple" to 125)`

* Casting can be used to maps too

### Operation in a map

`val menu: Map<String, Int> = mapof("apple" to 140, "pineapple" to 125)`

1. Access a value (using its key):

Use indexed access operator `[]`
`println("The value of apple is: ${menu["apple"]}")`

2. `.count()` to get number of items:

`println("Number of items in menu is: ${menu.count()}")`

3. `.put()` and `.remove()` to modify items in a map:

```
val freeMenu: MutableMap<String, Int> = menu

freeMenu.put("kiwi", 300)
freeMenu.remove("apple")

println(freeMenu)
// {"pineapple"=125, "kiwi"=300}
```

4. `.containsKey()` to check if key is included in map:

```println(menu.containsKey("pineapple"))
// true
```

5. `.keys` and `.values` to obtain keys or values as a list

```
println(menu.keys)
// [apple, pineapple]

println(menu.values)
// [140, 125]
```

6. `in` operator to check if key or value in map:

_Fundamentally, it is an operation on a list_

```
println("orange" in menu.keys)
// false

println(140 in menu.values)
// true
```
