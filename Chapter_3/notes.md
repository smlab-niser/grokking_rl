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
* $P_a(s,s') := Pr(s_{t+1}= s' | s_t = s, a_t = a)$ is the probability that action $a$ in state $s$ at time $t$ will lead to state $s'$ at time $t+1$.
* $R_a(s,s')$ is the immediate reward recived after transition from $s$ to $s'$ .

---

![alt text](Markov_decision_process.svg)

---

## Marcov property 



$$P(S_{t+1} | S_t, A_t) =P(S_{t+1} | S_t, A_t, S_{t-1}, A_{t-1}, ...)  $$ 
 
---
## 