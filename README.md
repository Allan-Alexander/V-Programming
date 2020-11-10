# Introduction to V Programming

V lang is a simple, fast, safe, compiled language for developing maintainable software. Despite being simple, V gives a lot of power to the developer and can be used in pretty much every field, including systems programming, webdev, gamedev, GUI, mobile (wip), science, embedded, tooling, etc.

## Why V-lang ?

**Performance**
      As fast as C (V's main backend compiles to human readable C)
      C interop without any costs
      Minimal amount of allocations
      Built-in serialization without runtime reflection
      Compiles to native binaries without any dependencies: a simple web server is only 65 KB
 
**Fast compilation**
      V compiles between ≈80k (Clang backend) and ≈1 million (x64 and tcc backends) lines of code per second per CPU core.
      (Intel i5-7500, SM0256L SSD, no optimization)
      V is written in V and compiles itself in under a second. 

**Small and easy to build compiler**
      V can be bootstrapped in under a second by compiling its code translated to C with a simple      

**C translation (wip)**
      V can translate your entire C project (wip) and offer you the safety, simplicity, and 10-25x compilation speed-up.

**Hot code reloading**
Get your changes instantly without recompiling.

Since you also don't have to get to the state you are working on after every compilation, this can save a lot of precious minutes of your development time.

### Hello World

```v
fn main(){
	println("Hello World")
}

```
OR

```v
println("Hello World")

```
fn main() is by default present<br>
Both works !!

### Variables

 lets print names......<br>
 for this you need to import 'os'.
 'os' is a default lib used to perform I/O operations.<br>

```v

import os
name := os.input("Enter your name: ")
println("Hello $name")

```
'input' is the method of 'os' library.'$' is used to print the value present in 'name' 
   input value is of type **"string"** <br>
   To request for name without any description like 'Enter your name: ' just use -- os.input("")<br><br>

   Variables are declared and initialized with `:=`. This is the only way to declare variables in V.<br> 
   This means that variables always have an initial value. This is done to improve memory management.<br><br>

   variables are by default private and immutable.<br>
   lets make them mutable....

### Mutable Variables
```v
import os
mut name := os.input("Enter your name: ")
println("Hello $name")
name      = os.input("Change name to --> ")
println("New name entered:  $name")
```
Here to change the value we DONT use ':='.<br>
':=' is used to initialize and declare to assign USE "=".<br>
return type of 'os.input' is  **"string"**. 'println' takes only a single argument.

TRY getting your age and id using 'os.input'  

### Numbers
```v
mut age := 21
println("My age is $age")
```
Here the value of age is int which is represented as i32 (int) and i64 (long) ..... which you will see in the next module.
The value of age is assigned by default by the compiler. You can change that by type casting which would be covered in the next module.
Lets try to increment the age by 1

```v

println("My age is $age+1")       // o/p:      My age is 21+1                            
// println("My age is",age+1)     // o/p:      error: too many arguments in call to `println` (2 instead of 1)  
println("My age is $age++")       // o/p:      My age is 21++

// Correct way
print("My age is ")
println(age+1)                    // o/p:       My age is 22 
                                  // Here mut is not required as we are not changing the value present in age  
//        OR
// println(++age)                 // for this to work add 'mut' before 'age'         
                                  //* o/p:       error: expr(): bad token `++`

                                  // explanation: not supported in v.

                                  */  
age++ println(age)                // another way of using ++age                

                                  // o/p:        warning: `++` operator can only be used as a statement
println(age++)                    //             21   
println(age)                      //             22  


```
#### What are STATEMENTS ?
   
   It is something that doesn't "have" a value or assigned a value.
   You can write several statements on the same line if you want, separated only by whitespace
   a := 2 + 2 for example is a statement 
   while just 2 + 2 is an expression.
   
### Arrays


   To declare and initialise an Array
   ```v
   mut num := [1,2,3]
   println(num)
   println(num.len) // o/P: "3"
   num = []
   println(num)      // Array is now empty

   user := []int{}   // Declare an empty array
   length := user.len
   println("user: $user  user length: $length")
```

   Initializing array property 
```v
   arr := []int{ len: 5, init : -1}
```

   The type of an array is determined by the first 
   element of that array.<br> 
   If V is unable to infer the type of an array, the user can 
   explicitly specify it for the first element: [byte(16), 32, 64, 128]. 
   V arrays are homogeneous (all elements must have the same type). 
   This means that code like [1, 'a'] will not compile.

#### Methods in Arrays


   max element in an array can be found using arrays.max<int>(num)
   method.
   min element in an array can be found using arrays.min<int>(num)
   method.
   To get the index of max element :-
   arrays.idx_max<int>(num)
   To get the index of min element :-
   arrays.idx_min<int>(num)
   To shuffle the first n arrays
   arrays.shuffle<int>(mut num, n)
	where n is the first n elements to be shuffled
   
   ```v
   import arrays

   mut num := [1,2,3,4]
   println(num.len)

   println(arrays.max<int>(num))           // max element
   println(arrays.min<int>(num))           // min element
   println(arrays.idx_max<int>(num))       // index of max
   println(arrays.idx_min<int>(num))       // index of min

   num1 := [5,6,7]
   println(arrays.merge<int>(num , num1))  // merge
      /*  OR  */  
   num2 := arrays.merge<int>(num,num1)     // merge
   println(num2)

   arrays.shuffle<int>(mut num,2)          // shuffle the first n elements    
   println(num)

   ```
