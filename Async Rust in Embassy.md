This is what a standard linux async runtime does. It waits for tasks and makes calls to them by using references to the heap. This causes issues in the rust embedded world
![[Pasted image 20241127201921.png]]
Two issues. we cannot make calls to the heap, due the lack of safety. So we solve this by statically allocating tasks on, as you guessed, the stack. using linked lists and futures, each task is called when the waker calls for it by just looking at a new task in memory. Refcounting is also needed. 
![[Pasted image 20241127203331.png]]

 Second issue is No OS. So the scheduling and execution must be done by means of the runtime. ![[Pasted image 20241127214450.png]]
This is to make the peripherals accessible. we know that io is memory mapped, so we can access the right locations [registers] and hit the functions that we need to use.

but how to wait? interrupts!

![[Pasted image 20241127215852.png]]

This is the overview of embedded rust with embassy.

One glitch in the plan tho is DMA: you usually get an interrupt per byte from the Memory peripheral you are DMAing into. This is very inefficient if you are relying on the async triangle up there to read your interrupts instead of an underlying RTOS. Embassy handles this admittedly badly by using a memory read from the peripheral at a statically allocated read location and sends back the whole payload by sending an interrupt at the very end. Prone to leaking :/

 
 