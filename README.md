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
return type of 'os.input' is  **STRING**. 'println' takes only a single argument.

TRY getting your age and id using 'os.input'  
