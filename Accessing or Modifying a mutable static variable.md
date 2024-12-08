In this book, we've not talked about _global variables_, which rust does support but can be problematic with Rust's ownership rules. If the threads are accessing the same mutable global variable, it can cause a data race.


In Rust, global variables are called _static variables_.  Heres an example of a declaration and use of a static variable with a string slice as a value. 

```rust

static HELLO_WORLD: &str = "Hello World!";

fn main() {
	println!("name is: {HELLO_WORLD}");
}
```

The names of static variables in Rust are in _SCREAMING_SNAKE_CASE_ by default.


The weirdest thing is that static variables can  be mutable.  Constants are not mutable. 

And since they are multi thread accessible. So any ~~mutable~~ access to a static variable can cause a data race. which is unsafe. 

Rust considers mutable static variables unsafe. Then why are they allowed lol. Random ass weapon. 

[[Unsafe Rust]]