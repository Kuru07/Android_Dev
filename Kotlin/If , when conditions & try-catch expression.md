---
share: true
---
## IF Conditions
```kotlin
  
fun main()  
{  
   println("Please enter a number")  
    val input = readln()  
  
    val inputInteger = input.toIntOrNull()  
  
    if(inputInteger != null) {  
        val output1 = if(inputInteger % 2 == 0 )  
        {  
            "Even"  
        }  
        else  
        {  
            "odd"  
        }  
        val isEven = inputInteger % 2 == 0  
        if(isEven) {  
            println("The even number $isEven")  
  
        }else if(!isEven)  
            println("Odd Number")  
        println(output1)  
    }  
    else  
        println("Input is NULL")  
}
```

## When Operations
```kotlin
  
fun main()  
{  
   println("Please enter a number")  
    val input = readln()  
  
    val inputInteger = input.toIntOrNull()  
  
    val output = when (inputInteger){  
        null -> "Enter a valid number"  
        3 -> "Number is 3"  
        5 -> "Number is 5"  
        in 10..20 -> "In Range 10 and 20"  
        else -> "I have no idea"  
    }  
    println(output)  
  
    if(inputInteger != null) {  
        val output1 = when {  
            inputInteger % 2 == 0 -> "the number is even!"  
            inputInteger < 10 -> "Less than 10"  
            else -> "Number is odd and atleast 11"  
        }  
        println(output1)  
    }  
    else  
        println("Input is NULL")  
}
```
## Try & Catch
* ==Grey links== are internal functions
* ==Blue links== are in our file
```kotlin
  
fun main()  
{  
   println("Please enter a number")  
    val input = readln()  
      
    //throw Exception("Dude wtf is pass there")  
    val inputInteger = try{  
        input.toInt()  
    }catch (e: Exception)  
    {  
        0  
    }  
    finally {  
        //Use in more advanced  
    }  
  
    val output = when (inputInteger){  
        3 -> "Number is 3"  
        5 -> "Number is 5"  
        in 10..20 -> "In Range 10 and 20"  
        else -> "I have no idea"  
    }  
    println(output)  
}
```

