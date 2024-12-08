Associated types connect a type placeholder with a trait such that the trait method can use these placeholder types in their signatures.  The implementer of a trait will specify the concrete type to be used in place of the placeholder type for the particular implementation. That way, we can define a trait that uses some types without needing to know exactly what types are until the trait is implemented.

One example of  a trait with an associative type is the `Iterator` trait that the standard library provides. The associated types is named `Item` and stands in for the type of the values the type implementing the `Iterator` trait is iterating over. The definition of the `Iterator` trait is as shown below.

```rust
pub trait Iterator {
	type Item;
	
	fn next(&mut self) -> Option <Self::Item>;
}
```

Associated types might seem like a similar concept generics in that the latter allow us to define a function without specifying what types it can handle. but they are different.

Trust me. I'm telling you they are NOT the same bro. relax. You're asking too many questions. Hey quit it man, you are gonna get us both in trouble.


I cannot lie this feature seems mad boring to care about.  I am gonna pass for now, and figure it out when i am building something bigger.

watching this video : https://www.youtube.com/watch?v=RDxz94tuxqM&list=PLai5B987bZ9CoVR-QEIN9foz4QCJ0H2Y8&index=37


