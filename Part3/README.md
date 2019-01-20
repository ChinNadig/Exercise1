# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 
 > In concurrency the tasks look like they are running at the same time but essentially they are not. The CPU operates on the time-slicing feature of operating system where each task will run part of its task and then go to waiting state. When first task is in waiting state, CPU is assigned to second task to complete it’s part of task. 
Whereas in parallelism multiple tasks run at the same time using multi-core infrastructure of CPU, by assigning one core to each task.
 
 ### Why have machines become increasingly multicore in the past decade?
 
 > Since the upper threshold of clock speeds has leveled out during recent years, multi-core processors have become a common means to improve computing performance. While adding more cores does not increase the overall computing performance by a proportional amount (two cores do not equal twice the speed), multi-core processors do provide a substantial performance boost over a single-core CPUs. Additionally, a multi-core processor can run more efficiently than a single processor, since not all cores need to be active unless needed. 
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 
 > When tasks need to run independently of each other at the same time. For instance, a web server. The web server needs to be able to address different users at the same time, while not waiting for another users query to complete. 
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 
 > Both. Situations that require concurrency are easier to solve, however it introduces more complexity to the system and introduces its own set of issues.
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 
 > Processes run in separate memory spaces. Threads run in shared memory space. Standard threads are scheduled by the operating system. Green threads are scheduled by a virtual machine. Coroutines are routines that can run for a while, then return control to another routine, then run some more from where they left off.
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 
 > pthread_create() creates a thread. threading.Thread() also creates a thread. Go creates a goroutine which is like a thread managed by the go runtime.
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 
 > CPythons memory management is not thread-safe, thus the GIL is needed to prevent multiple threads from running the same bytecode. 
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 
 > By using the multiprocessing package one can side-step the GIL by using subprocesses instead of threads.
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 
 > It changes how many logical processors units that are used. 
