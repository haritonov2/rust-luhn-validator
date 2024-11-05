# Rust Luhn Validator

This repository contains a Rust implementation of the Luhn algorithm, a simple checksum formula used to validate a variety of identification numbers, such as credit card numbers and Canadian Social Insurance Numbers.

## Features

-  Validate numbers against the Luhn formula
-  Strip spaces from input strings
-  Reject inputs with non-digit characters (except spaces)
-  Determine the validity of credit card numbers and similar identifiers

## Installation

To use this project, you need to have [Rust](https://www.rust-lang.org/) installed on your machine. Clone the repository and build the project using Cargo, the Rust package manager:

```bash
git clone https://github.com/yourusername/rust-luhn-validator.git
cd rust-luhn-validator
cargo build
```

## Usage
You can use the `is_valid` function in your Rust project to check the validity of a number string:

```rust
use rust_luhn_validator::is_valid;

fn main() {
    let number = "4539 3195 0343 6467";
    if is_valid(number) {
        println!("The number is valid.");
    } else {
        println!("The number is invalid.");
    }
}
```

## Example
Here's how the Luhn algorithm works on a valid credit card number:
1.	Double every second digit from the right:
▪	4539 3195 0343 6467 becomes 8569 6195 0383 3437
2.	Sum all the digits:
▪	8+5+6+9+6+1+9+5+0+3+8+3+3+4+3+7 = 80
3.	Check if the sum is divisible by 10:
▪	80 % 10 == 0, so the number is valid.
