# sjf-scheduling-nonpreemtive
Shortest Job First scheduling algorithm written in Python that calculates waiting time and turnaround time from user input. Includes grantt chart in output.

## Features 
  - Input for process arrival times and burst times.
  - Calculation of completion time, turnaround time, and waiting time for each process.
  - Display of a Gantt chart showing the order of execution.
  - Calculation and display of the average waiting time for all processes.

## Explanation of the Code

1. ** Process **
This Process class defines the attributes for each process:
  - pid: Process ID (e.g., A, B, C).
  - arrival_time: Time when the process arrives.
  - burst_time: Time required to complete the process.
  - completion_time, turnaround_time, waiting_time: Calculated during scheduling.

** calculate_sjf_non_preemptive **
Implements the SJF non-preemptive scheduling.
  - Ready Queue: Select processes that have arrived (arrival_time <= current_time).
  - Idle CPU: If no process is ready, the CPU idles until the next process arrives.
  - Shortest Job Selection: From the ready queue, select the process with the shortest burst_time.
  Time Updates:
    - completion_time: When the process finishes.
    - turnaround_time: Total time taken from arrival to completion (completion_time - arrival_time).
    - waiting_time: Time spent waiting (turnaround_time - burst_time).
  - Loop: Repeat until all processes are scheduled.

** diplay_grantt_chart **
Displays a Gantt chart showing the execution order of processes.
  - Prints the process IDs in the order they were executed.
  - Displays time intervals when each process finishes.

** print_process_summary **
Iterates through the completed processes and prints the relevant information (pid, arrival_time, burst_time, etc.).

** calculate_average_waiting_time **
Calculates the average waiting time of all processes. Sums up the waiting_time of all processes and divides by the number of processes.

** main **
 Drives the entire process scheduling simulation.
   - Input: Collects the number of processes and their arrival_time and burst_time.
   - SJF Calculation: Calls calculate_sjf_non_preemptive to execute the scheduling.
   - Display: Shows the Gantt chart and process summary.
   - Average Waiting Time: Calculates and prints the average waiting time.

## User Interaction

When the program runs, the user is prompted to enter:

1. The number of processes.
2. For each process:
   - Arrival time
   - Burst time

After entering all processes, the program will display:

- A Gantt chart showing execution order and completion times.
- A summary of each process's metrics.
- The average waiting time for all processes.
