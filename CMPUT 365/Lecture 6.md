previously...

markov decision processes, doing an example of mud and getting to goal in a maze.
what stochastic means
agent-environment interaction

### Agent-Environment Boundary

where is it? it depends...

>the boundary represents the limit of the agent's *absolute control*, not of it's knowledge.

e.g. agent in a car: is it the steering wheel? is it the entire car? the wheels? or the driver?

formalizing the interface:

probability of s' and reward given previous state and action is defined as the probability of state now is s' and reward now is r given previous state is s and previous action is a
in the mud maze problem, two rewards and eight states.

later we don't really care about the reward anymore.
probability of s' given state s and action a is defined as the probability of state now is s' given the previous state is s and the previous action is a.
the reward itself given state and action is thus defined as the expectation of the present reward given the previous state is s and the previous action is a.

sum of r in state multiplied by the sum of the probability that we will observe that state

stuck in the mud:
$$
1*0.1+0*0.9
$$
expected value is point 1.


### The Markov Property

>the future is independent of the past given the present

for example, a game of chess: all the information required is provided in the present state. we do not need any more information from the past to make the best move for the next state.

we say that the combination of states, actions, and rewards has the markov property if for any time step, state, action, and reward holds that the next time step only relies on the previous time step.

considering the whole history would not change the probabilistic predictor.

>the state representation does not tell all that we need to know, only that we haven't forgotten everything we need to know.


### Reward Hypothesis

any goal that we want our agent to have, we can design a reward function for it.
not necessarily the easiest way but it is a way to capture and communicate a goal.

ultimate goal: maximize the sum of rewards in the agent's lifetime

gamma is introduced as discount. if it's less than 1, we are basically reducing the reward the longer the agent takes to reach the goal prioritizing present reward rather than future. e.g. inflation; a dollar today is worth more than a dollar in the future.

rewards are not always monetary or concrete. things like feelings and subjective things account for reward maximization too. like if your program's goal is to maximize internal happiness and robbed a bank and got you a billion dollars, the guilt and shame would factor into the reward since it reduces internal happiness.