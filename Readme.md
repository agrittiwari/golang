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
- Unlike in C, in Go assignment between items of different type requires an explicit conversion

- Type Inference
  ```
  i := 42           // int
f := 3.142        // float64
g := 0.867 + 0.5i // complex128
  ```

- Constants
with keyword `const`
`const Pi = 3.14`
Constants cannot be declared using the := syntax

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