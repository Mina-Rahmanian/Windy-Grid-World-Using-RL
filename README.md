# Windy Grid World + King's Moves Using Reinforcement Learning
<br />


Useful bits of knowledge before start:
+ First of all, please read The Reinforcment Learning book in second edition from this link ["Sutton & Barto" - ``Especially page 130 & 131`` ](https://www.dbooks.org/reinforcement-learning-0262039249/). 
+ There are absolutely free resources for Reinforcement Learning in [here](https://medium.com/datadriveninvestor/absolutely-free-resources-for-reinforcement-learning-d16a5230cb0f).
+ Also if you want to work with MATLAB you can read this link [RL with MATLAB](https://github.com/MinaR-90/Self-Driving-Cab-Using-Reinforcement-Learning/issues/1) too. 
<br /><br /><br />


##  Games' Description


+ **PART 1- WindyGrid World**: Shown inset below is a standard gridworld, withstart and goal states, but with one difference: there is a crosswind running upwardthrough the middle of the grid. The actions are the standard four—up, down, right,andleft—but in the middle region the resultant next states are shifted upward by a“wind,” the strength of which varies from column to column. The strength of the wind is given below each column, in num-ber of cells shifted upward.


<p align="center">
<img width="580" height="350" alt="wind1" src="https://user-images.githubusercontent.com/71558720/103968491-f6280f80-5131-11eb-8589-fced916613db.PNG"><br /><br />
<p align="center">

We are to implement several algorithms to solve this problem like:
- Sarsa
- Q-learning
- Sarsa(𝜆)
- Q(𝜆)
<br /><br />


We compare all above solutions in terms of the optimal policies and episodes necessary for convergence. Also we select the best values for 𝜀 and 𝛼 for each case and we explain why!? If they are different. <br /><br />



+ **PART 2- windy gridworld task with King’s moves**: We re-solve the windy gridworld task plus ``King’s moves`` assuming that the effect of the wind, if there is
any, is stochastic, sometimes varying by 1 from the mean values given for each column. That is, a third
of the time we move exactly according to these values, as in the previous exercise, but also a third of
the time we move one cell above that, and another third of the time we move one cell below that.

``For example``; if we are one cell to the right of the goal and we move left, then one-third of the time we
move one cell above the goal, one-third of the time we move two cells above the goal, and one-third of
the time we move to the goal. <br /><br />


### Questions
1) Comparisons of solutions & Implementation of all algorithms for the second case (stochastic wind) 
2) Comparisons of solutions for the stochastic case  <br /><br />



********************************************************

# Solution


### Introduction

In this case the methods are tested assuming 4 actions are permitted. The following parameter values are
selected: ``α = 0:1``, ``ϵ = 0:01``, ``γ = 0:9``, ``λ = 0:8``. Starting from the point (4,1), we should rich the goal state (4,7)
via the optimal policy. We compare the result with the example 6.5 result given in the book.<br />

### 1) Graphical results


The algorithms is run for 1000 episodes. The ``α``, ``ϵ`` values are selected such that the learning is performed
leading to the shortest path in time steps as close as to the min time step (15). Smaller ``ϵ`` is preferred to let
the algorithm to exploit the best action more frequently. This ensures finding the optimal path faster. For the
learning rate, if it is too high learning happens faster but from a point it is saturated and no further policy
improvements occur (the graph slope does not change any more). Smaller learning rate leads to continuous
learning causing a convex graph which shows the slope increases but require more time. This convexity is
clearer in the SARSA and Q-Learning methods. The effect of parameters is given in fig 6 as well which is
indeed the main reason of selecting this values.


The Episode-Time step plot for each method is given in fig 1-4. In all cases, the optimal policy converges to
the shortest path which is shown in right part. Considering the average number of time steps for the last 100
episodes in SARSA case is around 17 steps with a slightly improvements in Q-learning (the slopes are almost
the same). As depicted in the right plots, starting from state (4,1) and following the arrows in the optimal
policy manner and considering the effect of wind in each column, we can verify that the obtained policy is the
same as the book until it reaches to the Goal point .


<p align="center">
<img width="890" height="750" alt="graph1" src="https://user-images.githubusercontent.com/71558720/104032529-476ce900-519c-11eb-957e-6273f6a73b2f.png"><br /><br />
<p align="center">


For the eligibility trace version, λ = 0:8 is selected. This value is selected such that its multiplication with 
 is not too small to have a better short term memory. If γ is close to 1, then the trace does not change. When
we apply the eligibility methods, as shown in Fig 3 and 4, the average number of steps to reach to the goal
decreases. This illustrates the advantage of this methods. That is mainly because in the eligibility trace more
weight is given to the most recent experiences that have more effects on reaching to the goal. Therefore, it
gives a better performance.



<p align="center">
<img width="890" height="750" alt="graph2" src="https://user-images.githubusercontent.com/71558720/104032943-e0036900-519c-11eb-8cea-4e760c65d795.png"><br /><br />
<p align="center">



### 2) Comparison and discussion



