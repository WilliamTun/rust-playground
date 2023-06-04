# Error handling


1. Recoverable error
2. Unrecoverable error (panic) - programme will crash


example.
let vector = vec![1,2,3]
println!("{}", vector[10]) // note. no values at index 10
// ^ this causes a panic unrecoverable error


# two ways to handle error
1. Handle the error
2. propagate the error 
   eg. log error and move on
   eg. ask user to fix error via input calls on the command line


# basic error handling example -> file not found
'''
use std::fs:File;

fn  main() {
    let filename = "path/to/file.txt"
    match File::open(filename) {
        Ok(file) => {
            println!("{:#?}", file);
        }
        Err(error) => {
            println!("{:#?}", error);
        }
    }
}

'''


# basic error handling example -> file not found with "ErrorKind"

'''
use std::fs:File;

fn  main() {
    let filename = "path/to/file.txt"
    match File::open(filename) {
        Ok(file) => {
            println!("{:#?}", file);
        }
        Err(error) => {
            match error.kind() {
                ErrorKind::NotFound => {
                    println!("File not found!");
                }
            }
        }
        _ => {
            println!("some other error found!");
        }
    }
}
'''




