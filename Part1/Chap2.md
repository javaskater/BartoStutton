# Introdution p 45
* The bandit problem is a one state problem
# very important p 49
* we take the sum of rewards prior to t
  * Qt is a scalar (beacause of a division)
  * do we sum the Ri all over the network ? What is a Ri for ai=a (the result of an action we have as many actions as there are armes to the bandit)
  * see introduction: it is a one state problem!
  * p 20 we have the explanation of the estimations 
* Qt(a) is the mean Award of all a actions befoire t
* q*(a) has been defined p 48 it is the Esperance or the rewards for all action a !!!
# page 56

* we have seen earlier that the Q2 = R1 whatever Q1 may be
  * I don't understand what optimistic initial value brings to the table
* see the formula 2.6 (page 54)
* * Greedy with optimistic (not Epsilon Greedy but pure greedy)

# page 57

* the pure greedy (Epsilon=0) does not explore other actions than the ones which bring the best Q
# page 59 
* more about the [softmax function](https://en.wikipedia.org/wiki/Softmax_function)
  * _converts a vector of K real numbers into a probability distribution of K possible outcomes_
  * pit(a) is the probaility that the action at the time t is __a__
    * _⇡t (a), for the probability of taking action a at time t_
* equation 2.12
  * At is the action chosen at time t (with Reward Rt)
  * a are the other actions not chosen at time t
  * the reward is incremented if Rt > mean(Rt) but decremented with the probability of having chosen A at time t
# page 61
* indirectly I have the definition of __q*__
  * q*(At) = E[Rt|At]
  * and here we substitute q*(At) with Rt
# page 63
* _If actions are allowed to affect the next situation as well as the reward, then we have the full reinforcement learning problem.
 