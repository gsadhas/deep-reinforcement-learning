# Problem statement
We need to train an agent to navigate and collect bananas in a large square world. The environment has two types of bananas, yellow and blue. Agent is rewarded with score +1 if it collects a yellow banana, and score -1 if it collects a blue banana. The agent task is episodic.

![Problem](https://user-images.githubusercontent.com/10624937/42135619-d90f2f28-7d12-11e8-8823-82b970a54d7e.gif)

The state space has 37 dimensions and contains agent's velocity along with ray-based perception of objects around the agent's forward direction. Agent can perform four discrete actions,
 * 0 - to move forward
 * 1 - to move backward
 * 2 - to turn left
 * 3 - to turn right

If the agent gets an average score of +13 over last 100 episodes, we will consider the environemnt is solved.

# Dependencies
1. We need to download the environment to run the project. This repo has source code to train the agent without real-time visualization. Please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip) to download the environment. Unzip the downloaded environment and keep it in the root level.
2. Please follow the installation steps to set up Unity ML-Agents at [this link](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Installation.md)
3. Python libraries and versions used in the project are availabe in requirements.txt file

# How to run
Please check Navigation.ipynb to start training your agent.
