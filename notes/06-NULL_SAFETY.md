# Null Safety

Null safety is a system that detect potential problems with null values during compile time, rather than the runtime.

Null safety allows to:

* Explicitly declare when `null` values are allowed
* Check for `null` values
* Use safe calls to property and functions that may contain `null` values
* decalre actions to take if `null` values are detected

## Nullable types

By default, a type is not allowed to take null values.
To declare a nullable type, `?` is added after type declaration.

```
fun main() {
    var neverull: String = "This cannot be null"

    neverNull = null
    // Throws a compiler error

    var nullable: String? = "This can be a null value"
    
    nullable = null
}
```

## Check for null values

```
fun describeString(maybeString: String?): String {
    if (maybeString != null && maybeString.length > 0) {
        return "String of length ${maybeString.length}"
    }
    else {
        return "Empty/null string"
    }
}
```

## Safe calls

A safe call is used to return the value or null, if one of the access properies is null.

```
fun lengthString(maybeString: String?): Int? = maybeString?.length

fun main() {
    val nullString: String? = null
    println(lengthString(nullstring))
}
// null
```

In this example, the function `lengthString()` uses a safe call to return either the length of the string or null

---
#### Safe calls chaining

Safe calls can be chained so that if any one of the property contains a null value, then null is returned without an error being thrown.
`var1.var2?.var3?.var4?.var5`

---

* A safe call operator can be used to safely call a member function


### Elvis operator

A default value can be returned if a null value is detected by using an Elvis operator `?:`
On the LHS of the elvis operator, write the null value check, and on the RHS, put the default value to be retuened if a `null` value is detected

```
fun main() {
    val nullString: String? = null
    println(nullString?.length ?: 0)
}
// 0
```

In this example, the value of variable `nullString` is null, hence 0 is returned, which is the value defined to be returned.
