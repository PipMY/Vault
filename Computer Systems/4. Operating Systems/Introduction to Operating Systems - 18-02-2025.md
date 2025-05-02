## **1. Why Do We Need an Operating System?**

The operating system serves two key purposes:

### **a. OS as an Abstract Machine**

- Provides **high-level abstractions** for programmers.
- **Hides hardware details**, making applications **portable**.
- Example: A **filesystem** abstracts disk operations.

### **b. OS as a Resource Manager**

- **Allocates resources** to processes/users.
- Ensures **no starvation** and **fairness** using scheduling policies.
- Examples of allocation policies:
    - **First-Come, First-Served (FCFS)**
    - **Round Robin (RR)**

---

## **2. Definition & Goals of an OS**

### **Definition:**

An **Operating System (OS)** is a program that acts as an **intermediary** between a **user** and the **hardware**.

### **Goals of an OS:**

- Execute user programs.
- Make the system easy to use.
- Manage resources **efficiently and fairly**.

---

## **3. Structure of a Computer System**

### **Four Main Components:**

1. **Hardware** – Provides basic computing resources (CPU, memory, I/O).
2. **Operating System** – Manages resources and hardware interactions.
3. **Application Programs** – Define user tasks (Word processors, Web Browsers).
4. **Users** – Can be humans, machines, or other computers.

---

## **4. Roles of the OS**

The OS plays multiple roles:

### **a. Resource Allocator**

- **Manages system resources**, such as CPU, memory, and I/O.

### **b. Control Program**

- Prevents **errors and improper use** of the system.

### **c. Kernel**

- The **core** part of the OS that **runs all the time**.
- Executes in **privileged mode**.

---

## **5. Dual-Mode Operation**

To protect the system, modern CPUs support **dual-mode operation**:

- **User Mode** – Executes application programs.
- **Kernel Mode** – Executes **OS code** and privileged instructions.

The **mode bit** in hardware:

- **0** → **Kernel mode** (privileged execution).
- **1** → **User mode** (restricted execution).

A **system call** switches execution from **User Mode → Kernel Mode**.

### **Privileged Instructions**

Certain operations can only be executed in **Kernel Mode**:

- **Enabling/disabling interrupts**.
- **Performing I/O operations**.
- **Halting a process**.

### **How Mode Switching Happens**

A transition from **User Mode → Kernel Mode** happens when:

- A **system call** is made (e.g., `read()`, `write()`).
- A **hardware interrupt** occurs.
- A **process error** happens.

---

## **6. Operating System Types**

### **a. Multi-User OS**

- Supports **multiple users** running programs **simultaneously**.

### **b. Multi-Programming OS**

- Multiple processes are loaded into memory to **maximize CPU utilization**.

### **c. Multi-Tasking OS**

- The CPU **rapidly switches** between tasks, creating an **interactive experience**.

### **d. Multi-Threading OS**

- A **single process** can run **multiple threads concurrently**.

### **e. Real-Time OS (RTOS)**

- Guarantees **instant response** to input.

---

## **7. Multi-Programming & Multi-Tasking**

### **Multi-Programming**

- Improves CPU efficiency by **loading multiple jobs** in memory.
- Uses **job scheduling** to decide which job to run.
- The OS **switches jobs** when a running job needs I/O.

### **Multi-Tasking (Time-Sharing)**

- **Extends Multi-Programming** for **interactive computing**.
- The CPU **rapidly switches** between processes.
- If a process is waiting for I/O, the OS **swaps** another process in.

---

## **8. Operating System Services**

### **Services Provided by an OS**

1. **User Interface** – CLI (Command Line), GUI (Graphical).
2. **Program Execution** – Loads and runs user programs.
3. **I/O Operations** – Manages file and device interactions.
4. **File-System Manipulation** – Reads/writes files, manages permissions.
5. **Inter-Process Communication (IPC)** – Allows communication via **shared memory** or **message passing**.
6. **Error Detection** – Handles hardware/software errors.

### **Resource Allocation**

- **Manages CPU, memory, disk, and I/O devices**.
- Ensures **efficient sharing** in multi-user environments.

### **Security & Protection**

- **Prevents unauthorized access** using authentication.
- **Prevents process interference** using access controls.

---

## **9. OS Interfaces**

Operating systems provide two main interfaces:

### **a. Command-Line Interface (CLI)**

- User **types commands** to interact with the OS.
- Example: Unix Shell, Windows Command Prompt.

### **b. Graphical User Interface (GUI)**

- User **interacts via icons, windows, and buttons**.
- Example: Windows, macOS, Linux GUI (GNOME, KDE).

Most modern OSes support **both CLI and GUI**.

---

## **10. Operating System Design**

### **Principles of OS Design**

- **User Goals** – The OS should be **easy to use, secure, and reliable**.
- **System Goals** – The OS should be **efficient, maintainable, and flexible**.

### **Policy vs. Mechanism**

- **Policy:** Defines **what** should be done.
- **Mechanism:** Defines **how** it should be done.

This **separation provides flexibility** to change policies later.

---

## **11. Operating System Structures**

Operating systems can be structured in different ways:

### **a. Monolithic (Unix, Linux, Windows)**

- Everything is **tightly integrated** in a single module.
- **Fast but difficult to maintain**.

### **b. Layered Approach**

- OS is **divided into layers**, each layer **only interacts with the layer below**.
- **Example:** THE Operating System.

### **c. Microkernel Approach**

- Moves **most OS functions into user space**.
- Uses **message passing** for communication.
- **Example:** macOS (based on **Mach**).

**Trade-off:** **More secure and modular**, but **slower due to communication overhead**.