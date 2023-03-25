# Scala Basics

## Simple Scala 

__main__
```scala
// scala 2
object Main {
    def main(args: Array[String]): Unit = {
        println("hi!")
    }
}
Main.main(args=Array("1"))
// scala 3
@main def hello()=println("bye")
```

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
`Good for Pattern Matching` -> Instances of case classes are ==immutable==. They are therefore compared by values (_rather than by reference like standard classes_)

`case class Location(a: Float, b: Float)` no `new` needed

```scala
val loc1 = Location(1.1, 1.2)
val loc2 = Location(1.1, 1.2)
val loc3 = Location(3.11, 2.01)
// scala3
if loc1 == loc2 then
    println(s"$loc1 and $loc2 are the same")
else
    println(s"$loc2 and $loc1 are not the same")
// scala 2
if (loc1 == loc3){
    println(s"$loc1 is the same as $loc3")
} else {
    println(s"$loc3 is not the same as $loc1")
}
```

__Objects__
Objects are single instances of their own definitions. ==Singletons of their own classes==.
```scala
object SomeFactory{
    private var somenum:Int = 0
    def create(): Int = {
        somenum += 1
        somenum
    }
}
var newSome = SomeFactory.create()
```

__Traits__
==Traits are abstract data types containing certain fields and methods.== Its like a `protocol`.

```scala
// scala 2
trait CanFly {
  def Fly(sound: String): Unit =
    println("Fly w/ the sound " + sound + "!")
}
// scala 3
trait CanFly:
    def Fly(sound: String): Unit =
        println("Fly w/ the sound " + sound + "!")
```
Then create `class` with `extends` keyword and `override` existing functions.
```scala
class Plane extends CanFly

```

## More Scala

### Arguments and Names
```scala
def showLocation(x: Float, y: Float): Unit = 
    println(s"the location has x=$x, y=$y.")
// scala> showLocation(1,2)
// the location has x=1.0, y=2.0.
// scala> showLocation(1,y=2)
// the location has x=1.0, y=2.0.
```

### Default Parameter Values
Something like `(a:Int=0, b:String="bye")`

### Control Structures
- Control Structure
  - if / then / else
    - `scala2` -> `if (){ } else if (){ } else { }`
    - `scala3` -> `if then else if then else` it has a *unique* `end if`
  - for loops
    - `scala2` -> `for () {   }`
    - `scala3` -> `for do` w/ indentation
  - while loops
    - `scala2` -> `while () {   }`
    - `scala3` -> `while do` w/ indentation
  - try / catch / finally 
- Unique Constructs
  - `for` expressions / comprehensions
  - `match` expressions
    - match with `case`