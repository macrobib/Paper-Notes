#### Response-Time Analysis for Mixed Criticality Systems

*Builds upon Audsley's optimal priority assignment approach:*
###### Audsley's optimal priority assignment:
- Compares with two contemprory priority assignment scheme, rate monotonic priority assignment and Deadline monotonic priority assignment.  
- An approach to check if tasks with arbitrary release times will even share a common release time, complexity of O(m log_e m). A priority assignment scheme with complexity of O(n^2 + n).
- Three main focus of the paper: Find the critical time instances, provide a priority assignment and an approach for feasibility test.
- Some major assumptions: Zero cost of preemption, preemption at boundaries, tasks are non-blocking and do not yield voluntarily.
- Priority assignment: Iterative approach is employed, a task is picked at random, assigned lowest priority and its feasibility is checked. If successful next task is picked and process continued till all tasks are assigned feasible priority. If at any time the 

###### Concept of RTA approach
 **Static Mixed Criticality(SMC)**
 - Deadline monotonic within criticality monotonic approach.
 - RTA algorithm is applied after this priority assignment:
 $$R_i = C_i + \sum_{x_j \in  hp (i)} \lceil \frac{R_i}{T_j} \rceil C_j(min(L_i, L_j))$$
- Three different schenarios are handler under SMC approach 
1. Li == Lj, in this case use the Cj value corresponding to normal criticality.
2. Li < Lj, Smaller criticality value corresponding to i is used.
3. Li > Lj, value corresponding to Cj is used, but runtime mechanism should make sure the task does not excedes this budget value.  

- Audsley's approach to priority assignment is used, which provides optimal priority assignment in n(n+1)/2 steps compared to the exhaustive search which is factorial in complexity.  

**Adaptive Mixed Criticality(SMC)**  
Main approach taken by AMC is as follows:
- There is a criticality leve indicator L.
- if L == Lo, at each instant waiting jobs generated by highest priority is picked for execution.
- If currently executing job consumes it Lo Crit Budget without signalling completion, criticality is set to HI.
- One criticality level is HI jobs of Lo criticality are not executed.
- Two approaches are provided for sufficient analysis of response time: 
	- AMC-rtb
	- AMC-max  

- AMC-max provides a tighter bound on the response time corresponding to AMC-rtb.  

**Reference**: [RTA](https://www-users.cs.york.ac.uk/burns/RTSS.pdf) 