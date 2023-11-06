- Type comes after the variable name

```
func add(x int, y int) int {
return x+ y
}
```


```
x int, y int
to 
x,y int
```

- A function can return any number of results
```
func swap(x,y int)(int int){
    return y,x
} 
```


- 
```
import "fmt"
import "math"

fmt.printf( "Hello world, there are %g  problems ",mat.sqrt(7))
fmt.println(math.sqrt(7))
}
```

- Variables
  ```
  var hi, hey, hello bool
  var bye int 
  var bye string //needs to initialised 
  ```
 

 > If an initializer is present, the type can be omitted; the variable will take the type of the initializer.

 ```
 var i, j int = 1, 2

func main() {
	var c, python, java = true, false, "no!"
    k:= false  //This shorthand is not available oustide functions.

	fmt.Println(i, j, c, python, java)
}
 
 ```


- Basic types of Go
    > 
> int8, int16, int32, int64, uint8, uint16, uint32, uint64, uintptr:

> System-level programming: These types are often used for low-level tasks like interacting with hardware, file I/O, and managing memory.
> Numeric processing: They are used for mathematical computations, data processing, and representing quantities such as time durations.
> byte (alias for uint8):

> Binary data handling: Bytes are essential for working with raw binary data, such as reading and writing files, network communication, and cryptography.
> rune (alias for int32):

> Text processing and internationalization: Runes are used to handle Unicode characters, making them crucial for internationalization, text manipulation, and parsing.
> float32, float64:

> Scientific computing: These types are used in scientific simulations, physics calculations, and data analysis where precision is required.
> Financial applications: Floats are used in financial modeling, risk analysis, and stock market prediction due to their precision.
> complex64, complex128:

> Signal processing: Complex numbers are used in signal processing for tasks like Fourier analysis, digital filters, and audio processing.
> Control systems: They are used in control system design, simulations, and analysis for systems with complex impedance.

```
bool

string

int  int8  int16  int32  int64
uint uint8 uint16 uint32 uint64 uintptr

byte // alias for uint8

rune // alias for int32
     // represents a Unicode code point

float32 float64

complex64 complex128

```
 > Unlike in C, in Go assignment between items of different type requires an explicit conversion

- Type Inference
  
  ```
    i := 42           // int
    f  := 3.142        // float64
    g := 0.867 + 0.5i // complex128
  
  ```

- Constants
  
> with keyword `const` `const Pi = 3.14`
> Constants cannot be declared using the := syntax

- Numeric Constants


```
const (
	// Create a huge number by shifting a 1 bit left 100 places.
	// In other words, the binary number that is 1 followed by 100 zeroes.
	Big = 1 << 100
	// Shift it right again 99 places, so we end up with 1<<1, or 2.
	Small = Big >> 99
)

func needInt(x int) int { return x*10 + 1 }
func needFloat(x float64) float64 {
	return x * 0.1
}

func main() {
	fmt.Println(needInt(Small))
	fmt.Println(needFloat(Small))
	fmt.Println(needFloat(Big))
}
```

- For loop

> Go has only one looping construct, the for loop.

> The basic for loop has three components separated by semicolons:

> the init statement: executed before the first iteration
> the condition expression: evaluated before every iteration
> the post statement: executed at the end of every iteration
> The init statement will often be a short variable declaration, and > the variables declared there are visible only in the scope of the for statement.

> The loop will stop iterating once the boolean condition evaluates to false.

> Note: Unlike other languages like C, Java, or JavaScript there are no parentheses surrounding the three components of the for statement and the braces { } are always required.

```
package main

import "fmt"

func main() {
	sum := 0
	for i := 0; i < 10; i++ {
		sum += i
		fmt.Println(sum)
	}
	fmt.Println(sum)
}

```

- For continued and For is Go's while
> The init and post statements are optional.
> At that point you can drop the semicolons: C's while is spelled for in Go.
```

func main() {
	sum := 1
	for sum < 1000 {
		sum += sum
	}
	fmt.Println(sum)
}
```
- Forever
  > If you omit the loop condition it loops forever, so an infinite loop is compactly expressed.
  `for{}`

- If and else
  > Go's if statements are like its for loops; the expression need not be surrounded by parentheses ( ) but the braces { } are required.

  ```
  // Variables declared by the statement are only in scope until the end of the if 

  // Variables declared inside an if short statement are also available inside any of the else blocks.
  if v:= math.sqrt(r); v> n{ 
    return v
  }else{
    fmt.Println(v)
  }
  fmt.Println(v) // can't accesss this here
  ```

  - Newton's Method


- Switch
> break; statement is not needed in Go, Another important difference is that Go's switch cases need not be constants, and the values involved need not be integers.
```
func main() {
fmt.Print("Go runs on ")
switch os := runtime.GOOS; os {
case "darwin":
    fmt.Println("OS X.")
case "linux":
    fmt.Println("Linux.")
default:
    // freebsd, openbsd,
    // plan9, windows...
    fmt.Printf("%s.\n", os)
}
}

```


- Switch Evaluation Order
> Using javascript on switch cases is awesome, Switch without a condition is the same as switch true.
```
func main() {
	fmt.Println("When's Saturday?")
	today := time.Now().Weekday()
	switch time.Saturday {
	case today + 0:
		fmt.Println("Today.")
	case today + 1:
		fmt.Println("Tomorrow.")
	case today + 4:
		fmt.Println("In two days.")
	default:
		fmt.Println("Too far away.")
	}
}

func main() {
	t := time.Now()
	switch {
	case t.Hour() < 12:
		fmt.Println("Good morning!")
	case t.Hour() < 17:
		fmt.Println("Good afternoon.")
	default:
		fmt.Println("Good evening.")
	}
}

```

- Defer
> A defer statement defers the execution of a function until the surrounding function returns.

- Stacked Defers
> A defer statement defers the execution of a function until the surrounding function returns.

- Pointers
> Go has pointers. A pointer holds the memory address of a value.
> The type *T is a pointer to a T value. Its zero value is nil.


 `var p *int`

> The & opeator generates a pointer to its operand

 ```
i := 42
p = &i 
 ```
> The * operator denotes the pointer's underlying value.

```
fmt.Println(*p) // read i through the pointer p
*p = 21         // set i through the pointer p
```

> This is known as "dereferencing" or "indirecting".

> Unlike C, Go has no pointer arithmetic.

- Structs