use std::io;

fn main() {
    let mut count = 0;

    loop {
        println!("Counter: {} | (Type + to increment, - to decrement, q to quit)", count);

        let mut input = String::new();
        io::stdin().read_line(&mut input).expect("Failed to read input");
        let input = input.trim();

        match input {
            "+" => count += 1,
            "-" => count -= 1,
            "q" => break,
            _ => println!("Invalid input, use +, -, or q"),
        }
    }
}
