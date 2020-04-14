# Project Report
This project utilised the DDPG (Deep Deterministic Policy Gradient) to train the 20 agents.
## State and Action Space
In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector must be a number between -1 and 1 (a continuous space).
## Learning algorithm
The DDPG algorithm is implemented in the class Agent in the notebook. All the 20 agents share the same weights, so they are saved in class member which is shared by all the instances (in this case agents).   

## Hyperparameters
BUFFER_SIZE (int): The size of replay buffer, set to 100,000
BATCH_SIZ (int): The size of mini batch, set to 128
GAMMA (float): The discount factor, set to 0.99
TAU (float): The factor for soft update of target parameter, set to 0.01
LR_ACTOR (float): The learning rate of the actor, set to 0.0001
LR_CRITIC (float): The learning rate of the critic, set to 0.0001
WEIGHT_DECAY (float): L2 weight decay
N_LEARN_UPDATES (int): The number of learning updates
N_TIME_STEPS (int): Time step do update

## Neural Network
Actor and Critic network models were defined in the class Actor and Critic in the notebook. 

The Actor networks utilised two fully connected layers with 384 and 128 units with relu activation and tanh activation for the action space. The network has an initial dimension the same as the state size.

The Critic networks utilised two fully connected layers with 384 and 128 units with leaky_relu activation. The critic network has  an initial dimension the size of the state size plus action size.

## Plot of Rewards
[image1]:./score.png
![Plot of Rewards][image1]

## Ideas of Future Work
The training is quite even with GTX1080Ti external GPU. That made it hard to tune different hyperparameters. I found the TAU plays the important role in the training convergency / speed. Setting TAU to 0.01 seems satisfying. In the future, maybe I can explore more with a PC with internal GTX card. Other algorithms such as PPO (Proximal Policy Optimization) or D4PG(Distributed Distributional Deterministic Policy Gradients) can also be tried.  