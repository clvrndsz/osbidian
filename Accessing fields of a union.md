
The final action that works only with unsafe is accessing fields of a union. A union is like a struct, but only one declared field is used at a time. Unions are primarily used to interface with C unions. Accessing union fields is unsafe because Rust cannot guarantee the type of the data currently being stored in the union instance.

You can read more about rust unions in [the rust reference](https://doc.rust-lang.org/reference/items/unions.html).

[[Unsafe Rust]]
