The embedded-hal crate is elite. gives you a bunch of modules that help you read and write output values to embedded systems devices. 

StatefulOutput is a fun module. can read and write to its own state. nifty.


microbit::Board::take() -> takes control of the peripherals safely.
This method will return an instance of the board the first time it is called. It will return only `None` on subsequent calls. This function can also return `None` if one of the peripherals was already taken. 


[[interrupts-embedded]]

