---
share: true
---

## Normal Functions
```kotlin
fun main()  
{  
    println("Enter a String")  
    val input = readln()  
  
    val final = reversed(string = input)  
    println("Reversed : $final")  
    println("Original : ${reversed(final)}")  
}  
  
fun reversed(  
    string : String = " Hello "  
) : String{  
    val final = buildString {  
        for(char in string.lastIndex downTo 0)  
            append(string[char])  
    }  
    return final  
}
```
## Extension Functions
* Can use after *.* operator
* Can specify in which var arg we can call the function and still it has its parameters
```kotlin
  
fun main()  
{  
    println("Enter a String")  
    val input = readln()  
  
    val final = input.reversed()  
    println("Reversed : $final")  
  
}   
  
fun String.reversed() : String{  
    val final = buildString {  
        for(char in this@reversed.lastIndex downTo 0)  
            append(this@reversed[char])  
    }  
    return final  
}
```

## Function Overloading
* With same signature we cant overload functions

```kotlin
  
fun main()  
{  
    println("Enter a String")  
    val input = readln()  
  
  
    val final = input.toIntOrNull()?.reversed()  
    println("Reversed : ${final}")  
  
}  
  
fun String.reversed() : String{  
    val final = buildString {  
        for(char in this@reversed.lastIndex downTo 0)  
            append(this@reversed[char])  
    }  
    return final  
}  
  
fun Int.reversed() : Int{  
    return this.toString().reversed().toInt()  
}
```