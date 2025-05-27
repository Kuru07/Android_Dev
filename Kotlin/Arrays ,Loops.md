---
share: true
---
## Arrays
 * Arrays size are fixed
 * Can add extra number by ==+==
 * But above will create ==2 arrays==
 * Immutable
 ```kotlin
   
fun main()  
{  
    val input = readln()  
    val inputAsInteger = input.toIntOrNull()  
   val favuoriteNumbers = intArrayOf(1,2,3,4,5,69)  
  
    favuoriteNumbers[3] = 57  
    if(inputAsInteger!=null && inputAsInteger in 0..favuoriteNumbers.lastIndex)  
    {  
        println("Your number is ${favuoriteNumbers[inputAsInteger]}")  
    }  
    else  
        println("Number not exists")  
}
```
## Loops
* Use *continue* to next iterate loops
* *Break* used to break the loops
* But getting input for the arrays in loops will create as much as ==arrays==
* ***List*** are mutable form of arrays

### While
```kotlin
  
fun main()  
{  
    println("How many numbers wanted?")  
    val amount = readln().toIntOrNull() ?: 0  
  
    var i = 0  
  
    //var numbers = intArrayOf()  
  
    var numbers = mutableListOf<Int>()  
    var sum = 0  
    while(i < amount){  
        println("Please Enter number #${i+1}")  
        //val number = readln().toIntOrNull() ?: 0  
  
        //val number = readln().toIntOrNull() ?: break  
        val number = readln().toIntOrNull() ?: continue  
  
        //numbers+= number  
  
        numbers.add(number)  
  
        i++  
    }  
  
    println("Numbers: ${numbers}")  
}
```

### For Loops
 
```kotlin
  
fun main()  
{  
    println("How many numbers wanted?")  
    val amount = readln().toIntOrNull() ?: 0  
  
    var numbers = mutableListOf<Int>()  
  
    for(i in 0 until amount)  
    {  
        println("Please Enter number #${i+1}")  
        val number = readln().toIntOrNull() ?: continue  
        numbers.add(number)  
    }  
  
    for(number in numbers)  
        println(number)  
  
  
    println("Enter a string")  
    val input = readln()  
  
//    for(char in input)  
//        println(char)  
  
    val final = buildString {  
    for(char in input.lastIndex downTo 0)  
        append(input[char])  
    }  
  
    println(final)  
}
```
