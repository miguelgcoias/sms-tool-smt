# Single machine scheduling tool
A Python tool that generates an optimal schedule for a set of tasks and their time and dependency constraints.

## Theoretical work
The tool is a direct implementation of the SMT formulation of the single machine scheduling problem by X. Liao, H. Zhang, M. Koshimura, R. Huang and W. Yu in [Maximum Satisfiability Formulation for Optimal Scheduling in Overloaded Real-Time Systems](https://doi.org/10.1007/978-3-030-29908-8_49).

## Input format
The problem instance should be formulated as follows:
- one line with the number n (strictly larger than 1) of tasks to be scheduled;
- a sequence of n lines, where each line i consists of a sequence r, p, d, k, p_1, ..., p_k which describes task i, where r is the release time, p is the processing time, d is the deadline time, k is the number of fragments, and p_1, ..., p_k are the processing times of the fragments;
- a sequence of n lines, where each line i describes the dependencies of task i. Each line consists of the number of dependencies followed by the indices of the tasks on which i depends.

## Output format
The tool will output an answer in the following format:
- one line with the number s of scheduled tasks;
- a sequence of s lines, where each line i contains the starting times of the fragments, ordered by fragment index and separated by spaces.

## Execution
The tool should be executed with the command
```
/path/to/proj1 < job.sms > solution.txt
```
where job.sms is a text file formatted as specified above, and solution.txt is a file where the solution will be written to.

## Dependencies
z3-solver must be installed.