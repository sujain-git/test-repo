
Process:

- Process is a running program, its an abstraction which OS uses to run program
- Program is file on disk, it might contain instructions or data as bytes
- OS takes this program and creates process to run these instructions
- If we want to run more than one progrm, Although there are only a few physical CPUs available, how can the
OS provide the illusion of a nearly-endless supply of said CPUs?
- CPU virtualization
  - time sharing the CPU between processes, stop one process, run another and run ti back and so on
  - penalty in terms of running time of a process, as each process will take more time to complete

- Time sharing
    - resource is shared by time, taking turns(CPU, network)
- Space sharing
    - resource is partitioned by space (DISK)

- To implement CPU virtualization, OS will need lowl level mechanisms(like context swtich) and some alogrithms(scheduling policies)
- Scheduling policies - based on how long the program is running, system should be optimized for throughput or interactiveness, what kind program load we are dealing with etc.
