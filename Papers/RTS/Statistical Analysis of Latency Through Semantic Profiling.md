##### Statistical Analysis of Latency Through Semantic Profiling.


- Most profiling toolsets available try to quantify the most penalized or hot function or code segments. But , ofter it is required to know of the predictability of the measurement as well. 
- Similarly, it is ofter required to know the performance in a semantically defined interval, which may span across multiple functions and need to handled as such.
The current paper takes a stab at this problem and proposes a tracing framework that helps to identify the dominant source of latency variance in sematic context. A novel abstraction ***variance tree*** is proposed.

Existing profilers focus on providing details in terms of average performance, i.e. which function is called in which context and how much it contributes towards total latency, But not the predictability measurement of the paths.  
Second points of concern is that *semantic interval* is significant from the perspective of the user and not from the function or call graph point of view.  
- VProfiler aggregates latency variance along a backward path of dependce relationship among threads from end of an interval to its start.
- Using a variance tree reasoning is done on relationship between overall latency variance and the variances and covariances of execution time of the culprit functions to determine root cause of the issue.
- Measuring unit : percentile of tail latency, thresholding value od 99th percentile.
- Latency causes: I/O, locks, thread scheduling, queuing delay, varying work per request.
- strace for I/O and Dtrace for performance profile : traditional.

###### Variance Tree
A representation of variance along with covariance with respect to other function.
- There will be legtimate functions with latency that should not be penalized by representation on the variance tree. Instread a *factor* is proposed to quantify meaningful variance.
- Aggregation of the latency is done over the collected segment value.
- With the help of the user input iterative refinement is done. e.g. if the top-k reason for variance calculated is not sufficient, the user can mark the same and depending on this, the child functions are added to the tracked functions and variance are detected.
- An implementation is provided for C++.

[Reference: *Statistical analysis of latency through semantic profiling.*](https://web.eecs.umich.edu/~mozafari/php/data/uploads/eurosys_2017.pdf)