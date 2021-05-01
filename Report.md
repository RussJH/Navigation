# Navigation Project Report


For instructions to run see [README.md](./README.md)

## Implementation Details

The Project consists of three main files as well as 

    - Agent.py          -- Implementation of a Deep Q Learning Agent
    - Model.py          -- Q Network Mdoel
    - ReplayBuffer.py   -- Double ended Queue with random sampling methods to store the learning experniences

### Learning Algorithm

### Hyper Parameters

### Nerual Network

## Plot
 The figure below is the plot of the rewards over runs during the training episodes

 ![Plot of rewards during training](Images/learning.png)
 > * Episode 100	Avg Score: 2.75
 > * Episode 200	Avg Score: 8.24
 > * Episode 300	Avg Score: 12.78
 > * Episode 400	Avg Score: 13.82
 > * Episode 500	Avg Score: 14.39
 > * Episode 600	Avg Score: 16.23
 > * Episode 700	Avg Score: 16.26
 > * Episode 800	Avg Score: 16.78
 > * Episode 900	Avg Score: 16.81
 > * Environment solved in 908 episodes, Avg Score: 17.03
 
 Running the Agent 100 times, once the environment was solved

 ![Plot of rewards solved](Images/solved-plot.png)
 > * Average Score: 16.91

## Future work