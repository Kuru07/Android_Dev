---
share: true
---
* To bundle data 
* Use like a blueprint for something
* Objects are instances
* Has constructor and functionality ( behaviour) 
* Classes by default are comaparable ==( In default comapred by refernces not by content)==
## Normal class
```kotlin
import org.w3c.dom.css.Rect  
import kotlin.math.sqrt  
  
fun main()  
{  
  
    val rect1 = Rectangle(  
        widrh = 5f,  
        height = 7f  
    )  
      
    val rect2 = Rectangle(  
        widrh = 5f,  
        height = 7f  
    )  
      
    println(rect1 == rect2) //False as refrences are different  
    println(rect1.height)  
    println(rect1.widrh)  
    println(rect1.diagonal)  
    println("Area is ${rect1.area}")  
}  
  
fun maxArea(rect1: Rectangle, rect2: Rectangle): Float  
{  
    val area1 = rect1.area  
    val area2 = rect2.area  
  
    return maxOf(area1,area2)  
}  
  
class Rectangle(val widrh: Float, val height: Float)  
{  
    val diagonal = sqrt(widrh * height + height * height)  
  
    val area = widrh * height  
}
```
## Data class
* For comapring content we use data class
* Has copy function to change a specific field while copying

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
    println(circle.area)  
  
    println(rect2)  
}  
  
  
data class Rectangle(val widrh: Float, val height: Float)  
{  
    val diagonal = sqrt(widrh * height + height * height)  
  
    val area = widrh * height  
}  
  
data class Circle(val radius: Float){  
    val area = radius * radius * PI  
}
```
