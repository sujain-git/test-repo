
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

- To implement CPU virtualization, OS will need lowl level mechanisms(like context swtich)(how) and some alogrithms(scheduling policies)(which). Modularity to separate mechamisms from policy
- Scheduling policies - based on how long the program is running, system should be optimized for throughput or interactiveness, what kind program load we are dealing with etc.

- Machine state of a Process
  -  Memory : the memory that the process can address (called its address space) is part of the process.
  -  Regsiters:
    -    Program counter (IP), what instruction will execute next
    -    Stack Pointer (SP),
    -    assocaited Frame Pointer: manage the stack for function parameters, local variables, and return addresses.
  - Storage devices : i/O
 
    Os has to load a program from disk to memory
    - eager loading, load everything(code, static data) before running the code
    - lazliy load parts of code/data as and when we require(requires paging , swapping)
    - allocate run time stack and gives it to the process
    -  The OS will also likely initialize the stack with arguments; specifically, it will fill in the parameters to the main() function, i.e., argc and the argv array
    -  The OS may also allocate some memory for the program’s heap
    -  on unix systems Os might open file descriptors to to stderr, stdout etc
    -  the OS transfers control of the CPU to the newly-created process, and thus the program begins its execution(from main()).
   
- Process States
-   Running, read to Run, blocked, zombie etc
-   Os has to keep track of process states, has process list, context about the process(Prcoess control block, process descriptor) etc. so that it can make context swtich
-   Parent process can check return code of a zombie process and indicate OS( wait() calls) to perform cleanup for extint process
