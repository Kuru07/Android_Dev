---
share: true
---
* Functions as a parameter to another function
```kotlin
  
fun main()  
{  
    println("Enter a String")  
    val input = readln()  
  
    val favouritenumbers = intArrayOf(1,2,3,69)  
//    val evenNumbers = favouritenumbers.filter {  
//        it % 2 == 0  
//    }  
  
    val evenNumberss = favouritenumbers.map{  
        it*it  
    }  
//    val lambda:(Char) -> Boolean = {  
//        it.isLetter()  
//    }  
    val lettersOnly = input.filter {  
       currentCharacter -> currentCharacter.isLetter()  
    }  
  
    val letters = input.myFilter {  
        it.isLetter()  
    }  
  
    println(evenNumberss)  
}  
  
fun String.myFilter(predicate: (Char)->Boolean):String{  
    return buildString {  
        for (char in this@myFilter){  
            if(predicate(char))  
                append(char)  
        }  
    }  
}
```
