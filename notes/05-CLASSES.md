# Classes

Kotlin supports object-oriented proramming with classes and objects.
Object are useful for storaing data, and classes are used to dealre a set of characteristics for an object.

The `class` keyword is used to declare a class

`class Customer`

## Properties

Characteristics of a class's object can be declared in properties.
Properties can be declared:

1. Within parentheses `()` after a class name:

`class Contact(val id: Int, var email: String)`

2. WIthing class body defined by curly braces `{}`:

```
class Contact(val id: Int, var email: String) {
    val category: String = ""
}
```

* It is recommended to declare properties as read-only (`val`), unless they need to be changed after an instance of a class has been created.

_The content contained within parenthesis `()` is called **class header**._

Class properties can have default values:

```
class Contact(val id: Int, var email: String = "example@gmail.com") {
    cal category: String = "work"
}
```

## Create class instance

To create an object from a class, a class instance is declared using a __constructor_.
By default, Kotlin automatically creates a construtor with the parameters declared in the class header.

```
class Contact(val id: Int, var email: String)

fun main() {
    val contact = Contact(1, foo@gmail.com)
}
```

In this example:
* `Contact` is a class
* `contact` is an instace of the `Contact` class
* `id` and `email` are properties of the `Contact` class
* `id` and `email` are used with the default constructor to create `contact` instance

_Kotlin classes can have many constuctor, including custo ones_

## Access properties

```
class Contact(val id: Int, var email: String)

fun main() {
    val contact = Contact(1, foo@gmail.com)

    println(contact.email)
    // foo@gmail.com

    contact.email = "bar@gmail.com"
    // New value is set

    // contact.id = 2 will not work because id is not a mutable variable
}
```

* String templates (`$`) can be used to access a property

`println("The email address is: ${contact.email}")`

## Member functions

Member functions must be declared within the class bodu. A member function can be called by writing the function name after the instace name seperated by a period `.`

```
class Contact(val id: Int, var email: String) {
    fun printId() {
        println(id)
    }
}

fun main() {
    val contact = Contact(1, "bob@gmail.com")
    contact.printId()
}
// 1
```

# Data Classes

Data classes are a type of class which are useful in storing and retrieving data.
Data classes have additional member functions which are helpful in viewing and manipulating the data.

`data class User(val name: String, val id: Int)`

## Member functions in data class

1. `toString()`:
Used to print a readable string of class instance and its properties.

2. `.equals()` or `==`:
Compares instances of a class.

3. `.copy()`:
Crates a class instance by copying another instance, but can be set to have some different properties.

### `.toString()`

`print()` or `println()` automatically uses the `toString()` function when used with a data class so output is easy to read.
Particularly useful for debugging and reading logs.

### `==`

Compares the data class intances

```
class User(val name: String, val id: Int)

val user = User('Alex', 1)
val user1 = User('Alex', 1)
val user2 = User('Bob', 2)

println(user == user1)
// true

println(user == user2)
// false
```

### `.copy()`

It is used to create a copy of the data class and change some peoperties.

```
class User(val name: String, val id: Int)

val user = User('Alex', 1)
val user1 = User('Alex', 1)
val user2 = User('Bob', 2)

println(user.copy("Max"))
// User(name=Max, id=1)

println(user2.copy(id=3))

```
