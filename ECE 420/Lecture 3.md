Lecture 3 (Friday, January 9)
S(p) = p
linear speedups - embarassingly parallel
- gpu rendering

S(p) < p
usually things follow sublinear speedup due to numerous factors
- idle time due to load imbalance
- overhead due to comms
- idle time from sync
- extra computation in the algorithm of parallel programs
- other

S(p+1) < S(p)
slowdown
- overheads increase with processor count, but work is O(n)
- contention for a resource depends on p
	- for example, in shared memory there is a critical section that needs to be read by processors. more processors need to line up to read it

S(p) > p is not possible; over 100 percent efficiency

---

### Gene Amdahl's law

the speedup of a prgm is limited by its sequential portion
$$
$$
$$
S(p) - T_1/T_p ≤ T_1/(xT_1/p+(1-x)T_1)
$$
$$
\lim_{p \to \infty}S(p) ≤ \frac{1}{1-x}
$$
where x is the parallelizable part of the program