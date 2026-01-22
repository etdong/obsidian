### Fault tolerant design

Previously...
error budget
reducing fault frequency
	upgrading hardware
	improving software (too late)

fault tolerance techniques
- error detection
- error diagnosis
- error confinement
- error recovery

### Fault tolerant strategies

**backward error recovery**:
	rolling back the system to a non-error state.
	for critical and uncorrectable faults and in safety-critical systems

e.g. payment systems when payments fail, apache hadoop rolling back to checkpoints when nodes fail, cloud based virtual machines using snapshots

recovery states are automatically saved at predetermined checkpoints.
during rollback, we check with requests and continue rolling back until something works.

advantages:
	we have no knowledge on the errors
	generalizable solution
	perfect for faults that are arbitrary or unpredictable

disadvantages
	requires significant resources
	requires identification of safe states
	no guarantee the error will not return


**forward error recovery**:
	correct/fix and push through the error state.
	for minor and correctable faults

e.g. ecommerce system failed operation without having to redo previous steps, data transmission (hamming codes), autonomous cars using redundant sensors to push through failures and continue driving

the system will correct or build an error free state with error compensation for corrupted or missing data. 

error compensation uses alternative systems to continue to run in a degraded mode without correcting or rolling back the system.

1. damage assessment
2. damage control
3. error correction

advantages:
	more efficient use of time and resources

disadvantages:
	specific design
	time and cost depends on the damage
	not applicable for unpredictable errors


different families of fault tolerance:

single version techniques:
	expecting interruption of normal operation to handle abnormal response. prevents system degradation.
e.g. 
interface exception: incorrect or unexpected input
local exceptions: errors within a single component due to its internal logic
failure exceptions: failures in external components and subsystems, etc

multi version techniques:

e.g.
- distributed systems use replication and load balancing for reliability
- aerospace use triple modular redundancy (N version programming)
- ATMs operating in offline mode with limited functionality
- railway signaling systems
- autonomous cars with redundancy

**recovery blocks:**
	the entire system are compartmentalized and treated as fault-recoverable blocks
	uses backward error recovery
	operates with an acceptance test, whether the block works with versions

1. run the primary version for the acceptance test
2. if the primary version fails, roll back
3. run the next version for the same acceptance test until a good version is found
4. if all fail, the system fails

cons:
	reliability relies on test coverage and quality
	state saving is resource heavy
	acceptance needs to be small and fast to execute (faster than the function itself)
		optimization problem. needs to be small, fast, and accurate
	acceptance test is ad-hoc
		if comprehensive tests exist, the faults would have already been fixed


**N-version programming**:
	concurrently execute N versions of the function and return the results based on voting of the individual outputs.
	forward error recovery

two main components of n-version programing
- versions
- voting

intuition is that we have many teams of devs working on the same software. if one version fail, we can use others as backups. low probability of two or more versions with faults.

technique depends on design diversity though. may lead to specification or design errors.

N version is more applicable than recovery blocks due to concurrent execution. recovery blocks also assume that a single acceptance test is enough to test a system.


**N self-checking programming**:

combines recovery blocks and n version programming together.

executes N versions concurrently or sequentially, runs their own corresponding acceptance test, then run the voter and return on majority agreement.

cons: a LOT more overhead than n-version or recovery blocks.
	extra efforts in deriving individual acceptance tests


multi version techniques have high dev cost, scalability issues, difficulty in maintenance and documentation, etc


### Fault Removal
improve the system by detecting faults through debugging and testing and removing them before they're a problem.