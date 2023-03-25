# Scala Basics

## Simple Scala 

__Expression__

```scala
println("hello"+"scala")
// value
val x = 1 + 1
val x: Int = 1 + 1
// variables
var x: Float = 1 + 1
x = 3 // var can be re-assigned
// block
println({
    var x:Int = 5 + 5
        x = x * x
        println(x)
        x * x
}) // it prints out 100 first and then x*x 10,000
```

__Functions__
Functions have parameters and take arguments.
```scala
(x: Int) => x+1 // anonymous function
val oneMore = (x:Int) => x + 1 // var okay too. Must include parameter type
```

__Methods__
Methods are defined by `def` (like python). `def` is followed by a `name`, `parameter list`, `return type` & a `body`.
```scala
def multiply (a:Int, b:Int):Int = a * b // println(multiply(3,4))
def multiMultiply(a: Int, b: Int)(c: Int)(d: Int): Int
// scala> println(multiMultiply(2,2)(3)(4))
// 48
```

| Scala 2 | Scala 3 |
|  :---: | :---: |
| use `{}` after `=` for multiline expression | use indentation after `=` |


> * _Python_ just uses `:` before `body`. types are ==lower cases== but ==True, False==
> * _Golang_ does not use `:` for parameter notation and types are ==lower cases== `int`, `bool`, `string`, etc. __Example:__ `func add(a, b int, c float32)`

```scala
def getString(a: Float):String={
    var number = a * a
    number.toString // automatically return last
}
// scala> getString(1.2)
// val res0: String = 1.44
```

__Classse__
`class` keyword followed by its `name` and `constructor parameters`.

```scala
// scala2 just remove {} in 3 and add :
class Messenger(begin:String, end:String) { 
    def greet(info: String): Unit =
    println(begin + info + end)
}
val messenger = new Messenger("Hello, ", "!") // scala 2
val messenger = Messenger("Hello, ", "!") // scala 3
```

__Case Classes__
`Good for Pattern Matching`

__Objects__

__Traits__