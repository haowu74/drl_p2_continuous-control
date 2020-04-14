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
Episode 1	Score: 0.64	Average Score: 0.64
Episode 2	Score: 1.59	Average Score: 1.12
Episode 3	Score: 1.76	Average Score: 1.33
Episode 4	Score: 2.20	Average Score: 1.55
Episode 5	Score: 2.51	Average Score: 1.74
Episode 6	Score: 3.57	Average Score: 2.05
Episode 7	Score: 4.43	Average Score: 2.39
Episode 8	Score: 5.40	Average Score: 2.76
Episode 9	Score: 7.24	Average Score: 3.26
Episode 10	Score: 7.28	Average Score: 3.66
Episode 11	Score: 8.63	Average Score: 4.11
Episode 12	Score: 7.87	Average Score: 4.43
Episode 13	Score: 8.77	Average Score: 4.76
Episode 14	Score: 11.54	Average Score: 5.25
Episode 15	Score: 11.58	Average Score: 5.67
Episode 16	Score: 11.71	Average Score: 6.05
Episode 17	Score: 13.56	Average Score: 6.49
Episode 18	Score: 12.28	Average Score: 6.81
Episode 19	Score: 12.72	Average Score: 7.12
Episode 20	Score: 12.02	Average Score: 7.37
Episode 21	Score: 13.46	Average Score: 7.66
Episode 22	Score: 12.38	Average Score: 7.87
Episode 23	Score: 14.22	Average Score: 8.15
Episode 24	Score: 12.08	Average Score: 8.31
Episode 25	Score: 12.95	Average Score: 8.50
Episode 26	Score: 13.57	Average Score: 8.69
Episode 27	Score: 16.68	Average Score: 8.99
Episode 28	Score: 16.18	Average Score: 9.24
Episode 29	Score: 16.38	Average Score: 9.49
Episode 30	Score: 16.13	Average Score: 9.71
Episode 31	Score: 16.40	Average Score: 9.93
Episode 32	Score: 17.92	Average Score: 10.18
Episode 33	Score: 19.19	Average Score: 10.45
Episode 34	Score: 19.67	Average Score: 10.72
Episode 35	Score: 18.94	Average Score: 10.96
Episode 36	Score: 18.51	Average Score: 11.17
Episode 37	Score: 22.04	Average Score: 11.46
Episode 38	Score: 20.99	Average Score: 11.71
Episode 39	Score: 22.13	Average Score: 11.98
Episode 40	Score: 24.57	Average Score: 12.29
Episode 41	Score: 21.37	Average Score: 12.51
Episode 42	Score: 23.48	Average Score: 12.78
Episode 43	Score: 24.87	Average Score: 13.06
Episode 44	Score: 23.94	Average Score: 13.30
Episode 45	Score: 23.99	Average Score: 13.54
Episode 46	Score: 25.08	Average Score: 13.79
Episode 47	Score: 24.07	Average Score: 14.01
Episode 48	Score: 24.02	Average Score: 14.22
Episode 49	Score: 24.43	Average Score: 14.43
Episode 50	Score: 26.16	Average Score: 14.66
Episode 51	Score: 26.26	Average Score: 14.89
Episode 52	Score: 24.97	Average Score: 15.08
Episode 53	Score: 23.84	Average Score: 15.25
Episode 54	Score: 26.52	Average Score: 15.46
Episode 55	Score: 26.92	Average Score: 15.67
Episode 56	Score: 25.50	Average Score: 15.84
Episode 57	Score: 27.90	Average Score: 16.05
Episode 58	Score: 27.56	Average Score: 16.25
Episode 59	Score: 28.02	Average Score: 16.45
Episode 60	Score: 30.89	Average Score: 16.69
Episode 61	Score: 30.88	Average Score: 16.92
Episode 62	Score: 30.54	Average Score: 17.14
Episode 63	Score: 29.95	Average Score: 17.35
Episode 64	Score: 30.98	Average Score: 17.56
Episode 65	Score: 31.38	Average Score: 17.77
Episode 66	Score: 30.10	Average Score: 17.96
Episode 67	Score: 31.67	Average Score: 18.16
Episode 68	Score: 29.96	Average Score: 18.34
Episode 69	Score: 28.51	Average Score: 18.49
Episode 70	Score: 31.49	Average Score: 18.67
Episode 71	Score: 31.63	Average Score: 18.85
Episode 72	Score: 30.79	Average Score: 19.02
Episode 73	Score: 31.46	Average Score: 19.19
Episode 74	Score: 32.82	Average Score: 19.37
Episode 75	Score: 33.47	Average Score: 19.56
Episode 76	Score: 33.89	Average Score: 19.75
Episode 77	Score: 33.46	Average Score: 19.93
Episode 78	Score: 34.05	Average Score: 20.11
Episode 79	Score: 32.27	Average Score: 20.26
Episode 80	Score: 33.69	Average Score: 20.43
Episode 81	Score: 34.25	Average Score: 20.60
Episode 82	Score: 34.60	Average Score: 20.77
Episode 83	Score: 34.25	Average Score: 20.93
Episode 84	Score: 33.79	Average Score: 21.09
Episode 85	Score: 34.24	Average Score: 21.24
Episode 86	Score: 36.13	Average Score: 21.42
Episode 87	Score: 35.22	Average Score: 21.57
Episode 88	Score: 34.79	Average Score: 21.72
Episode 89	Score: 33.55	Average Score: 21.86
Episode 90	Score: 34.12	Average Score: 21.99
Episode 91	Score: 35.28	Average Score: 22.14
Episode 92	Score: 34.92	Average Score: 22.28
Episode 93	Score: 33.30	Average Score: 22.40
Episode 94	Score: 32.59	Average Score: 22.51
Episode 95	Score: 33.65	Average Score: 22.62
Episode 96	Score: 33.84	Average Score: 22.74
Episode 97	Score: 33.35	Average Score: 22.85
Episode 98	Score: 33.67	Average Score: 22.96
Episode 99	Score: 34.01	Average Score: 23.07
Episode 100	Score: 34.22	Average Score: 23.18
Episode 100	Average Score: 23.18
Episode 101	Score: 34.29	Average Score: 23.52
Episode 102	Score: 34.02	Average Score: 23.84
Episode 103	Score: 32.44	Average Score: 24.15
Episode 104	Score: 32.37	Average Score: 24.45
Episode 105	Score: 34.34	Average Score: 24.77
Episode 106	Score: 33.77	Average Score: 25.07
Episode 107	Score: 33.57	Average Score: 25.36
Episode 108	Score: 33.20	Average Score: 25.64
Episode 109	Score: 33.73	Average Score: 25.91
Episode 110	Score: 33.58	Average Score: 26.17
Episode 111	Score: 31.92	Average Score: 26.40
Episode 112	Score: 32.85	Average Score: 26.65
Episode 113	Score: 32.77	Average Score: 26.89
Episode 114	Score: 31.90	Average Score: 27.10
Episode 115	Score: 33.63	Average Score: 27.32
Episode 116	Score: 32.45	Average Score: 27.52
Episode 117	Score: 31.98	Average Score: 27.71
Episode 118	Score: 32.97	Average Score: 27.91
Episode 119	Score: 32.40	Average Score: 28.11
Episode 120	Score: 32.09	Average Score: 28.31
Episode 121	Score: 31.88	Average Score: 28.50
Episode 122	Score: 32.02	Average Score: 28.69
Episode 123	Score: 32.13	Average Score: 28.87
Episode 124	Score: 32.33	Average Score: 29.07
Episode 125	Score: 31.61	Average Score: 29.26
Episode 126	Score: 31.03	Average Score: 29.44
Episode 127	Score: 31.47	Average Score: 29.58
Episode 128	Score: 31.82	Average Score: 29.74
Episode 129	Score: 29.77	Average Score: 29.87
Episode 130	Score: 31.11	Average Score: 30.02

Environment solved in 30 episodes!	Average Score: 30.02
![Plot of Rewards][image1]


## Ideas of Future Work
The training is quite even with GTX1080Ti external GPU. That made it hard to tune different hyperparameters. I found the TAU plays the important role in the training convergency / speed. Setting TAU to 0.01 seems satisfying. In the future, maybe I can explore more with a PC with internal GTX card. Other algorithms such as PPO (Proximal Policy Optimization) or D4PG(Distributed Distributional Deterministic Policy Gradients) can also be tried.  