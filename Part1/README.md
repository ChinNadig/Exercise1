Part1: Thinking about elevators
---------------------------

Not for handing in, just for thinking about. Talk to other groups, assistants, or even people who have taken the course in previous years.

Brainstorm some techniques you could use to prevent a user from being hopelessly stranded, waiting for an elevator that will never arrive. Think about the [worst-case](http://xkcd.com/748/) behaviour of the system.

### What if the software controlling one of the elevators suddenly crashes?
> The embedded system should have an independent SW code applied in a particular area of the Flash memory (Bootloader), which detects if the main SW code crashes, acting in consequence.

### What if it doesn't crash, but hangs?
> As the system should be programmed in a real time approach, some emergency functions might be activated if the processes do not meet the predefined deadline.

### What if a message between machines is lost?
> One system should be aware of expecting incoming messages from another one, asking for them again and/or executing another function in consequence.

### What if the network cable is suddenly disconnected? Then re-connected?
> There should be an incoming “life signal” value (a 4-bytes counter, for example) in order to know when the cable is disconnected and re-connected.

### What if a user of the system is being a troll?
> The algorithm should be smart enough to be aware of what an external element/user can do into the system, and limit its possibilities.

### What if the elevator car never arrives at its destination?
> A group of sensors (and an efficient algorithm) should be used by the system to know if the destination if never arrived because the elevator is physically not been moved or the condition to confirm the right destination (limit switch, mathematical calculation…) is never high.
