# CPU Scheduling Algorithms Simulator

This project is a **C++ simulator** that demonstrates and compares different **CPU scheduling algorithms**. It allows users to generate random processes and then run them through various scheduling strategies to observe their performance, mainly focusing on **waiting time**.  

---

## 📌 Features

- Random **process generator**:
  - Each process has:
    - `PID` → Unique Process ID  
    - `Burst Time` → Execution time required  
    - `Priority` → Value between 1 (highest) and 3 (lowest)  

- **Implemented Scheduling Algorithms**:
  1. **First Come First Served (FCFS)**  
  2. **Shortest Job First (SJF)**  
  3. **Priority Scheduling**  
  4. **Round Robin (RR)** with quantum = 4  
  5. **Multilevel Queue Scheduling** (with 3 queues using RR, FCFS, and SJF)

- Interactive **menu-driven interface** for selecting algorithms.

- Ability to **display processes** and **regenerate new processes** at any time.

---

## 🖥️ How It Works

### Process Generation
- `generateProcesses(num_processes)` creates random processes with random burst times (1–20) and priorities (1–3).  
- Example:
  ```
  ID    Burst Time    Priority
  0     12            2
  1      5            3
  2     19            1
  ...
  ```

### Algorithms Implemented

1. **First Come First Served (FCFS)**  
   - Processes are executed in the order they arrive.  
   - Waiting Time = Sum of burst times of all previous processes.  

2. **Shortest Job First (SJF)**  
   - Processes with the shortest burst time are executed first.  
   - Waiting time is minimized but requires knowledge of burst times.  

3. **Priority Scheduling**  
   - Processes with higher priority (lower number) are executed first.  

4. **Round Robin (RR)**  
   - Each process gets a fixed **quantum** (default = 4).  
   - If a process is not finished, it re-enters the queue until completed.  

5. **Multilevel Queue Scheduling**  
   - Processes are divided randomly into 3 queues:  
     - **Queue 0** → Round Robin  
     - **Queue 1** → FCFS (with added waiting from Queue 0)  
     - **Queue 2** → SJF (with added waiting from Queues 0 & 1)  

---

## 📊 Output Example

When running FCFS:  
```
FCFS Scheduling:
Process Burst Time  Priority  Waiting Time
0       12          2         0
1        5          3        12
2       19          1        17
...
Average Waiting Time: 10.5
```

Round Robin Example:  
```
Round Robin Scheduling:
Process Burst Time  Priority  Waiting Time
0       12          2         18
1        5          3          7
2       19          1         23
...
Average Waiting Time: 16.2
```

---

## 🚀 How to Run

### 1. Clone / Download Project
```bash
git clone <repo_url>
cd CPU-Scheduling-Algorithms-Simulator
```

### 2. Compile
```bash
g++ -std=c++11 -o scheduler main.cpp
```

### 3. Run
```bash
./scheduler
```

### 4. Menu Options
```
--------------------------------------------
Choose a scheduling algorithm:
1. First Come First Served (FCFS)
2. Shortest Job First (SJF)
3. Priority Scheduling
4. Round Robin (RR)
5. Multilevel Queue Scheduling
--
8. Display Processes
9. Clear Processes and Generate New Ones
0. Exit
--------------------------------------------
```

---

## 📖 Learning Purpose

This project helps understand:
- How different **CPU scheduling algorithms** work.
- How **waiting time** differs across strategies.
- The trade-offs between fairness, priority handling, and efficiency.

---

## ⚙️ Future Improvements
- Add **Turnaround Time** and **Response Time** metrics.  
- Support for **preemptive versions** (Preemptive SJF, Priority Preemptive).  
- Add **Gantt chart visualization** for execution order.  
- Option to **input custom processes** instead of only random generation.  

---

## 👨‍💻 Author
Developed by **Greeshraj Patairiya**  
🎓 IIT Kharagpur  
