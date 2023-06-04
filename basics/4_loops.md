# Loops

- loop ... only found in RUST
- for loop
- while loop


# 1) loop 
runs an infinite loop!

// runs forever
loop {
    println("Hello")
}

// runs until break
let mut counter = 0;
loop {
    counter += 1
    println!("{}", counter);
    if counter == 10 {
        break;
    }
}



# 2) while loop

// while loop
let mut counter = 0;
while counter <= 10 {
    println!("{}", counter);
    counter += 1;
}

# 3) for loop

// for loop

let my_list = ["A", "B", "C"]

for letter in my_list.iter() {
    println!("{}", letter);
}