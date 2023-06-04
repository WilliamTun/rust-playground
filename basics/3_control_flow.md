# IF ELSE STATEMENTS

let word = "Duck";

if word == "Duck" {
    println("Quack");
} else if word == "Dog" {
    println!("Woof")
} else {
    println!("...")
}


# MULTI-CONDITIONAL IF ELSE

let letter = "X"
let y = 0
let z = 1

if (letter == "X" || 
    letter == "Y")
    && y <= 5 {
        println!("Do something")
    }



# ENUM 

Option enum:
1. Some (value exists)
2. None (no value exists)


let phrase = String::from("Duck Airlines");
let letter = phrase.chars().nth(5)
let value = match letter {
    Some(character) => character.to_string()
    None => String::from("no value")
};

println("{}", value);

// ^ if nth on line 36 was set to 5, print would return letter A from Duck Airlines.
// ^ if nth on line 36 was set to 100, a value does not exist and so, we would print "no value"


# MATCH STRING

let animal = "Duck";
match animal {
    "Duck" => println!("Quack")
    "Dog" => println!("Bark!")
    _ => println!("...silence...")
}


# MATCH RANGE

let ndb_freq = 384

// if frequency range is between 200 and 500, it is valid:

match ndb_freq {
    200..=500 => {
        println!("NDB freq is valid");
    }
    _ => {
        println!("Invalid NDB freq")
    }
}

// alternative line: 

match ndb_freq {
    ndb_freq if ndb_freq >= 200 && ndb_freq <= 500 => {
        println!("NDB freq is valid");
    }
    _ => {
        println!("NDB freq is not valid");
    }
}



# MATCH with ENUM

// define enum with types
enum NavigationAids {
    NDB(u16),
    VOR(String, f32),
    VORDME(String, f32),
    FIX{name: String, latitude: f32, longitude: f32}
}

// assign values to enums
fn main() {
    let ndb_uwl =  NavigationAids::NDB(100)
    let vor_dqn = NavigationAids::VOR(String::from("DQN"), 114.5)
    let vor_dme_sgh = NavigationAids::VORDME(String::from("SGH"), 118.5) 
    let fix_tarry = NavigationAids::FIX {
        name: String::from("TARRY"),
        latitude: 40.053,
        longitude: -83.91
    }
}

