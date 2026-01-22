### IR based fault localization
last time...
information retrieval 101
information redundancy
- this is the last module before midterm 1
term frequency
document frequency
inverse document frequency
- rarity of term within a collection of documents (globally)
tf-idf
- rarity of term across collection but often appears in individual documents


now...
we use some of the strategies talked about previously. our corpus/collection is now the source code and our queries are our bug reports.

steps
1. preprocessing
	- corpus and query construction
	- tokenize and clean
		- stopword removal
		- stemming
2. indexing with weighted tf-idf
	- build a vector space model. similar to llms
	- transforms the fault localization into a search problem
3. searching and compute cosine similarity scores
4. ranking based on similarity, higher score areas are more likely to contain faults

e.g.
bug report: "a problem with the classNotFound exception"
source code: "get classNotFound exception return exception"
assumption: no preprocessing needed.

vector representation:
bug = [1, 1, 1, 1, 1, 1, 0, 0]
source: [0, 0, 0, 0, 1, 2, 1, 1]

### Overview - Dependability
maintenance is part of the user requirements, including resolving faults in the system.
dependability
- impairments
	- faults
	- errors
	- failures
- atrributes
	- availability
	- reliability
- means
	- fault removal
		- testing
		- debugging
			- spectrum based fl
			- ir based fl
	- fault tolerance
		- software redundancy
			- recovery blocks
			- n version programming
			- n-self checking programming
all of these are fair game for the midterm except testing
finished the software side of reliability


### Information Redundancy
add information to original data to be able to recover it on partial loss.
things like parity bits.

a "code" when speaking on information redundancy is moreso the cryptographic definition rather than the software engineering definition.

there are two common forms in information redundancy: detection and correction code.

>code of length n is a set of n-tuples satisfying some wel-defined set of rules
>codeword is an element of the code that satisfies the rules
>a word is one that doesn't satisfy the rules.

errors is just loss of data in this context. losses of bits and burst errors