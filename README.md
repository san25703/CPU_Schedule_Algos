# CPU Scheduling Algorithms

## Objective

This project implements a variety of CPU scheduling algorithms in C++, designed to simulate and evaluate the performance of different scheduling techniques. The algorithms included are:

1. **First Come First Serve (FCFS)**
2. **Round Robin (RR)**
3. **Shortest Process Next (SPN)**
4. **Shortest Remaining Time (SRT)**
5. **Highest Response Ratio Next (HRRN)**
6. **Feedback (FB)**
7. **Aging**

## Features

- **Input Parsing**: Efficiently reads and processes input data, including process names, arrival times, and service times.
- **Algorithm Execution**: Executes the specified scheduling algorithm, providing detailed trace or statistical output.
- **Trace Mode**: Provides a visual timeline of process execution, aiding in the analysis of algorithm behavior.
- **Statistics Mode**: Computes and displays key performance metrics such as average turnaround time and normalized turnaround time.

## Algorithms Overview

- **FCFS**: Executes processes in the order of their arrival.
- **RR**: Executes processes in a round-robin manner with a specified quantum.
- **SPN**: Selects the next process based on the shortest service time.
- **SRT**: Selects the process with the shortest remaining time next.
- **HRRN**: Selects the process with the highest response ratio.
- **FB**: Utilizes multiple feedback queues with varying priority levels.
- **Aging**: Prevents process starvation by incrementally increasing the priority of waiting processes.
