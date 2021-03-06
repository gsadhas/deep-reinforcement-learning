# Problem statement

Train a double-jointed arm that can move to target locations. The goal is the agent must maintain its position at the target location for as many time steps as possible.

![Environment](../images/reacher.gif)

# Environment 

We use [reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment which is based on Unity ML-agents. The project environment is provided by Udacity and it is similar to the Reacher environment on the Unity ML-Agents GitHub page.
* Agent Reward Function (independent) - a reward of +0.1 is provided for each step that the agent's hand is in the goal location
* Behavior Parameters
	* Vector Observation space - 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm
	* Vector Action space - (continuous) each action is a vector with four numbers, corresponding to torque applicable to two joints 
	* Visual Observations: None

Every entry in the action vector should be a number between -1 and 1. 

# Solution
This is an episodic task. We can solve the environment in one of the two ways,
* Version 1 - Train only one agent. In order to solve the environment, the agent must get an average score of +30 over 100 consecutive episodes. In this Github repo, the environment is solved using Deep Deterministic Policy Gradients [(DDPG)](https://arxiv.org/abs/1509.02971) algorithm.
	* How DDPG works
		* DPPG is an actor-critic network we use to mitigate the limitation of Deep Q Networks (DQN). DQN is not good for continuous action space
		* It uses actor and critic networks. Actor network approximates the optimal policy to output best believed action for the given state. Critic network evaluates the optimal action value function using the best believed action from the actor network.
		* DDPG uses two copies of network weights for both actor and critic, one for regular network and another one for target network. Both actor and critic has one regular network and one target network. We train the regular network, and use the target network for prediction to stablize the training.
		* DDPG uses two main components, soft updates and replay buffer. Through soft updates, target network is updated with regular network weights i.e ~ 0.01% of regular network weights are blended into target networks.
	
* Version 2 - Train 20 agents in parallel (TODO)

# Installation requirements
1. This repo is built on Python 3.6 and PyTorch 0.4. Please refer [this link](https://github.com/udacity/deep-reinforcement-learning#dependencies) to set up your environment
2. Install the [Unity environment](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Installation.md)
3. Setting up the environment
	* The environment can be downloaded from one of the links below for all operating systems
		* Linux: click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
		* Mac OSX: click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
		* Windows (32-bit): click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
		* Windows (64-bit): click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)
		* For AWS: To train the agent on AWS (without [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), use [this](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) link to obtain the "headless" version of the environment. The agent can not be watched without [enabling a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), but can be trained. (To watch the agent, one can follow the instructions to enable a virtual screen, and then download the environment for the Linux operating system above.)
	* Unzip the downloaded zip file

4. Clone this repo


# How to run
Please refer the [Continuous_Control.ipynb](Continuous_Control.ipynb) notebook instructions to run the project. You need to update the UnityEnvironment() function call to read the enironment file that you downloaded from the above step #3

# Future work
* Max-out the timesteps (i.e infinite while loop) for each episode instead of using max_t=1000 timesteps
* Experiment with other hyperparameters other than LR, batch size and noise, and run hyperparameter search
* Train multi-agents to solve the environment (Solution - Version 2)
