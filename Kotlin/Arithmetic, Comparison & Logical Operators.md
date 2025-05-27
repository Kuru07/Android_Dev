---
share: true
---
## Arithmetic operators
```kotlin
  
fun main()  
{  
    val x=5  
    val y=6  
    val z=7.0  
    var a = 11  
    println(x+y) // Add  
    a++  
    a+=5  
    a-=5  
    a*=5  
    a/=5  
    println(a+y)  
    a--  
    println(a+y)  
    println(x-y) // Sub  
    println(x/y) // Div  
    println(x/z) // Div  
    println(x*y) // Mul  
    println(x%y) // Modulo  
}
```
## Comparison operators
*$* is a string template operator
```kotlin
  
fun main()  
{  
    val x=5  
    val y=4  
    val equal = x == y  
  
    println("Is x is a even number? ${x % 2== 0}")  
    println("Is y is a even number? ${y % 2== 0}")  
    println(equal)  
    println(x == y)  
    println(x > y)  
    println(x < y)  
    println(x != y)  
    println(x <= y)  
    println(x >= y)  
    println(x % y == 0)  
}
```
## Logical Operators
```kotlin
  
fun main()  
{  
    val x=5  
    val y=4  
    val andBothEven = x % 2 == 0 && y % 2 == 0  
    val orBotheven = x % 2 == 0 || y % 2 == 0 && x + y == 7  
    println("Is x an even? $andBothEven ")  
    println("Is x an even? $orBotheven ")  
}
```
