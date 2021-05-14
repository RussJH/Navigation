# Navigation Project Report

For instructions to run see [README.md](./README.md)

## Implementation Details

The Project consists of the following files:

    - Agent.py                  -- Implementation of a Deep Q Learning Agent
    - Model.py                  -- Q Network Mdoel
    - ReplayBuffer.py           -- Double ended Queue with random sampling methods to store the learning experniences
    - Navigation.ipynb          -- Jupyter notebook used to train the DQN Agent 
    - NavigationSolved.ipynb    -- Jupyter notebook used to run the trained DQN agent 100x and plot the results 


### Learning Algorithm and Neural Network

For this project we used a Deep Q-Network Learning Agent with a three layer QNetwork. The agent takes a state size and action size as well as seed (default 0) for the greedy policy random function. The agent implements a Deep Q-Network algoritm utilzing a PyTorch Linear (y=xA^T + b) tranformation and the three layer QNetwork. The first layer applies a linear transformation from the state dimensions to 64, the second layer is 64 x 64 and the third layer applies a linear transformation from 64 to the action dimensions. 

When chosing an action the Agent implements an epsilon greedy policy where epsilon starts at 1.0 with a floor of .01 and a decay rate of .995. As the agent steps through the actions it applies its experiences (states, actions, rewards and next states) after 4 steps chosen from the buffer. The agent estimates the action-value function by using the Bellman equation as an iterative update and utilzies PyTorch Adam optimizer to minimize losses. It then updates the model with the results a inerpolation paramter (tau) with a value of 1e-3 with the equation target  = tau * local + (1- tau)*target.

### Hyper Parameters
|Parameter| Value|
--- | --- |
Epsilon start | 1.0 |
Epsilon decay | 0.995 |
epsilon minimum | 0.01 |
Discount factor | 0.99 |
Soft update rate | 1e-3 |
Learing Rate | 5e-4 |
Replay buffer size | 1e5 |
Batch size | 64 |



## Plot
 The figure below is the plot of the rewards over runs during the training episodes

 ![Plot of rewards during training](Images/learning.png)
 > * Episode 100	Avg Score: 1.65
 > * Episode 200	Avg Score: 6.46
 > * Episode 300	Avg Score: 12.69
 > * Episode 400	Avg Score: 13.73
 > * Episode 500	Avg Score: 15.76
 > * Episode 600	Avg Score: 16.02
 > * Episode 700	Avg Score: 15.91
 > * Episode 800	Avg Score: 15.76
 > * Episode 900	Avg Score: 16.45
 > * Episode 1000	Avg Score: 16.73
 > * Agent Trained in 1000 episodes.	Avg Score: 16.73
 
 Running the Agent 100 times, once the environment was solved

 ![Plot of rewards solved](Images/solved-plot.png)
 > * Average Score: 16.91

## Future work

Some of the drawbacks of the implementation of the DQN in this project is that it has a limited number of experience tuples in memory, the sampling algorithm chooses them at random when performing the update action, and gives equal weight to all of the transitions. By implementing a better sampling algorithm which prioritizes transitions that learned the most when chosing experience tuples from memory, the agent could maximize the reward value with less fluctuations in the policy. 