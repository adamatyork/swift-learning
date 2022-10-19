# <i>The thrills and spills of nulls and nils - </br></i> Handling 'nothingness' in C# and Swift.

## In C#...
When we want to tell the compiler that a reference variable has no value, we simply assign it null! </br> 

```
MyClass myClass = null
```

What's null? It's nothing. It's a pointer to nothing, or a <i>void pointer</i>. </br>
We use it to say <i>'This reference variable points to nothing but I've still assigned it, look!'</i>

...and what about a value type? Value types can't be null. They can't point to <i>nothing</i>, because they are not pointers. <i> Or can they? </i>

C# provides `Nullable<T>`, a wrapper for types, both reference and value, that can either hold `null` or a value. </br>
Syntactic sugar for declaring a Nullable type is `'?'`

Eg. 
```
int? myNumber = null
```
## Why?
This means we can allow for value types to have <b>no value</b>, which allows us to do comparisons such as:
```
if(myNumber == null) { // do something }
``` 
which, previously, would throw an error.

It also means we can be more efficient in situations where we want to declare a variable to assign to later, but with no initial value.
Instead of assigning it an arbitrary value that will have to be garbage collected (if you're lucky), we can simply assign it `null`. </br></br>

## So what about in Swift?

</br>
Swift provides a new type specially for handling null values in much the same way as C#.

<i>but...</i> Swift has no concept of null. Instead, we use `nil`.

The `Optional<Wrapped>` type provides similar functionality to C#'s `Nullable<T>`. An optional can either hold a wrapped value, or `nil`.


The syntax for declaring an optional is like this:
```
var myString: Optional<String>
```
but this can be sweetened with syntactic sugar to this:
```
var myString: String?
```

Oh yeah, by the way, Strings are value types in Swift.

We can 'unwrap' an Optional a couple of ways.

### <b>Conditionally...</b>
```
print(wrappedOptional?)
```
which tells the compiler to ignore the current statement if the optional is `nil`.

### <b><i>Un</i>conditionally...</b>
```
print(wrappedOptional!)
```
which tells the compiler that we're certain the value is not `nil`, so process the statement either way.
If the value <i>is</i> `nil`, you dun gon' goofed, and you'll get runtime errors.


We can also use the good old `null coalescing operator` on value types when using Optionals.

```
var example = myString ?? "Hello, World!"
```
</br>
<b>TO BE CONTINUED...</B>





