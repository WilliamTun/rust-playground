
# Basic function 

fn main() {
    let greater = return_greater(10, 5)
    println!("{}", greater);
}

fn return_greater(first: u8, second: u8) -> u8 {
    if first > second {
        first
    } else {
        second
    }
}

# TWO key ways data is passed to a function
1. Pass by value
   - pass actual value from stack
2. Pass by reference
   - pass pointer to value
     and value is kept on heap


# =========================

# Closures - Are functions without a name


1) example 1: basic
```
// closures are defined by "||"
|| {
    println("This is a closure")
}
```


2) example 2: write out & call closures by assigning to a variable
'''
// assign closure to varable

let wrte_message = || {
    println("This is a closure")
}

write_message();
'''



3) example 3: add parameters to closures

'''
let name = "Will";
let write_message |slogan: String| {
    println("{}, {}", name, slogan;
};

write_message(String::from("i like to dance zouk"));
'''


4) example 4: write message out to console and return value from closure

let name = "Will"
let write_message |slogan: String| -> String {
    String::from( format!("{}, {}", name, slogan))
};

let phrase = write_message(String::from("I like zouk"));
println!("{}", phrase);

# ==========================