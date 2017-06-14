#####Scalable Real-Time System Design using Preemption Thresholds
Scalable implementation architecture where design level tasks are grouped into a smaller number of run-time threads during implementation.  
_Benefits:_ Higher schedulability for small number of tasks and lower runtime overhead.
###### Approach:
- Approach is based on scheduling model, utilizing preemption threshold, which provides a middle ground for preemptive and non-preemtive scheudling approaches.
- The approach is in turn dual-priority system, where task's regular priority is used when task is released, but once tasks is scheduled to run its priority is boosted to preemption threshold.
- Scheduling model has two parts: Design level cocurrency and Implementation level concurrency.
- **Design Level concurrency**
  - Task is used as a design level abstraction.
  - Each task has a single trigerring event and executes under single timing constraint.
- **Implementation Level concurrency**
  - Thread represents the level of abstraction.
  - Threads are modeled as event handler with event queue, processing multiple event sets from timers, interrupts or from other threads.
- The approach in this paper is similar to stack sharing, where tasks that do not preempt each other are assigned a single stack.
- The task model allows two different tasks that are mutually non-preemptible to be mapped to same thread.
###### Contribution
Paper tries to reach consensus between two different problems:
**Feasibility Problem**: Given a set of tasks $\mathcal{T}$ = {$\tau_{i}$ = $\langle$ $C_{i}$, $T_{i}$, $D_{i}$  $ \rangle$ $\textbar$ 1 $\leq$ i $\leq$ N}, find a feasible implementation model $\mathcal{I}$  = $\langle$ M, $\psi$, $\pi$, $\gamma$  $\rangle$ if it exists.
**Optimization Problem**:  Given a schedulable taskset $\mathcal{T}$ = {$\tau_{i}$ = $\langle$ $C_{i}$, $T_{i}$, $D_{i}$  $ \rangle$ $\textbar$ 1 $\leq$ i $\leq$ N}, find an optimal feasible implementation $\mathcal{I}$  = $\langle$ M, $\psi$, $\pi$, $\gamma$  $\rangle$ such that there exists no other $\mathcal{I^{'}}$  = $\langle$ $M^{'}$, $\psi^{'}$, $\pi^{'}$, $\gamma^{'}$  $\rangle$ with $M^{'}$ $<$ M.
- Thus aims to minimize preemption by minimizing mapped threads, while maintaining schedulability.
###### Priority and Preemption level assignment.
Three different approaches proposed form feasible scheduling attribute level assignment
- **Pre-assigned preemption threshold**: Find feasibility under both preemptive and non-preemptive scheduling approaches, and if satisfied that guarantees task feasibility.
- **Two stage greedy algorithm**: Uses Audsley's approach augmented with a heuristic function to assign task priorities, task are moved from non-sorted to sorted queue in increasing priority order. While assigning priority as per Audsley's approach, first test is done to assure response time is less than deadline, next a maximum blocking time is appended and schedulability is checked again.
- **Simulated annealing** : Global optimization approach to priority assignment.
  - Algorithm moves randomly from one task to another for lowest priority assignment.
  - ​Random swapping and downward jump controlled by a control parameter C or cooling factor. Cooling factor reduced at each instant and thermal equilibrium is reached or search is stopped when downward jump exceeds _log_(2 * N) or number of solutions explored exceed $N^{2}$. 
  - Initially starts with deadline monotonic priority assignment.
##### Task grouping:
- Sort tasks by Preemption level ----> Start with lowest PL ----> Group all tasks with PL $\le$ a given PL value goes into one group ----> continue to all tasks are grouped.
###### Optimal Preemption Level assignment:
- Start with PL == priority for all tasks ----> for PL = {N to 1} ----> increase PL of each instance till schedulable ----> Repeat till end.

**Reference**: [Scalable Real-Time System Design using Preemption Thresholds: Manas Saksena& Yun Wang](http://dl.acm.org/citation.cfm?id=1890633)


