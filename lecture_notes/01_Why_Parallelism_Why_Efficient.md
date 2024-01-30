# Parallel Processing Course Overview

## Observations
- **Speedup using P processors**: The speedup achieved by using P processors is calculated as the execution time with one processor divided by the execution time using P processors.
- **Communication & Speedup**: The speedup of parallel execution can be significantly limited by the overhead of communication between processors.
- **Work Assignment Imbalance**: 
    - In massively parallel execution, the communication costs can dominate the computational overhead, severely limiting the potential speedup.
    - An imbalance in work assignment among processors can also limit the efficiency of parallel execution.

## Course Themes
1. **Designing Scalable Parallel Programs**: Emphasis on designing parallel programs that can efficiently scale with the increase in processor count.
2. **Parallel Computer Hardware**: Understanding the workings of parallel computer hardware.
3. **Efficiency vs Speed**: 
    - Fast execution on a parallel computer does not necessarily equate to efficient use of hardware.
    - For example, achieving only 2x speedup using 10 processors is less efficient compared to maximizing the hardware's full capacity.

## Why Parallel Processing?
- **Increasing Clock Frequency**: Overcoming the limitations of increasing processor clock frequency.
- **Exploiting Instruction-Level Parallelism (ILP)**:
    - Understanding a processor's perspective of a program as a sequence of instructions.
    - Increasing the rate at which a processor can run instructions for faster execution.
    - ILP is the concept where processors leverage parallel execution to speed up program execution, albeit invisibly.
    - **ILP Example**: In the expression `a = x*x + y*y + z*z`, parallel execution can be utilized.
    - **Diminishing Returns of Superscalar Execution**: 
        - Most available ILP is exploited by a processor capable of issuing four instructions per clock cycle.
        - Little performance benefit is observed from building a processor that can issue more than four instructions per clock.
