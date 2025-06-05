# POLICY EVALUATION

## AIM
To develop a Python program to evaluate the given policy.

## PROBLEM STATEMENT
To find best policy from two policies which are defined by user using policy evaluation function. Where the mdp includes 16 states from 0-15, 0 is the starting state, assigning some 4 random state as holes and 15 is the goal state and then we need to calculate optimal state value function for each state such that we can reach goal using optimal policy using policy evaluation.

## POLICY EVALUATION FUNCTION
```
def policy_evaluation(pi, P, gamma=1.0, theta=1e-10):
    prev_V = np.zeros(len(P), dtype=np.float64)
    # Write your code here to evaluate the given policy
    while True:
      V=np.zeros(len(P))
      for s in range(len(P)):
        for prob,next_state,reward,done in P[s][pi(s)]:
           V[s]+=prob*(reward+gamma *prev_V[next_state]*(not done))
      if np.max(np.abs(prev_V-V))<theta:
        break
      prev_V=V.copy()
    return V
```


#### Policies:
![Screenshot 2025-03-26 105050](https://github.com/user-attachments/assets/09641909-b6c3-468a-bf79-c078d1c65566)


![Screenshot 2025-03-26 104752](https://github.com/user-attachments/assets/1c747667-db7c-4bc5-a7ba-dcc541414f13)

#### State value function:
![Screenshot 2025-03-26 105139](https://github.com/user-attachments/assets/eb2d2d40-51a8-461b-8891-0ae170e41d23)

#### Best policy:

![Screenshot 2025-03-26 104927](https://github.com/user-attachments/assets/bc59ba3c-e20c-44a7-b27a-ffb1984a5c31)

## RESULT:
Thus, The Python program to evaluate the given policy is successfully executed.
