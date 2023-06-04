


# Scalar data types: 
hold one value
- numbers
- characters
- booleans

# Compound data types: 
hold many values
- arrays
- tuples

# String data types



# ==============================
# PRIMITIVE DATA TYPES

# Integer whole numbers. 
writing code that uses integer, we want to know if the integer is negative. 
- If we work with negative values, we need a SIGNED INTERGER. SIGN = + / - 
- If we work with just positive values, we can use an UNSIGNED INTEGER

Why use unsigned integer vs signed?
Max value of an unsigned integer is much larger (~2x) than signed integer.

How many bits do we assign an integer?
RUST can assign:
8 / 16 / 32 / 64 / 128 bits to an integer


If we declare an UNSIGNED 8 bit value, 
it can be between 0 and 255

If we decalred a SIGNED 8 bit value,
it can be netween -128 and 127


# rust syntax for ints / floats
"i" = signed integer
"u" = unsigned integer
"isize" and "usize" = tied to CPU
"f32" = unsigned 32bit floating point 
"f64" = unsighed 64bit floating point.


# booleans
true / false

# characters
- letters and numbers on a keyboard is a character.
- under the hood, the characters are stored as numbers. 
- specific characters have a specific number associated with in, in a key-value pair. 
- what defines the character-number key-value pairs? These definitions are defined in the ASCII and Unicode tables.


- 1 byte characters restricted to 255 characters in ASCII table
- 2 byte characters restricted to 65,535 characters in Unicode-16 table
- 4 byte characters restricted to 4,294,967,296 characters in Unicode-32 table. This is a RUST thing. Any character in RUST can be any character in any language & more! 


# ============================

# COMPOUND DATA TYPES

Arrays 
- holds multiple values of SAME datatypes

Tuples
- holds multiple values of MANY datatypes

^ These data types are fast at runtime
  but they are declared at FIXED SIZE. 


Example array:

let X [<datatype>;<length>] = [x, x];
let X [f32;2] = [0.0, 0.0];
let X [f64;10000] = [0.0; 10000];

Example Tuple:

let X : (<datatype>, <datatype>, <datatype>) = ("x", x, x)
let X : (&str, f64, f64) = ("KCLE", 40.0, -40.0);


Printing tuples:

Option 1: string interpolation
let location : (&str, f64, f64) = ("KCLE", 41.2, -48.5);
println!("location name: {}, lat {}, long {}",
location.0, location.1, location.2);

Option 2: destructuring
let location : (&str, f64, f64) = ("KCLE", 41.2, -48.5);
let (name: str, lat: f64, long: f64) = location;
println!("Location name: {}, lat {}, long {}", name, lat, long);



# ============================

# STRING

# TWO TYPES OF STRINGS

1. String
   - vector of u8 data
   - mutable
   - stored on the heap
2. &str ("string slice")
   - vector of u8 data
   - immutable
   - stored on choice of heap / stack / embedded in compiled code


reminder:
- The stack is the memory set aside as scratch space for a thread of execution. The stack is always reserved in a LIFO (last in first out) order; the most recently reserved block is always the next block to be freed. This makes it really simple to keep track of the stack; freeing a block from the stack is nothing more than adjusting one pointer.
- The heap is memory set aside for dynamic allocation. Unlike the stack, there's no enforced pattern to the allocation and deallocation of blocks from the heap; you can allocate a block at any time and free it at any time. This makes it much more complex to keep track of which parts of the heap are allocated or free at any given time; 


# Concatenation of strings

let X : &str = "X";
let Y : &str = "Y";

// option 1
let XY = [X, Y].concat();

/// option 2
let XY2 = format!("{}{}", X, Y);


