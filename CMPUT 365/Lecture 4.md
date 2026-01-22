update rule:

new estimate = old estimate + step size * (target - oldestimate)

one of the key conditions to convergence in this formula is the step size. 

an extreme example is like having only movements in units of one kilometer and attempting to achieve meter level precision.

but if it decays too quickly, we reach an achilles problem.

the step size decay function must be unbounded over its sum to infinity, but converges over the sum of its squares to infinity.

constant step size is biased.
the first term will always exist in our estimate. although it gets smaller by (1-alpha)^n, it will never be zero. this is what it means to be biased.

although fixed step size is biased and not as accurate, it is useful for non-stationary problem.

### Optimistic uncertainty
initialize Q0 to an optimistic overestimation of it's true value.
we either maximize reward or learn from it. we can treat Q0 as a hyperparameter.
we can transform the reward and the initialization to achieve the same effect, as long as the relative distance is preserved.

upper confidence bound with high probability in bandits. basically pick the arm that has the largest possible bound.

pessimism doesn't work because we are trying to optimize for greed. since anything is better than negative infinity it will choose any option that isn't worse and not explore.

