#### Preemption Threshold Scheduling: Stack Optimality, Enhancements and Analysis

Preemption thresholding scheduling (PTS) in a realtime multithreaded system reduces system preemptions and reduces run-time overhead while ensuring real-time constraints.  
Optimality of PTS is considered in this paper for minimizing systems total stack memory requirements.
- The paper focus on minimizing the stack usage due to preemption in embedded memory constrained systems.
- Main aim of the paper being, provided a workload give a limit on amount of memory that can be saved by limiting the preemptions while not violating any of of real-time constrains of given workload.
- Second aim is to provide a framework that applies to both fixed priority and dynamic priority schemes.
##### Overview
- Introduced as part of ThreadX.
- Many of the resource sharing protocols has been integrated along with PTS. priority cieling can be used along with extended approach to Baker's Stack Resource Policy runs along with PTS.
##### Details
- In case PTS blocking time on  a high priority task due to a low priority task, but with higher preemption threshold value needs to be considered.
- The worst case response time equation thus includes addition paramter blocking time, which is for all tasks with priority lower than current task but higher preemption threshold, maximum value of the budget.
##### Memory optimality and Response
- Stack memory optimality:
	- A contribution of this paper is to find a preemption level mapping that is both feasible and in some sense optimal.
	- Initially a identity preemption threshold assignment is done, identity preemption threshold assignment corresponds to value where PT is equal to tasks preemption level.