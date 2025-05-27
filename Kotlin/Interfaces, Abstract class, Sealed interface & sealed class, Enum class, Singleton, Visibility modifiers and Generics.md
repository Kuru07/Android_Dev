---
share: true
---
## Interfaces
* To use a single function to allow multiple data class types for example
* To implement all things from a interface use ==ctrl + i==
* Use getter and setter functions to read and set the value
* Can have functions we want to override it
```kotlin
import org.w3c.dom.css.Rect  
import kotlin.math.PI  
import kotlin.math.sqrt  
  
fun main()  
{  
  
    val rect1 = Rectangle(  
        widrh = 5f,  
        height = 7f  
    )  
  
    val rect2 = rect1.copy(  
        height = 10f  
    )  
  
    val circle = Circle(radius = 5f)  
    println(sumAreas(rect1,circle))  
  
    println(rect2)  
}  
  
fun sumAreas(vararg shape: Shape): Double{  
    return shape.sumOf {  
        currentShape -> currentShape.area.toDouble()  
    }  
}  
  
interface Shape {  
    val area: Float  
    val circumference: Float  
}  
  
data class Rectangle(val widrh: Float, val height: Float) : Shape  
{  
    val diagonal = sqrt(widrh * height + height * height)  
  
    override val area = widrh * height  
  
    override val circumference: Float  
        get() = 2 * widrh + 2 * height  
}  
  
data class Circle(val radius: Float): Shape{  
    override val area = radius * radius * PI.toFloat()  
  
    override val circumference = 2 * radius * PI.toFloat()  
}
```
## Abstract Classes
* We cant create instances of abstract classes directly
* We can only create instances for its children which is inheritance
* We can use *Open* keyword but want to providde open default value too
```kotlin
import org.w3c.dom.css.Rect  
import kotlin.math.PI  
import kotlin.math.sqrt  
  
fun main()  
{  
  
    val rect1 = Rectangle(  
        widrh = 5f,  
        height = 7f  
    )  
  
    val rect2 = rect1.copy(  
        height = 10f  
    )  
  
    val circle = Circle(radius = 5f)  
    println(sumAreas(rect1,circle))  
  
    println(rect2)  
}  
  
fun sumAreas(vararg shape: Shape): Double{  
    return shape.sumOf {  
        currentShape -> currentShape.area.toDouble()  
    }  
}  
  
abstract class Shape{  
    abstract val area: Float  
    abstract val circumference: Float  
}  
  
  
data class Rectangle(val widrh: Float, val height: Float) : Shape()  
{  
    val diagonal = sqrt(widrh * height + height * height)  
  
    override val area = widrh * height  
  
    override val circumference: Float  
        get() = 2 * widrh + 2 * height  
}  
  
data class Circle(val radius: Float): Shape(){  
    override val area = radius * radius * PI.toFloat()  
  
    override val circumference = 2 * radius * PI.toFloat()  
}
```

## Sealed Interface or Class
* A sealed interface can be only implemented in current module
```kotlin
import org.w3c.dom.css.Rect  
import kotlin.math.PI  
import kotlin.math.sqrt  
  
fun main() {  
  
    val rect1 = Rectangle(  
        widrh = 5f,  
        height = 7f  
    )  
    val rect2 = rect1.copy(  
        height = 10f  
    )  
  
    val circle = Circle(radius = 5f)  
    println(sumAreas(rect1, circle))  
  
    printShapes(rect1,circle)  
}  
  
sealed interface Shape {  
    val area: Float  
    val circumference: Float  
}  
  
fun printShapes(vararg shapes: Shape){  
    for(shape in shapes){  
        val output = when(shape){  
            is Circle -> "Thats a circle"  
            is Rectangle -> "Thats a secret"  
        }  
        println(output)  
    }  
}  
  
fun sumAreas(vararg shape: Shape): Double {  
    return shape.sumOf { currentShape ->  
        currentShape.area.toDouble()  
    }  
}  
  
  
data class Rectangle(val widrh: Float, val height: Float) : Shape {  
    val diagonal = sqrt(widrh * height + height * height)  
  
    override val area = widrh * height  
  
    override val circumference: Float  
        get() = 2 * widrh + 2 * height  
}  
  
data class Circle(val radius: Float) : Shape {  
    override val area = radius * radius * PI.toFloat()  
  
    override val circumference = 2 * radius * PI.toFloat()  
}
```

## Enum Class
* Enumerate a set of related objects
* Used in dropdown in android dev
```kotlin
import org.w3c.dom.css.Rect  
import kotlin.math.PI  
import kotlin.math.sqrt  
  
fun main() {  
  
    val rect1 = Rectangle(  
        widrh = 5f,  
        height = 7f  
    )  
    val rect2 = rect1.copy(  
        height = 10f  
    )  
  
    val circle = Circle(radius = 5f)  
    println(sumAreas(rect1, circle))  
  
  
    for(country in Country.entries){  
        println(country.code)  
    }  
}  
  
enum class Country(val code: String){  
    GERMANY("DE") , FRANCE("FR") , USA("US")  
}  
  
fun greetMe(country: Country):String  
{  
    return when(country){  
        Country.GERMANY -> "Guten Tag!"  
        Country.FRANCE -> "Bonjour!"  
        Country.USA -> "Hello!"  
    }  
}  
sealed interface Shape {  
    val area: Float  
    val circumference: Float  
}  
  
fun printShapes(vararg shapes: Shape){  
    for(shape in shapes){  
        val output = when(shape){  
            is Circle -> "Thats a circle"  
            is Rectangle -> "Thats a secret"  
        }  
        println(output)  
    }  
}  
  
fun sumAreas(vararg shape: Shape): Double {  
    return shape.sumOf { currentShape ->  
        currentShape.area.toDouble()  
    }  
}  
  
  
data class Rectangle(val widrh: Float, val height: Float) : Shape {  
    val diagonal = sqrt(widrh * height + height * height)  
  
    override val area = widrh * height  
  
    override val circumference: Float  
        get() = 2 * widrh + 2 * height  
}  
  
data class Circle(val radius: Float) : Shape {  
    override val area = radius * radius * PI.toFloat()  
  
    override val circumference = 2 * radius * PI.toFloat()  
}
```

## Singleton
* Can have only a single instance
## Visibility modifiers
* Modifiers are ==private , public & protected, internal  ==
## Generics

```kotlin
  
fun main(){  
    val favouriteNumbers = intArrayOf(1,2,3,69)  
    val helloworld = " HEllp world"  
  
    val evenNumber = favouriteNumbers.filter { it % 2== 0}  
    val lettersOnly = helloworld.filter { it.isLetter() }  
  
    val stringsList = listOf(  
        "Hello World!",  
        "Bye Bye",  
        "Madhumidha"  
    )  
    val integers = listOf(1,2,3,4,5)  
  
    val filteredStrings = stringsList.myFilter {  
        currentString -> currentString.length > 10  
    }  
  
    val filteredNumbers = integers.myFilter { it < 3 }  
  
    println(filteredStrings)  
    println(filteredNumbers)  
  
    val result = makeNetworkcalls()  
}  
  
fun <T> List<T>.myFilter(predicate: (T)-> Boolean): List<T> {  
    val result  = mutableListOf<T>()  
    for(element in this){  
        if(predicate(element)){  
            result.add(element )  
        }  
    }  
    return result.toList()  
}  
  
//Backened api calls be like result , error code  
  
fun makeNetworkcalls():Result<Int, String>{  
    return Result.Failure("Something went wrong")  
}  
sealed class Result<out D,out E>{  
    data class Success<D>(val data: D):Result<D, Nothing>()  
    data class Failure<E>(val data: E):Result<Nothing, E>()  
}

```
