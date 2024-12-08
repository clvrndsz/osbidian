Interrupts are the only way to actually use peripheral controls to edit and control the state of your program. The catch is that they are to called asynchronously and the only way to share data is by writing to statically allocated memory. Ultra risky for data races. 


I am now using the rust discovery book to teach me instead.