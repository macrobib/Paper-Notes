#### A Dual-Layer Bus Arbiter for Mixed-Criticality Systems with Hypervisors

Deals with the timing issues that arises from moving a real-time hypervisor implementation to multi-core.
- Deal with concurrent access to memory from multiple cores in   a hypervisor setup.
- XtratuM based approach.
- Schedule table based approach called here as Statically defined slots or Major Time Frame(MAF).
- Each partition having internal schedule which the guest is free to decide.
- Health monitor to detect and respond to undefined behaviors.
- Modification to done the AMBA arbiter.
- TDMA time slot assigned to critical partitions, while to non-critical partitions RR based approach used.
- Evaluation on Terasec DE-2 based development platform with LEON3.
