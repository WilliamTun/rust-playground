
# Ownership and borrowing

- ! This is advanced concept!
- memory mangement makes RUST great
- permits: speed, safety and ease of parallel processing


reminder:
# STACK
- The stack is the memory set aside as scratch space for a thread of execution. The stack is always reserved in a LIFO (last in first out) order; the most recently reserved block is always the next block to be freed. This makes it really simple to keep track of the stack; freeing a block from the stack is nothing more than adjusting one pointer.
# HEAP
- The heap is memory set aside for dynamic allocation. Unlike the stack, there's no enforced pattern to the allocation and deallocation of blocks from the heap; you can allocate a block at any time and free it at any time. This makes it much more complex to keep track of which parts of the heap are allocated or free at any given time; 


# Key points
- Ownership and borrowing only applies to data on the heap. 
- keep an eye on:
  1) who owns the data at a giventime
  2) do we pass data by reference or value
  3) is the data mutable

# =========================
# Memory Management

GARBAGE COLLECTION
-> gives relief from memory management
-> manual memory management involves:
   a) creating objects
   b) using objects
   c) deallocating objects
   
-> morphs memory mangement workloads to different form
-> memory management is handled by GARBAGE COLLECTOR! 

-> as a RUST programmer, you need to pay attention to situations where garbage collector cannot dispose of objects
eg. subscribing and unsubscribing to events 

-> C++ : memory management is handled by programmer
-> RUST : takes responsibility of memory management

# =========================
# Ownership

// this set of code will fail
let X = String::from("original value");
let Y = X
println!("{}", X)
// ^ we cannot print X anymore
//   as the value originally in X
//   has been passed onto Y
//   Y now owns the original value


# =========================
# Borrowing

// Allows another variable to temporarily take ownership of the data WITHOUT deallocating the original variable

let mut X = String::from("original value");  <--- note the mutable mut
let Y = &X // <--- note the appersand& 
println!("{}", X)


