---
marp: true
theme: gaia
paginate: true
---


# Definitions

1. Agent.
2. Environment.
3. State.
4. Observation.
5. Episode.

---
## MDP

A MDP is a 4-tuple ($S$,$A$,$P_a$,$R_a$), where: 
* $S:=$ is a set of states called the state space.
* $A:=$ is a set of actions called the action space.
* $A_s:=$ is a set of actions available from state $s\epsilon S$.
* $P_a(s,s') := \mathbb{P}(s_{t+1}= s' | s_t = s, a_t = a)$ is the probability that action $a$ in state $s$ at time $t$ will lead to state $s'$ at time $t+1$.
* $R_a(s,s')$ is the immediate reward recived after transition from $s$ to $s'$ .

---

![](Markov_Decision_Process.svg)

---

## Marcov property 

$$\mathbb{P}(S_{t+1} | S_t, A_t) =\mathbb{P}(S_{t+1} | S_t, A_t, S_{t-1}, A_{t-1}, ...)  $$ 

![](Marcov_phy.svg)
 

---
## Episode

Is a sequence :

$[(S_0,A_0,R_0),(S_1,A_1,R_1),...,(S_T,A_T,R_T)]$

its just one run.

![](Episode.svg)

---
## Return
A given episode $[(S_0,A_0,R_0),(S_1,A_1,R_1),...,(S_T,A_T,R_T)]$ of MDP and a given $\gamma\epsilon[0,1]$.
$$G_t=R_{t+1} + \gamma R_{t+2} + ... = \sum_{k=0}^{\infin} \gamma^k R_{t+k+1}    $$

or 
$$ G_t = R_{t+1} + \gamma G_{t+1}$$

---
## Reward function.
Given MDP we define reward function. $s ,s'\epsilon S, a\epsilon A$
$$ r(s) = \mathbb{E}_{a,s'}[R_{t+1} | S_t = s] $$ 
$$ r(s,a) = \mathbb{E}_{s'}[R_{t+1} | S_t = s, A_t =a ] $$ 
$$ r(s,a,s') = \mathbb{E}[R_{t+1} | S_t = s, A_t =a,S_{t+1} = s' ] $$ 
---

![](RewardFunction.svg)

---
## Policy 
Given a MPD we define

$$ \pi(a|s)= \mathbb{P} [A_t = a | S_t = s] $$

* A policy fully defines the behavior of an agent.

---
![](RewardFunctionWithPolicy.svg)

Now we acn talk about: 
$$ r(s) = \mathbb{E}_{a,s'}[R_{t+1} | S_t = s] $$ 



---
## State-value function $V$

Given a MDP and a policy $\pi$ on it we define
* $$ V_{\pi}(s) = \mathbb{E}_\pi [G_t|S_t=s]~~ \forall s \epsilon S $$
* $$ V_{\pi}(s) = \mathbb{E}_\pi [R_{t+1} + \gamma G_{t+1}|S_t=s]~~ \forall s \epsilon S  $$
* $$ v_\pi (s) = \sum_a \pi (a|s) \sum_{s',r} p(s',r|s,a)[r+\gamma v_\pi(s')], ~~ \forall s \epsilon S$$

---
## See inside This equation

$$ v_\pi (s) = \sum_a \pi (a|s) \sum_{s',r} p(s',r|s,a)[r+\gamma v_\pi(s')], ~~ \forall s \epsilon S$$

![]

---
##  Action-value function $Q$

* $$q_\pi(s,a) = \mathbb{E}_\pi [G_t | S_t = s, A_t = a] $$
* $$q_\pi(s,a) = \mathbb{E}_\pi [R_t + \gamma G_{t+1}| S_t=s,A_t=a]$$
* $$ q_\pi(s,a) = \sum_{s',r} p(s',r|s,a) [r+\gamma v_\pi(s')], \forall s\epsilon S, \forall a \epsilon A$$

---
## See inside This equation

 $$ q_\pi(s,a) = \sum_{s',r} p(s',r|s,a) [r+\gamma v_\pi(s')], \forall s\epsilon S, \forall a \epsilon A$$











































