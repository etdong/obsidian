## Bandits

used in things like recommenders

actions have immediate consequences

define
$$
q^*(a) = exists [R_t st A_t=a]
$$
$$
A_t = argmax_aQ_t(a)
$$
we dont know q* so we use an estimate, $Q_t$
$A_t$ is a greedy action, also called exploitation

reinforcement learning deals with this human issue: exploration vs exploitation

### Exploration

how can we explore?

- randomly (epsilon greedy)
- optimism in uncertainty
- uncertainty
- novelty/boredom/surprise
- temporally-extended exploration

this course is **not** about exploration. we are just going to do random exploration.

sometimes we decay epsilon, but might not be good for problems that could change
basically this is our exploration term for gradient stochastic descent. searching for optimums

**important**
new estimate = old estimate + stepsize[target - oldestimate]

stepsize is alpha, 1/n as time goes on to reduce movement as samples increase

