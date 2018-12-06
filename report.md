This report contains additional details on the project.

# Collaboration and Competition

In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping.

The task is episodic, and in order to solve the environment, your agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). Specifically,

After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores. This yields a single score for each episode. The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5.

The learning algorith for this project was Deep Deterministic Policy Gradient for a Continuous Action-space. This work was introduced in the following paper: 

Continuous control with deep reinforcement learning
Timothy P. Lillicrap, Jonathan J. Hunt, Alexander Pritzel, Nicolas Heess, Tom Erez, Yuval Tassa, David Silver, Daan Wierstra
https://arxiv.org/abs/1509.02971

The team above summarized their work in this way:

"We adapt the ideas underlying the success of Deep Q-Learning to the continuous action domain. We present an actor-critic, model-free algorithm based on the deterministic policy gradient that can operate over continuous action spaces. Using the same learning algorithm, network architecture and hyper-parameters, our algorithm robustly solves more than 20 simulated physics tasks, including classic problems such as cartpole swing-up, dexterous manipulation, legged locomotion and car driving. Our algorithm is able to find policies whose performance is competitive with those found by a planning algorithm with full access to the dynamics of the domain and its derivatives. We further demonstrate that for many of the tasks the algorithm can learn policies end-to-end: directly from raw pixel inputs."

## Learning Algorithm

Here are some additional details of the application of the algorithm to this project.
* During training the overall simulation is limted to 5000 episodes of a maximum of 2000 time steps.  During each step the states, actions, rewards, next_states, and dones are added to a fixed size replay buffer.
* The project contains both a critic and and actor models.
    * The actor (policy) network maps states to actions.
    * The critic (value) network that maps (state, action) pairs to Q-values.
* In this sense the actor controls our actions and the critic can estimate how well we did.
* In this project, the weights are updated in the learn function after 20 stpes.  The learn function is called 10 times at this point so we see 10 weight updates (soft update) every 20 steps.
* Both the actor and critic have regular and target weights, the learn function mixes in the regualr network weights to the target weights. See the call to soft update model parameters using θ_target = τ*θ_local + (1 - τ)*θ_target.  This strategy leads to faster convergence.   

The following hyperparameters were used for the project:

```
BUFFER_SIZE = int(1e5)  # replay buffer size - orginal was 1e5
BATCH_SIZE = 512  # minibatch size - orginally was 128
GAMMA = 0.99  # discount factor
TAU = 1e-2  # for soft update of target parameters - orgial was 1e-2
LR_ACTOR = .001  # learning rate of the actor - orgial was 1e-4
LR_CRITIC = .001  # learning rate of the critic - orgial was 1e-2
WEIGHT_DECAY = 0  # L2 weight decay
```

## Plot of Rewards

After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores. This yields a single score for each episode. The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5.

![Plot of Rewards](https://github.com/bohoro/CollaborationAndCompetition/blob/master/plot/plot.jpeg?raw=true)

Problem solved in Episode 1375 with an Average Score: +0.50

## Ideas for Future Work

Implement the multi-agent actor-critic methods as introduced in the following paper:

Multi-Agent Actor-Critic for Mixed Cooperative-Competitive Environments
Ryan Lowe, Yi Wu, Aviv Tamar, Jean Harb, Pieter Abbeel, Igor Mordatch
https://arxiv.org/abs/1706.02275

The team above summarized their work in this way:

"We explore deep reinforcement learning methods for multi-agent domains. We begin by analyzing the difficulty of traditional algorithms in the multi-agent case: Q-learning is challenged by an inherent non-stationarity of the environment, while policy gradient suffers from a variance that increases as the number of agents grows. We then present an adaptation of actor-critic methods that considers action policies of other agents and is able to successfully learn policies that require complex multi-agent coordination. Additionally, we introduce a training regimen utilizing an ensemble of policies for each agent that leads to more robust multi-agent policies. We show the strength of our approach compared to existing methods in cooperative as well as competitive scenarios, where agent populations are able to discover various physical and informational coordination strategies."
