# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

### What is concurrency? What is parallelism? What's the difference?

> Concurrency: The capability of executing two tasks virtually at same time. They take advantage of CPU time-slicing feature of OS where each task runs part of it and then go to waiting state. When first task is in waiting state, the second task continues its part of task.
Parallelism: The capability of executing multiple tasks (or sub-tasks) at the same time using multi-core infrastructure of CPU. Parallelism is a subset of concurrency.

> The difference between them is that concurrency does not run various tasks simultaneously, but they are distributed along the time, giving the impression of parallelism to the end user. A single-core architecture is valid enough.
Parallelism really execute different tasks at the same time, so it needs a multi-core infrastructure, assigning one core to each task or sub-task.
 
### Why have machines become increasingly multicore in the past decade?
 
 > Since the upper threshold of clock speeds has leveled out during recent years, multi-core processors have become a common means to improve computing performance. While adding more cores does not increase the overall computing performance by a proportional amount (two cores do not equal twice the speed), multi-core processors do provide a substantial performance boost over a single-core CPUs. Additionally, a multi-core processor can run more efficiently than a single processor, since not all cores need to be active unless needed. 
 
### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 
 > When tasks need to run independently of each other at the same time. For instance, a web server. The web server needs to be able to address different users at the same time, while not waiting for another users query to complete. 
 
### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 
 > Concurrent programs speed up the system, but makes programming more complicated, as concurrency is non-deterministic and requires extra components (semaphores, mutex) to avoid the systems blocks.
 
### What are the differences between processes, threads, green threads, and coroutines?
 
 > 1. Process: OS-managed truly concurrent (with the suitable hardware support). Each process exists within its own address space.
2. Thread: OS-managed, within the same address space as the parent and all its other threads. Truly concurrent, and multi-tasking is pre-emptive.
3. Green Thread: These are user-space projections of the same concept as threads, but are not OS-managed. Not truly concurrent, but interleaved or multiplexed instead.
4. Coroutine: Not OS-managed. Exactly as threads, except for co-operatively multitasking, and hence not truly concurrent.
Threads are located inside processes.
 
### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 
 > pthread_create() creates a thread. threading.Thread() also creates a thread. Go creates a goroutine which is like a thread managed by the go runtime.
 
### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 
 > GIL is a mutual exclusion (mutex) module that avoids threads to access the same function (or better said Python object) at a time, making one of these two to wait until the first one finishes. This lock is necessary mainly because CPython's memory management is not thread-safe.

### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 
 > By using the multiprocessing package one can side-step the GIL by using subprocesses instead of threads.
 
### What does `func GOMAXPROCS(n int) int` change? 
 
 > Just for programming language Go, the function GOMAXPROCS sets the maximum number of CPUs that can be executing simultaneously and returns the previous setting. If n<1, it does not change the current setting.
