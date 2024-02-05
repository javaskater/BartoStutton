# Finite Markov Decision Process (MDP)

## p 70
* p 70 Figure 3.1 very interesting
  * The action At gives rise to Rt+1 and St+1 (consequence of action At) which are seen by the Agent
  * Rt is a real number (size 1)
  * St can be of any size (see the exercises of [RCP211](https://jhub3.cnam.fr/user/24592/lab/tree/MonDossier/RCP211/TP4))
* the sets are in curved letters*
* important equation 3.2: s' is associated with St and s with St-1, and a with At-1 b
  * but r is associtiated wuth Rt
  * a belongs to the Set of actions attached to the state s=Rt-1
## p 71
* equation 3.3 states that p though a conditional probability if a probability distribution 
  * and the sum over all rewards Rt and States (s' or St) is equal to 1
    * given a state s=St-1 and the chosen Action a=At-1
* _That is, the probability of each possible value for St and Rt depends only on the immediately preceding state and action, St 1 and At-1_
  * but not on earlier States and Actions (St-2, At-2)
* the 3.6 equation is more difficult to understand
  * p(s'|s,a) = SUMr(p(s',r|s,a)). It is the proportion taken by r in the outcomes (for passing from s to s' using action a) x r 
  * r(s,a,s') is a mean value of all the r values for passing from s to s' using action a
  * we cn see also using the demo of the [Bayes Theorem](https://en.wikipedia.org/wiki/Bayes%27_theorem)
    * here P(A and B) = p(s',r|s,a), P(B) = p(s'|s,A) then P(A|B) = p(r|s,a,s') = P(A and B)/P(B) = p(s',r|s,a)/p(s'|s,a)
    * r(s,a,s') = Sumr(r*p(r|s,a,s'))
# p 73
* Example of _Bio reactor_
  * Stirring rate --> Taux d'agitation (in french)
  * vat --> the tank
* Example Robot:
  * joint --> Articulation (de robot in french )
  * jerkiness --> saccade (in french)
  * moment-to-moment --> de temps en temps (in french)
# p 74, 75:
* Recycling robot
* with the table and the graph
  * we understand the usefullness of the probabilities at page 71
  * two kind of nodes
    * state nodes: big White Circles with the name of the state inside
    * action nodes: small black circles with the action's name next to it
* we use p(s'|s,a) which is a sum on all p(s'r|s,a) see _p 71_ 
  * here only one r?
* we use r(s,a,s') see mean value on all r see _p71_ 
  * here only one r ?
* to go back to p(s',r|s,a) is the target of Exercise 3.4
  * the probability are 1, 0, alpha; 1 - alpha, beta, 1 - beta

# 3.2 Goals and rewards
## p 76
* _The reward signal is your way of communicating to the robot what you want it to achieve, not how you want it achieved_
* We want to maximize Gt the expected return avec At (Gt = Rt+1 + Rt+2 + ... + RT)
  * don't forget that the consequence of At is the Agent receving Rt+1 and seeing a new state St+1
* a episode is an _ending in a way_
* a terminal state with a reset to a starting state !!!
  * from the end back to the beginning
* we call it episodic tasks !!! 
## p 77
* As many processes end up indefinitely we use the discounted Return
* GT = 0

# p 78
* pole hinged  to a cart --> poteau articulé sur un chariot (in french)

# 3.4 Unified notation
## p 79
* The square in Grey is for an absorbing state ...

# 3.5 Policies and values functions
* All the exercises [3.11, 3.12, 3.13 ...](git@github.com:LyWangPX/Reinforcement-Learning-2nd-Edition-by-Sutton-Exercise-Solutions.git)
## p 80
* V is how good in term of future rewards
* Pi is defined here as a probaility of choosing a knowin state s !!!
* Exercice 3.11 goes back to the four agument function of p 32 (by me 71 of the pdf)
  * the two solution sites give the same solution 
    * p supposes we are on state St = s and action a
    * so we multiply by the probability of being in action a for all the a actions starting from s=St
* The value function definition is very interesting, it depends on a policy, following that policy
  * what will be Expected value of random variable ?
  * it has been given in exercice 3.11 as Suma(Pi(a|St))
* Exercices 3.12 and 3.13 are very instructing of what is the Expected value following Pi ?
## p 81
* 3.14 is the formula to be found in exercice 3.12
  * It is an important equation called the **Bellman Equation**
## p 83 End
* Equation exercice 3.17 comes from the relationship between vpi and qpi (exercice 3.12)
  * and from the Bellmann equation 3.14 !!
# p 84
## Exercise 3.19:
* Expected Value or mean value seems to be Sums'r(p(s',r|s,a))
* Expected Value on politics pi seems to be Suma(Pi(a|s))
# p 85
* Equation 3.18 transform Epi in E how is it possible ?
  * it is beacause v* is max q and not Epi(q)
  * and q is E() 
# p 86:
* _that the maximum over that choice is taken rather than the expected value given some policy_