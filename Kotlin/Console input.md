---
share: true
---
To read input well use *readln()*
```kotlin
  
fun main()  
{  
   println("Please enter a number")  
    val input = readln().toInt()  
  
    val isEven = input % 2 == 0  
    println("You've entered $input and even: $isEven")  
}
```
