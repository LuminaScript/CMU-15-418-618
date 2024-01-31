## Process
- **Single Core Process**
  - Utilizes context switching and round-robin scheduling.

## Thread
- **Definition**
  - The smallest sequence of programmed instructions that can be managed independently by a scheduler.
- **Characteristics**
  - A thread is a component of a process.
  - Every process has at least one thread, known as the main thread, which is the entry point for the program.
  - A process can have multiple threads.

## Parallel Programming
- **Single Core vs. Multi-Core**
  - Parallelism in a single core involves context switching, which is generally ineffective.
  - Multiple cores allow for more effective parallel processing.
- **Types of Parallelism**
  - **Task-Level Parallelism**: Performing different tasks on the same or different data sets.
  - **Data-Level Parallelism**: Performing the same task on different data sets (multiple threads operating on the same data).

## Concurrency and Parallelism
- **Terminology**
  - In this course, concurrency and parallelism are considered equivalent.
  - True parallelism involves processes running on different processors.

## Supercomputing, Heterogeneous Computing, and GPUs
- **Supercomputer**
  - A computer with performance significantly higher than a general-purpose computer.
  - Performance is typically measured in floating-point operations per second (FLOPS).
  - Common uses include biomedical research, physics simulations, and aerospace simulations.
- **GPUs vs. CPUs**
  - **CPU Characteristics**:
    - High clock speed latency device.
    - Fewer cores.
    - Contains optimization hardware like branch predictors.
  - **GPU Characteristics**:
    - Low clock speed throughput device.
    - Thousands of cores.
    - Lacks optimization hardware.
  - **Comparison**:
    - GPU: Context switching is hardware-based.
    - CPU: Context switching is software-based.
    - GPU: Can switch between threads if one stalls.
    - CPU: Stalls during memory instruction latencies with L1 and L2 cache misses.
    - GPU: Thread schedulers and dispatch units are in hardware.
    - CPU: Work item creation is done in software.

## Heterogeneous Computing
- **Definition**
  - Systems that use more than one kind of processor or cores.
- **Approach**
  - Performance gains are achieved not just by adding the same type of processors, but by incorporating dissimilar coprocessors, usually with specialized processing capabilities for specific tasks.
- **Example**
  - A typical smartphone may include a text processor, graphics processor, and a CPU.
