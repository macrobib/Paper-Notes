### An Elastic Mixed-Criticality Task Model and Early-Release EDF Scheduling Algorithms
##### key Idea:
- Introduce early release point to EDF-VD to improve schedulability of low criticality tasks.
- Builds on Elastic scheduling model proposed by Buttazzo, which proposed the idea of variable period bounded by a maximum period, which is determined offline and provides minimum service for the task.
- Proposes conservative and aggressive early release approaches, and investigate application to Preference Oriented Earliest Deadline Scheduler.
- Main idea is that unlike EDF-VD, the period used for low criticality tasks consists of two different values, $p_{emc}$ and $p_{erp}$ where former is the relaxed period while later is the early release period.
##### Early Release Mechanism: Deadline assignment and slack requirement.
- Two approaches to deadline asignment: conservative and aggressive.
- **Conservative**: Even for early release points the deadline assigned is based on $p_{emc}$ in stead of the early release period. This makes sure there are fixed number of release for any specific period.
- Early release assigned as per the slack available. Hence, a run-queue needs to maintain individual slacks and expiry time. Early release possible if and only if enough slack is available before the task deadline. Imp detail: Maintain a sorted runqueue of slack based on individual slack deadlines to enables easy calculation of early release success during runtime.
-**Aggressive**: Aggressive effort does not allow early release task to do time sharing with its future instance. i.e, task should finish by its actual deadline d. So slack required S = $c_i$
-  

**Reference** [An Elastic Mixed-Criticality Task Model and Early-Release EDF Scheduling Algorithms Hang Su et.al](https://www.researchgate.net/profile/Hang_Su10/publication/311959240_An_Elastic_Mixed-Criticality_Task_Model_and_Early-Release_EDF_Scheduling_Algorithms/links/58ab7b5a4585150402036bf1/An-Elastic-Mixed-Criticality-Task-Model-and-Early-Release-EDF-Scheduling-Algorithms.pdf)