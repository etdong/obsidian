### Markov Decision Processes

basically agents will create a tree that summarizes the agent environment interactions. the tree aides in sequential decision making using probabilities.

we are maximizing total estimated future reward by taking into account the state that the agent is in.

this expected return is calculated by breaking up a task into episodes, where each episode is similar to a game of chess -- a sequence of actions that lead to a termination.

### Reward Hypothesis
give a man a fish:
	standard programming. tell the agent exactly what we want it to do.
	unable to adapt.
teach a man to fish:
	supervised learning.
give a man a taste for fish:
	reinforcement learning. give the agent a problem and they will solve it for themself

>Intelligent behavior arises from the actions of an individual seeking to maximize its received reward signals in a complex and changing world.

goal setting and rewards is tricky when there's no common currency. we can assign arbitrary reward numbers to goals and intermediate tasks.

rewards can be derived from example, inverse reinforcement learning, or evolutionary optimization/meta RL

there are also some challenges to the hypothesis. e.g. minimizing negative outcomes instead of maximizing reward or in a song recommendation system where "optimizing" would be just playing your favorite song over and over.

>we could add human intervention to minimizing negative outcomes and add weight to the negatives.

>we could add a reward space where playing the same song over and over reduces the reward -- similar to only drinking when we're thirsty.


