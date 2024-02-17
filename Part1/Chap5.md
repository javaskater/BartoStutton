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