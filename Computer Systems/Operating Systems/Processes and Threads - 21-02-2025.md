## **1. Process**

A **process** is a **program in execution**.

An operating system executes different types of programs:

- **Batch Systems** – Jobs
- **Time-Shared Systems** – User Programs or Tasks

Each process requires resources such as:

- **CPU time**
- **Memory**
- **Files**
- **I/O devices**

Resources may be allocated **at the start** or **dynamically** as the process executes.

---
## **2. Process Management Responsibilities**

The operating system is responsible for **managing processes**, including:

- **Process creation and deletion**
- **Process suspension and resumption**
- **Process synchronization mechanisms** (via **priority & scheduling**)

---
## **3. Process Components**

A process consists of several components:

- **Code (Text Section)** – Program instructions.
- **Current Activity** – Includes the **program counter** and **CPU registers**.
- **Stack** – Stores temporary data such as local variables.
- **Data Section** – Contains global variables.
- **Heap** – Memory dynamically allocated during execution.

### **Process Representation in Memory**

A process is structured as:

Process Memory={Code,Stack,Heap,Data}\text{Process Memory} = \{\text{Code}, \text{Stack}, \text{Heap}, \text{Data}\}Process Memory={Code,Stack,Heap,Data}

---
## **4. Process Control Block (PCB)**

Each process is represented by a **Process Control Block (PCB)**, also called a **Task Control Block**.

The OS maintains a **process table** containing all PCBs.

### **PCB Structure:**

- **Process ID (PID)** – Unique identifier.
- **Process State** – Running, waiting, ready, etc.
- **CPU Registers** – Stores values when switching processes.
- **CPU Scheduling Info** – Includes priority and scheduling algorithms.
- **Memory Management Info** – Tracks memory allocation.
- **I/O Status** – Lists open files and I/O devices.

---
## **5. Process States**

A process transitions between different states:

1. **New** – Process is being created.
2. **Running** – Process is executing instructions.
3. **Waiting** – Process is waiting for an event (e.g., I/O).
4. **Ready** – Process is ready to run but waiting for CPU.
5. **Terminated** – Process has finished execution.

---
## **6. Process Creation**

Processes are created by other processes, forming a **hierarchy (process tree)**.

### **Execution Models:**

1. **Parent & Child execute concurrently.**
2. **Parent waits until the child process terminates.**

### **Resource Sharing:**

1. **Parent and child share all resources.**
2. **Child inherits a subset of parent’s resources.**
3. **Parent and child share no resources.**

### **Process Creation in UNIX**

- **`fork()`** – Creates a new child process.
- **`exec()`** – Replaces the child’s memory with a new program.

---
## **7. Process Termination**

A process **terminates** when it finishes execution or is killed by the OS.

- **A child process may terminate when:**
    - It has exceeded allocated resources.
    - The assigned task is no longer required.
    - The parent terminates (leading to **cascade termination**).

### **Special Cases:**

- **Zombie Process** – A terminated process that still exists in the process table (waiting for the parent to collect exit status).
- **Orphan Process** – A child process whose parent has terminated.

---
## **8. Process Scheduling**

To maximize **CPU utilization**, the OS **schedules processes** efficiently.

### **Scheduling Queues:**

- **Job Queue** – All system processes.
- **Ready Queue** – Processes in memory, ready for execution.
- **Device Queues** – Processes waiting for I/O devices.

Processes migrate among these **queues**.

---
## **9. The Kernel**

The **Kernel** provides an **environment** for processes to execute.

### **Essential Kernel Components:**

1. **Privileged Instruction Set** – Only executable by the OS.
2. **Interrupt Mechanism** – Handles hardware/software interrupts.
3. **Memory Protection** – Prevents unauthorized access.
4. **Real-Time Clock** – Provides time-based operations.

### **Kernel Subsystems:**

- **First-Level Interrupt Handler (FLIH)** – Determines and prioritizes interrupts.
- **Dispatcher (Scheduler)** – Assigns CPU time to processes.

---
## **10. Dispatcher**

The **dispatcher** selects a process for execution when:

- A **process cannot continue**.
- **An interrupt occurs**, causing a switch.
- **A system call suspends execution**.
- **An error forces process termination**.

---
## **11. Threads**

A **thread** is the **smallest unit of execution** within a process.

Each thread:

- **Belongs to a process**.
- **Has its own execution context** (registers, stack).
- **Shares memory and resources** with other threads in the same process.

### **Thread Types:**

1. **User Threads** – Managed in user space.
2. **Kernel Threads** – Managed by the OS.

---
## **12. Multithreading vs. Single Threading**

- **Multithreading** – An OS supports multiple threads within a single process.
- **Single Threading** – No thread distinction (e.g., MS-DOS).

### **Thread Memory Model**

- **Local variables** – Stored in the **stack** (each thread has its own).
- **Global variables** – Stored in the **data section**, shared across all threads.

---
## **13. Benefits of Multithreading**

1. **Faster Context Switching** – Less overhead than switching processes.
2. **Improved Responsiveness** – UI remains interactive even if a thread is blocked.
3. **Efficient Resource Sharing** – Threads **share memory and resources**.
4. **Economy** – Threads are **cheaper** to create than processes.
5. **Scalability** – Threads **utilize multi-core CPUs** efficiently.

---
## **14. Concurrency vs. Parallelism**

- **Concurrency** – Tasks **appear** to execute **simultaneously** on a single-core CPU.
- **Parallelism** – Tasks execute **simultaneously** on **multiple cores**.

### **Amdahl’s Law**

Amdahl’s Law calculates the **performance improvement** when adding cores:
$$
Speedup = \frac{1}{S+\frac{1-S}{N}}
$$
where:

- $S$ = **Serial portion** of execution.
- $N$ = **Number of processing cores**.
As $N$ increases, the speedup is **bounded by the serial portion**.

---
## **15. Multithreading Models**

### **1. Many-to-One**

- Multiple **user threads** map to a **single kernel thread**.
- **Blocking one thread blocks all threads**.
- **Example:** Solaris Green Threads.

### **2. One-to-One**

- Each **user thread** maps to **one kernel thread**.
- **More concurrency but higher overhead**.
- **Examples:** Windows, Linux.

### **3. Many-to-Many**

- **Multiple user threads** map to **multiple kernel threads**.
- **OS dynamically manages kernel threads**.
- **Examples:** Solaris (before version 9), Windows (ThreadFiber package).

---
## **16. Thread Creation**

Threads are created using **thread libraries**, which provide an **API** for managing threads.

### **Thread Implementation:**

1. **User-Space Thread Library** – Threads managed **without OS support**.
2. **Kernel-Level Thread Library** – OS manages **thread scheduling**.
