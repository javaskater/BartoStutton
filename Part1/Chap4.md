# p 97
## The DP algorithm
* V id a function from State dimension to R (the value of S is a rela)
# p 98
* the probability of accessing next state doing the right move is given 1
  * shouldn't it be between 0 and 1  (0,1]?
* the probaility of accessing a not neighbouring state is 0
* définition of vpi int that case (r=-1) 
  * the negative value of all steps accessing to one final state...
## Exercise 4.1 and the Python code
* [The Exercise 4.1 Python code on Github](https://github.com/LyWangPX/Reinforcement-Learning-2nd-Edition-by-Sutton-Exercise-Solutions/blob/master/Chapter%204/Ex4.1.py)
* The main problem of this code is determining the neighbouring states 
  * if we the neighbour is 15 or 0 the result will be 0
  * we never start from 0 or 15
* The calculation is Sum(neighbouring states)*0.25 -1 (-1 = 4*0.25*-1) 
  * here p(s',r|s,a) = 1 if the state is accessible, 0 elsewhere... 
## Exercise 4.2 and the Python code
* same code as 4.1
## Exercise 4.3
* return to the definitions __equation 3.14 p 81__
  * the exercise 3.12 don't demonstrate anything they just state  
# p 100
## demonstration's question:
* E = Epi because At = pi'(s)
* I did not know that equivalence ....
* $q_{k+1}(s, a) = \sum_{s', r} p(s', r | s, a)\left[r + \gamma \sum_{a'} \pi(a'|s)q_k(s', a')\right]$

# Back to the reading of BartonStutton
* What is the difference between Q and V
[Datascience StackExchange](https://datascience.stackexchange.com/questions/9832/what-is-the-q-function-and-what-is-the-v-function-in-reinforcement-learning) is a nice place to exchange, you ca write formulas in Latex

# p 102
## Policy iteration
* The alogorithm is very interesting. We have 2 loops, 
  * one for policy evaluation which returns _V(s)_ for each State s belonging to S for a policy $\pi$ 
  * one for policy $\Pi(s)$ whic is the choice of a for each s $\in$ S
    * if for one state the choice of a change (compared to old_action whic was $\pi(s)$ before the new calation) then $\Pi$ is said not to be stable and is replaced by the new Policy
* don't forget the difference between __V__ and __q__ [Response 57 of that Stack Exchange Post](https://datascience.stackexchange.com/questions/9832/what-is-the-q-function-and-what-is-the-v-function-in-reinforcement-learning)
* the solution of the exercises is directly under */home/jpmena/CONSULTANT/IA/Reinforcement-Learning-2nd-Edition-by-Sutton-Exercise-Solutions/Chapter 4/Solutions_to_Reinforcement_Learning_by_Sutton_Chapter_4_r5.pdf*

# 105 Value Iteration
## Algorithm
* Delta is resetted to zero avec the evaluation of each s $\in$ S
* We stop when the mas of the difference between the old sweep and the new sweep is lower than $\delta$

# 108
* MDP means Markov Decision Process
* DP means : Dynamic programming
# 109
* [GPI for Markov Decision Process](https://arxiv.org/abs/2206.05809) G stands not for Geometric but for Generalized !!!
## 110 Conclusion of chapter 4
[Dynamic PRogramming in Markov Decision Process is explained from page 15 of that research paper](http://researchers.lille.inria.fr/~lazaric/Webpage/MVA-RL_Course14_files/notes-lecture-02.pdf)

## 111
* The definition of _boostraping_
> That is, they update estimates on the basis of other estimates. We call this general idea bootstrapping.


