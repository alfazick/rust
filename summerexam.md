
## 1. File I/O (20 marks)

**Objective**: Understand file handling and error management in Rust.

**Task**:
Write a Rust program that copies the content of a source file named `source.txt` to a destination file named `destination.txt`. Handle potential errors like file not found, insufficient permissions, etc., and provide a descriptive error message.

**Starter Code**:
```rust
fn main() {
    let source = "source.txt";
    let destination = "destination.txt";
    
    // TODO: Implement the file copy logic here.
}
```

## 2. Shared State Concurrency (20 marks)

**Objective**: Understand the use of `Arc` and `Mutex` to safely share mutable state across threads.

**Task**:
Write a Rust program that spawns multiple threads to increment a shared counter. The counter should be a mutable integer wrapped in a `Mutex` and then in an `Arc` to allow safe shared access from multiple threads. Spawn 10 threads, and each thread should increment the counter 100 times. After all threads have finished their execution, print the final value of the counter in the main thread. The expected output should be 1000.

**Starter Code**:
```rust
use std::sync::{Arc, Mutex};
use std::thread;

fn main() {
    let counter = Arc::new(Mutex::new(0));

    let mut handles = vec![];

    for _ in 0..10 {
        let counter = Arc::clone(&counter);
        let handle = thread::spawn(move || {
            // TODO: Increment the counter 100 times in this thread.
        });
        handles.push(handle);
    }

    for handle in handles {
        handle.join().unwrap();
    }

    // TODO: Print the final value of the counter.
}
```

## 3. Inter-process Communication (20 marks)

**Objective**: Understand how to use channels for communication between processes.

**Task**:
Implement a Rust program where two processes communicate using channels. One process (the sender) should send a string message to the other process (the receiver). The receiver should convert the received string to uppercase and send the modified string back to the sender. The sender should then print the received uppercase string.

**Starter Code**:
```rust
use std::thread;
use std::sync::mpsc;

fn main() {
    let (tx, rx) = mpsc::channel();

    // TODO: Spawn the sender and receiver threads and implement the logic.
}
```
## 4. Error Handling (20 marks)

**Objective**: Understand Rust's error handling mechanism and how to define custom error types.

**Task**:
Write a Rust function that reads an integer from a file named `data.txt` and multiplies it by 2. The function should return a `Result<i32, CustomError>`. Define a `CustomError` enum that can represent various error conditions such as:
- File not found.
- Parsing error (e.g., the file does not contain a valid integer).

**Starter Code**:
```rust
enum CustomError {
    // TODO: Define the variants of CustomError.
}

fn multiply_from_file() -> Result<i32, CustomError> {
    // TODO: Implement the function logic.
    unimplemented!()
}

fn main() {
    // TODO: Test the multiply_from_file function.
}
```
## 5. Generics and Traits (20 marks)

**Objective**: Understand the use of generics and traits to create flexible and type-safe code in Rust.

**Task**:
Define a trait named `Area` with a method `area(&self) -> f64`. Implement the `Area` trait for several geometric shapes like `Rectangle`, `Circle`, and `Triangle`. Create a generic function `print_area<T: Area>(shape: T)` that takes any shape and prints its area. In the `main` function, create instances of each shape and use the `print_area` function.

**Starter Code**:
```rust
trait Area {
    // TODO: Define the area method.
}

// TODO: Define the geometric shapes and implement the Area trait for them.

fn print_area<T: Area>(shape: T) {
    // TODO: Implement the function logic.
}

fn main() {
    // TODO: Test the geometric shapes and the print_area function.
}
```

