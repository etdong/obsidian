### Critical sections and race conditions

when multiple threads access a shared resource, it can result in an error if we don't maintain order in which thread reads/writes the resource.

>thread 1 reads 0
>thread 2 reads 0
>thread 1 writes +1 to get 1
>thread 2 writes +1 to get 1 (trolling)

**Mutex** (mutual exclusion) locks make sure theres only one thread that can access the data

before entering a critical section, thread should "take" the lock by calling
`int pthread mutex_lock(pthread_mutex_t* mutex_p)`
and when exiting the critical section:
`int pthread mutex_unlock(pthread_mutex_t* mutex_p)`

when the lock is taken, other threads will sleep or block after attempting to take the lock. only when the owner thread gives the lock back to the system will threads be able to take it again.



**Semaphores** are used for producer-consumer sync.
e.g. thread telephone. thread 0 to thread 1, then thread 1 to thread 2, etc.

could be implemented with busy waiting, but that consumes cpu cycles and is slower.
semaphores are signaled by the owner not requiring downtime