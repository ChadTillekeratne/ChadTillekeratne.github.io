
## cgroup - Control Groups
- cgroup (control groups) - allow for system resource (CPU time, system memory, network bandwidth, etc.)  to be set to user-defined groups of tasks (processes)
  - `cgcconfig` (Control Group config) - can start at boot time to reestablish predefined cgroups
  -  Allow for fine-grained control over allocating, prioritizing, denying, managing, and monitoring system resources
  - https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/resource_management_guide/ch01
  - https://man7.org/linux/man-pages/man7/cgroups.7.html

## Namespace
- Namespace - Process isolation -  Linux kernel feature that partitions kernel resources; limits what a process can see
  - Works by having the same namespace for a set of resources and processes, but those namespaces refer to distinct resources
  -  Kinds of namespaces:
     - Mount (mnt) 
     - Process ID (PID)
     - Network (net)
     - Interprocess Communication (IPC)
      - UTS - Unix Time-Sharing - allow for a single system to appear to have different host and domain names to different processes
      - Control group (cgroup) namespace - hides the identitiy of the control group of which a process is a member
          - Process in such a namespace, would see a path that is relative to the cgroup set at creation time (hides true cgroup position and identity)
	  - Time - allows processes to see different system times
  - https://en.wikipedia.org/wiki/Linux_namespaces
  - https://www.toptal.com/linux/separation-anxiety-isolating-your-system-with-linux-namespaces