previously...
backward recovery
- incremental checkpointing and rolling back
forward recovery
- damage assessment, error confinement, state reconstruction
- basically fixing bugs
recovery blocks
- multiple implementations, choosing one that passes the tests
N-version programming
- concurrent running of versions and vote on the best version
N-self checking programming
- do an acceptance test on each version in parallel then vote on the best version


fault tolerant design
- maintaining high reliability by either reducing failures or minimizing service interruptions
	- failure detection and recovery, error correction
	- redundancy and graceful degradation




### Dependability

we want to give consumers the trust that our program is secure and reliable.
directly affects user experience; failures make users lose trust in the program and likely be rejected by the users.
maintenance cost also rises with a less reliable system.

**Fault removal** and **fault localization** pinpoint the location of the bugs in the code and fix them.
helps the developer to recover from bugs faster and reduce the impact to the consumer.
reduces the debugging time by reducing manual efforts

**Software faults:**
- error: a mistake in code
- fault: a defect in the code that can cause incorrect or unexpected results
- failure: when a system fails to perform it's required function

error -> fault -> failure


**rubber duck debugging** is just explaining every line of code simply to cover your own faults.


### Spectrum-based fault localization
lots of fault localization techniques. we are going to examine spectrum-based techniques and information retrieval based techniques

SBFL also known as statistical debugging uses results of test cases to identify the location of faults.

we can examine the most suspicious program elements by using the test coverage.

four steps:
1. run all tests
2. build the test execution profiles (how many tests are covering this statement?)
3. calc suspiciousness score
4. examine by suspiciousness ranking

for step 3:
$$
Ochiai(element) = ef/sqrt((ef+nf)*(ef+ep))
$$
where 
ef is number of failed tests
ep is number of passed tests
nf is number of failed tests that do not cover the element
np is number of passed tests that do not cover the element

ochiai doesn't use np.

we don't always need the calculation. basically just pick the statements that have more failing tests and less passing tests. those places are the most likely to have faults.

why is this useful?
this is a good estimation method to check where bugs are. this can be used for automating bug fixes.

some problems:
relies on good test coverage
tie issues
assumption that tests are perfect and not flaky



preview of next class:
### Information retrieval based fault localization
uses bug reports and the description/context to locate the fault.

3 steps:
1. preprocessing
2. construct vector space model
3. calculate similarity metrics

