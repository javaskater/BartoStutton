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
[Datascience StackExchange](https://datascience.stackexchange.com/questions/9832/what-is-the-q-function-and-what-is-the-v-function-in-reinforcement-learning#:~:text=The%20V%20function%20states%20what,under%20the%20policy%20%CF%80%20is.) is a nice place to exchange, you ca write formulas in Latex
