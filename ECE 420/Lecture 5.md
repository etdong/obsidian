more multithreading

passing arguments to threads

```
rc = pthread_create(&threads[t], null, PrintHello, (void*) t);
```

cast it to a single void reference is correct.

```
rc = pthread_create(&threads[t], null, PrintHello, (void*) &t);
```
passing the address is okay but not recommended in pthreads. need to watch out for the lifetime of t.

when on heap (malloc'd), do not need to pass it since it is globally accessible.

**Where are variables stored?**

globals: data
statics: data
constants: code or data
	constant itself stored in data segment, references are embedded in the code
local variables: stack
pointers: data or stack
	depends on the context. you can declare global or static pointer, in which case the pointer will end up in the data segment.
dynamically alloc'd space: heap


easier to pass multiple arguments to a thread using a struct.


**Tread Termination**
ways that a thread can be terminated:
- thread returns normally from routine
- thread makes a call to pthread_exit(status)
- the parent process is terminated by return or exit()
- if main finishes first without calling pthread_exit() explicitly (return is called implicitly to terminate the process)

in subroutines that execute to completion normally, no need to explicitly call pthread_exit().


joining is a way of synchronizing threads.

pthread_join() blocks the calling thread until the threadid thread terminates.
usually called by main to wait for threads to finish.