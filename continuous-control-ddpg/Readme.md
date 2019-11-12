# Problem statement

Train a double-jointed arm that can move to target locations.

* Goal - the agent must maintain its position at the target location for as many time steps as possible

# Environment 

The environment is based on Unity ML-agents. The project environment is provided by Udacity and it is similar to the Reacher environment on the Unity ML-Agents GitHub page.


* Agent Reward Function (independent) - a reward of +0.1 is provided for each step that the agent's hand is in the goal location

* Behavior Parameters
	* Vector Observation space - 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm
	* Vector Action space - (continuous) each action is a vector with four numbers, corresponding to torque applicable to two joints 
	* Visual Observations: None

Every entry in the action vector should be a number between -1 and 1. 

# Solution
This is an episodic task. We can solve the environment in one of the two ways,
* Version 1 - Train only one agent. In order to solve the environment, the agent must get an average score of +30 over 100 consecutive episodes. In this Github repo, the environment is solved using Deep Deterministic Policy Gradients ![(DDPG)](https://arxiv.org/abs/1509.02971) algorithm.

* Version 2 - Train 20 agents in parallel (TODO)

# Installation requirements
1. This repo is built on Python 3.6 and PyTorch 0.4. Please refer ![this](https://github.com/udacity/deep-reinforcement-learning#dependencies) link to set up your environment
2. Install the ![Unity environment](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Installation.md)
3. Clone this repo


# How to run
Please refer the ![Continuous_Control.ipynb](Continuous_Control.ipynb) notebook instructions to run the project
