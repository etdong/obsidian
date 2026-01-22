remember to do assignment 1

**Process**
basically just a program; contains information about program resources and program execution state. things like:
- PID
- group id
- environment
- working directory
- program instructions
- signal actions
- libraries
- heap
- stack

**Stack**
special region of memory that stores temp variables

push and pops. like normal
not required to manage the memory manually, allocation and frees are automatic

stack variables are bound by the lifetime of their scope

**Heap**
larger than stack, global memory.
manual allocations and frees.

heap does not have stack-like size restrictions

susceptible to memory leaks due to manual error
heap variables are global.

**Threads**
a procedure in a process that runs independently from the main program
they maintain minimal resources to execute code
POSIX threads are lightweight, faster startup threads.
do **not** need to copy data from process to process. threads share address space.
Pthreads rely on shared memory to communicate

Working modes:
- manager/worker
	- the manager thread assigns work to other threads
- peer
	- the manager thread also participates in the work after creating threads
- pipeline
	- the threads each have a sequential job like a factory line

pthread_create and pthread_join create and merge threads respectively.

