# Windy Grid World + King's Moves Using Reinforcement Learning
<br />


Useful bits of knowledge before start:
+ First of all, please read The Reinforcment Learning book in second edition from this link ["Sutton & Barto" - ``Especially page 130 & 131`` ](https://www.dbooks.org/reinforcement-learning-0262039249/). 
+ There are absolutely free resources for Reinforcement Learning in [here](https://medium.com/datadriveninvestor/absolutely-free-resources-for-reinforcement-learning-d16a5230cb0f).
+ Also if you want to work with MATLAB you can read this link [RL with MATLAB](https://github.com/MinaR-90/Self-Driving-Cab-Using-Reinforcement-Learning/issues/1) too. 
<br /><br /><br />


##  Games' Description

Shown inset below is a standard gridworld, withstart and goal states, but with one difference: there is a crosswind running upwardthrough the middle of the grid. The actions are the standard four—up, down, right,andleft—but in the middle region the resultant next states are shifted upward by a“wind,” the strength of which varies from column to column. The strength of the wind is given below each column, in num-ber of cells shifted upward.


<p align="center">
<img width="600" height="370" alt="wind1" src="https://user-images.githubusercontent.com/71558720/103968491-f6280f80-5131-11eb-8589-fced916613db.PNG"><br /><br />
<p align="center">

We are to implement several algorithms to solve this problem like:
- Sarsa
- Q-learning
- Sarsa(𝜆)
- Q(𝜆)
<br /><br />


We compare all solutions in terms of the optimal policies and episodes necessary for convergence. Also we select the best values for 𝜀 and 𝛼 for each case and we explain If they are different.



















