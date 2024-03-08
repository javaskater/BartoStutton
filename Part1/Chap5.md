# MonteCArlo Methods
# 114 
* Algorithm MonteCarlo 
  * to understand it let go [Response 57 of that Stack Exchange Post](https://datascience.stackexchange.com/questions/9832/what-is-the-q-function-and-what-is-the-v-function-in-reinforcement-learning)
  * We are starting with $S_t$ but are searching it in the previous events
  * What does it mean append G to return St? $S_t$ is a list of values G
    *  each element (G value) is obtained for an episode following $\pi(s) : S_0, A_0, R_1 ...S_{T-1}, A_{T-1}, R_T$ 
    *  the episode is not infinite !!!
  * the average is calculated on the R'list of G values!
  * unless means I stop calculating G if $S_t$ is found in my previous values (the first time t=T-1 and the values has to be retrieved in the values from 0 to T-2)
## 116
* I don't answer to the exercices 5.1, 5.2
* __DP__ stads for _Dynamic Programming_ !!!! 
# 120
* Stuck at the question $q_{\pi_k} \geqslant v_{\pi_k}$
  * [here](https://ai.stackexchange.com/questions/2733/understanding-why-the-expectation-is-over-the-new-policy-pi-in-the-proof-of) the start of an answer
  * refers to pages 84 an 85 of this book (the inequality is but explained __p 100__)
  * difference between v and q functions: [Response 57 of that Stack Exchange Post](https://datascience.stackexchange.com/questions/9832/what-is-the-q-function-and-what-is-the-v-function-in-reinforcement-learning)
  * it is greater because $\pi_k$ is an optimal policy that gives the best solution (see reponse 57 above)
> You sum every state action-value multiplied by the probability of taking that action (given by the policy π(a|s)).
# 121
* Exercice 5.4. the [solution to exercise 5.4](https://github.com/LyWangPX/Reinforcement-Learning-2nd-Edition-by-Sutton-Exercise-Solutions/blob/master/Chapter%205/Solutions_to_Reinforcement_Learning_by_Sutton_Chapter_5_r3.pdf) is using a Q value from part 2 (equation 2.4 p 53) which has nothing to do with the $V_\pi$ value and th $q_\pi$
  * it is a mean value of all rewards for state s
# 123
* difference between [Epsilon Soft and Epsilon Greedy Policy](https://lazyprogrammer.me/what-is-the-difference-between-epsilon-greedy-and-epsilon-soft-policies/)
  * an Epsilon greedy policy is a psecial case of an Epsilon Soft Policy !!!
* The inequality at 5.2 is very well explained in [the answer 9 line 3 of that StackExchange](https://stats.stackexchange.com/questions/248131/epsilon-greedy-policy-improvement)
  * the max over a is under $\pi\prime$ but its value is still $q_\pi$ 
  * $\pi$ and $\pi\prime$ use theepsilon Greedy Policy, 
    * but the max under $\pi\prime$ might be greater than the max under $\pi$ alone
# 125 
## Off policies
# 126
* the notation $A_{t:T-1} \sim \pi$ means that the choice of 
  * $A_t$ when coming from $S_t$ (which brings to $S_{t+1}$)
  * $A_{t+1}$ when coming from $S_{t+1}$ (which brings to $S_{t+2}$)
  * until $A_{T-1}$ when coming from $S_{T-1}$ (which brings to $S_T$)
* is all done using the politic $\Pi$
* $Pr(A_t, S_{t+1}, A_{t+1}, S_{t+2}, ..., S_T | S_t) = \pi(A_t|S_t) \times p(S_{t+1}|A_t, S_t) \times Pr(A_{t+1}, S_{t+2}, ..., S_T | S_{t+1})$
  * $p(S_{t+1}|A_t, S_t)$ if the probaility we reach $S_{t+1}$ under the hypothese we come from $S_t$ through action $A_t$ which itself is only $\pi(A_t|S_t)$ probable ! 
* [MDP](https://builtin.com/machine-learning/markov-decision-process) or _Markov Decision Process_
* Equation 5_4 I intorduced the coefficient inside the Expectation 
  *  The value function is given in equation 3.12 page 80 [What $E_\pi$ means](https://stats.stackexchange.com/questions/373076/what-does-an-expectation-with-respect-to-a-policy-mean-in-the-reinforcement-lear) it is a mean on all the possible trajectoris from s ?
  
## Equation 5.4
* The calculations of [$V\pi and Q_\pi$](https://datascience.stackexchange.com/questions/9832/what-is-the-q-function-and-what-is-the-v-function-in-reinforcement-learning)
* $\pho$ is the division of the probabilty of _reaching T from t using the optimal policy_ by *reaching T from t using the befaviour policy*
* $E_\pi$ if a sum of all probailities that $\pi$ generates ([Video](https://deeplizard.com/learn/video/eMxOGwbdqKY) says that $\pi$ if a probability distribution on all the actions that follow s)
* [from the video](https://deeplizard.com/learn/video/eMxOGwbdqKY) the value function is the Expected return!
  * Gt is called the Q-value
* [from this site](https://deeplizard.com/learn/video/eMxOGwbdqKY) $\pi$ is a probability distribution over a $\in$ A(s)
* In this [Stack Exchange Post](https://ai.stackexchange.com/questions/35915/how-do-we-estimate-the-value-of-a-stochastic-policy) it is explained how the Expectation is calculated (it is $\sum_{a \in A(s)}\pi(a|s)$)

# 130
## Exercice 5.5:
* there is an error in multiplying 0.9 and 0.1 by $\frac{1}{2}$ 
  * we don't find this $\frac{1}{2}$ in the las equality