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

To provide input and output formats for this project, we need to consider the scheduling algorithms and the way processes are described in the code. Here's a detailed format:

### Input Format

The input consists of:
1. **Process Descriptions**: A list of processes with their arrival times and service times.
2. **Algorithm Descriptions**: A list of scheduling algorithms to be executed with their parameters.
3. **Operation Mode**: The mode of operation (either tracing the timeline or showing statistics).

#### Process Description Format
Each process is described by:
- A string representing the process name.
- An integer representing the arrival time of the process.
- An integer representing the service time of the process.

#### Algorithm Description Format
Each algorithm is described by:
- An integer representing the algorithm ID.
- An optional integer representing the quantum (for algorithms like Round Robin and Aging).
- A string representing the operation mode (`trace` or `stats`).

### Example Input
```plaintext
# Number of processes
5
# Process Descriptions (one per line)
P1 0 5
P2 1 3
P3 2 8
P4 3 6
P5 4 2
# Number of algorithms
3
# Algorithm Descriptions (one per line)
1 trace        # First Come First Serve
2 4 stats      # Round Robin with quantum 4
3 trace        # Shortest Process Next
```

### Output Format

The output will vary based on the operation mode:

#### Trace Mode
For each algorithm in trace mode, the timeline of the processes' execution will be displayed.

Example:
```plaintext
FCFS
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14
------------------------------------------------
P1     |*|*|*|*|*| | | | | | | | | |
P2     | | | | |.|.|*|*|*| | | | | |
P3     | | | | | | | |.|.|.|.|.|.|*|*|
P4     | | | | | | | | | | | | | |.|.|*|*|*|*|
P5     | | | | | | | | | | | | | | | |.|*|*|

RR-4
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14
------------------------------------------------
P1     |*|*|*|*| |*| | | | | | | | |
P2     | | | | |.|.|*|*|*| | | | | |
P3     | | | | | | | |.|.|.|.|.|.|*|*|
P4     | | | | | | | | | | | | | |.|.|*|*|*|*|
P5     | | | | | | | | | | | | | | | |.|*|*|

SPN
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14
------------------------------------------------
P1     |*|*|*|*|*| | | | | | | | | |
P2     | | | | |.|.|*|*|*| | | | | |
P5     | | | | | | | |.|*|*| | | | |
P4     | | | | | | | | | | | |.|.|.|*|*|*|*|
P3     | | | | | | | | | | | | | | |.|.|.|.|*|*|*|*|*|*|*|*|
```

#### Statistics Mode
For each algorithm in stats mode, the following statistics will be displayed:
- Process Names
- Arrival Times
- Service Times
- Finish Times
- Turnaround Times
- Normalized Turnaround Times

Example:
```plaintext
RR-4
Process    |  P1  |  P2  |  P3  |  P4  |  P5  |
Arrival    |  0   |  1   |  2   |  3   |  4   |
Service    |  5   |  3   |  8   |  6   |  2   | Mean
Finish     |  8   |  5   | 17   | 14   |  6   |-----|
Turnaround |  8   |  4   | 15   | 11   |  2   | 8.00|
NormTurn   |1.60  |1.33  |1.88  |1.83  |1.00  | 1.61|
```

### Additional Notes
- **Parsing the Input**: The `parse()` function should be responsible for reading the input, initializing the processes and algorithms, and setting the operation mode.
- **Modifying the Code**: Ensure that the code is designed to handle input from standard input (e.g., using `cin` for input and `cout` for output).

By following the above input and output formats, you can ensure that the program can process scheduling tasks and provide meaningful results in both tracing and statistics modes.
