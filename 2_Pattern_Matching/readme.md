# Pattern Matching
## Basic Pattern Matching
Pattern matching is a mechanism for checking a value against a pattern.
Use `match` keywords and `case` clause.

```scala
import scala.utl.Random
val x = Random.nextDouble() * 10
x match {
    case x if (x <= 3) => "small"
    case x if (x >3 && x <=7 ) => "medium"
    case _ => "large"
}
// scala 3
def tryMatch (x:Double):String = x match
    case x if x <= 3 => "small"
    case x if x >3 && x <=7 => "medium"
    case _ => "large"
```

## Matcing on Case Classes

### `sealed` Types
`sealed` provides ==extra sefety== -> The compiler checks if `cases` of a `match` is *exhaustive*.

```scala
sealed trait CanFly

case class Bird(name: String, speed: Double) extends CanFly
case class Plane(airline: String, speed: Double) extends CanFly
case class Batman(group: String, speed: Float) extends CanFly
// incomplete code but self-explanatory
def showFlyingObjects(flyingObject :CanFly): String =
    flyingObject match
        case Bird(name, _) => "Bye"
```