---
share: true
---
* Null is used to assign a null value if specific value is not assigned
* *!!* operator is used to check  null , but arise ==null pointer exception==
* *?:* Used to assign a ==default value== to a nullable operator
* *?.* Only call a certain function if input is ==not null==
```kotlin
  
fun main()  
{  
   println("Please enter a number")  
    val input = readln()  
  
    val inputInteger = input.toIntOrNull() ?: 0  
    val inputInteger2 = input.toIntOrNull()?.inc()  
  
    val isEven = input.toIntOrNull()?.rem(2)?.equals(0)  
    println("The even number $isEven")  
}
```
* Kotlin has null safety
* 