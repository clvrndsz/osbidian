
We can use unsafe rust to implement an unsafe trait, a trait is unsafe when at least one of its methods has some invariant that the compiler cannot verify. We declare that a trait is unsafe by adding  the unsafe keyword before `trait` and marking the implementation of the trait as `unsafe` too. 


```rust
unsafe trait Foo {
    // methods go here
}

unsafe impl Foo for i32 {
    // method implementations go here
}

fn main() {}

```


By using the `unsafe impl`, we're promising that we'll uphold the guarantees of safety ourselves. 

[[Unsafe Rust]]