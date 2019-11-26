# Problem statement
Train an agent to play tennis. In this environment, two agents control rackets to bounce a ball over a net. The goal of each agent is to keep the ball in play.

![tennis](../images/tennis.png)

# Environment

We use [Tennis](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis) environment which is based on Unity ML-agents. The project environment is provided by Udacity and it is similar to the Tennis environment on the Unity ML-Agents GitHub page.
- Agent reward function - If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. 
- Behavior Parameters
  - Vector Observation space - 8 variables corresponding to the position and velocity of the ball and racket
  - Vector Action space - (continuous) action space of size 2 corresponding to movement toward (or away from) the net, and jumping
  - Visual Observations: None

This task is an episodic task. The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5.

# Getting started
1. This repo is built on Python 3.6 and PyTorch 0.4. Please refer this [link](https://github.com/udacity/deep-reinforcement-learning#dependencies) to set up your environment
2. Download the environment
  - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
  - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
  - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
  - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)
  
  (For Windows users) Check out this [link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

  (For AWS) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux_NoVis.zip) to obtain the "headless" version of the environment. You will not be able to watch the agent without enabling a virtual screen, but you will be able to train the agent. (To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the Linux operating system above.)
 3. Clone this project repo
 
 # How to run
Please refer to [tennis_notebook.ipynb](tennis_notebook.ipynb) notebook and follow the instructions. You need to update the UnityEnvironment() function call to read the enironment file that you downloaded. The notebook also has information about the network, hyer-parameters and future work.
 
