# Deep-Reinforcement-Learning-with-DDQN
Trial Environment - OpenAI Gym's Cartpole Environment (Implemented using PyTorch)

## What is DDQN?
A deep Q network (DQN) is a multi-layered neural network that for a given state 's' outputs a Q value for each action. The action with the best Q value is chosen as the action in the next step. Therefore the Q network tries to estimate the best possible action to choose in a given state. Since we always try to maximize the Q value the Q networks tend to have a problem of overestimating the Q value of a state. This causes the Q values to sometimes blow up to very large values.

A DDQN uses two different Q networks to overcome this problem. One of the networks is a copy of the other from T timesteps ago. The current (online) network is used to estimate the action to be taken while the old Q network is used to evaluate the action. Thus the Q value of the action is always lower than what would be obtained from the online network. The old Q network remains a periodic copy of the online Q network.

## Environment
A pole is attached by an un-actuated joint to a cart, which moves along a frictionless track. The system is controlled by applying a force of +1 or -1 to the cart. The pendulum starts upright, and the goal is to prevent it from falling over. <br>
<p align = "center">
  <img src = "/Images/dataset_1.png" height = 300>
</p>

## Results
A reward of +1 is provided for every timestep that the pole remains upright. The episode ends when the pole is more than 15 degrees from vertical, or the cart moves more than 2.4 units from the center. OpenAI Gym defines CartPole-v0 as being "solved" upon getting average reward of 195.0 over 100 consecutive trials.
The following graph shows the evaluation environment reward after every 1000 paramter updates. In the code, the parameters of the online Q network are updated at the end of every episode. However, the Q network can be updated at every step in every episode to yield faster convergence. <br>
<p align = "center">
  <img src = "/Images/result_1.png" height = 300>
</p>

<p align = "center">
<img src = "/Images/cartpole.gif">
</p>
