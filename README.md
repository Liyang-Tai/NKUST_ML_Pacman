# NKUST_ML_Pacman

(1) Instruction

Download the reinforcement pack of Pacman game: http://ai.berkeley.edu/projects/release/reinforcement/v1/001/reinforcement.zip

Unzip the package and place mlLearningAgents.py inside the directory.

Run the training command in the directory. i.e. for 2000 runs of training and 10 runs of playing in a small grid, run:
python pacman.py -p QLearnAgent -x 2000 -n 2010 -l smallGrid

How to run command in directory: Shift + Right Click > Open in Powershell

!! Make sure to run in python 2 !!

(2)

New Pacman.ppt : Weekly Planning Report

pac_demo.mp4 : Demonstration video

(3) Credit

https://github.com/mandichen/Pacman_Qlearning

## Implementation of Q-learning
The structure of agent class is given: Function `getAction()` executes while the agent needs to take an action. Function `final()` is called at the end of every game.

The steps of implying Q-learning in a Pacman game:
1. initialize Q(s,a)
1. take a random action
1. update Q(s,a)
1. choose the action maximises Q or a random action according to Ɛ-greedy function
1. repeat step 3 and 4 until the game ends
1. update Q(s,a) where s is the last state before the end, a is the last action taken

For initiaization we need to add some attributes to the class:
* a dictionary for storing Q(s,a)
* a list records last state
* a list records last action
* a variable stores the score before last action

For storing Q(s,a), a handy structure called Counter can be found in util.py. We can make use of the function `argMax()` to return the action maximises Q.

Step 2-4 in Q-learning can be included in `getAction()` function. step 6 could be included in `final()` function.

`getAction()`:
* observe the reward of state
* update Q(s,a)
* Ɛ-greedy choose action
* update attributes
* return action

`final()`:
* observe reward
* update Q(s,a)
* reset attributes
