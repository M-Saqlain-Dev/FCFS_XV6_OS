## **Enhancements and Additions to XV6 Operating System**

### Introduction
The XV6 operating system, a teaching tool developed at MIT, provides a minimal but functional representation of the UNIX operating system. As part of the project scope, several enhancements and modifications were made to the baseline XV6 system. This report provides a detailed overview of these changes.

### **1. System Call Implementation**

#### **1.1 Addition of `report_statistics()` System Call**
- **Location**: `proc.c`, `syscall.c`, and relevant header files.
- **Description**: 
   - A new system call, `report_statistics()`, has been implemented. This call provides statistics and diagnostics about process execution, aiding in system introspection.
- **Purpose**:
   - To gain insight into process-related metrics for debugging, performance tuning, and monitoring.

### **2. Scheduler Enhancements**

#### **2.1 FCFS (First-Come-First-Serve) Scheduling**

- **Location**: `proc.c`
- **Description**: 
   - Modification from the round-robin algorithm to a First-Come-First-Serve (FCFS) scheduling mechanism.
- **Implementation**:
   1. **Sorting Based on Arrival Time**:
       - Processes are sorted based on their `arrival_time` attribute.
       - Ensures the earliest arriving process gets scheduled next.
   2. **Modification to the Scheduler Loop**:
       - Instead of the standard round-robin, the loop picks the process with the earliest `arrival_time` that is in a `RUNNABLE` state.
- **Purpose**:
   - To provide a predictable execution order based on when processes enter the system.

#### **2.2 Adjustments for Context Switching**:

- **Description**:
   - Necessary adjustments made to ensure proper context switching and process state management in the new scheduling environment.
   - Ensures no process starvation and maintains system interactivity.

#### **2.3 Incorporating New Attributes**:

- **Description**:
   - Attributes `arrival_time`, `start_time`, and `end_time` added to the `proc` structure.
   - Assists the scheduler in determining the order of process execution and provides data for performance analysis.

### **3. Error Handling and Diagnostics**

- **Location**: Various files, including `syscall.c` and `proc.c`.
- **Description**: 
   - Enhanced error handling mechanisms to catch and report system errors.
   - Provides clearer feedback to developers and end-users, aiding in troubleshooting.

### **4. Code Refactoring and Cleanup**

- **Location**: Various files across the system.
- **Description**: 
   - Periodic refactoring and code cleanup operations were performed to enhance code readability, maintainability, and performance.

### Conclusion

The XV6 operating system has undergone several significant modifications to enhance its functionality, reliability, and diagnostic capabilities. These changes, ranging from the introduction of new system calls to alterations in the scheduling algorithm, ensure that the system is better suited to contemporary needs while maintaining the teaching essence of XV6. Clients are encouraged to review these changes in detail to fully comprehend the breadth and depth of the enhancements.

---

You can share this comprehensive report with your client.
