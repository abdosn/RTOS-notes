# RTOS-notes
RTOS Notes and tasks

The Operating System is a system which takes number of Tasks and perform them in a specific time called Periodicity. 

Task is nothing but a piece of code that repeated every specific time. Every task has its own periodicity . The OS will Synchronize between these task Simply.

> Real-Time system is a system thaqt respond to external event in a timely fashion

Real-Time system is a software system which the correct functioning of the system depends on the results produce by the system and the time which those rsults are produced

Real-time operating systems (RTOS) are used in environments where a large number of events, mostly external to the computer system, must be accepted and processed in a short time or within certain deadlines. such applications are industrial control, telephone switching equipment, flight control, and real-time simulations.  With an RTOS, the processing time is measured in tenths of seconds. This system is time-bound and has a fixed deadline. The processing in this type of system must occur within the specified constraints. Otherwise, This will lead to system failure.

Examples of real-time operating systems are airline traffic control systems, Command Control Systems, airline reservation systems, Heart pacemakers, Network Multimedia Systems, robots, etc.

Multitasking is a process of scheduling and switching the Central processing unit (CPU) between several tasks .
A single CPU switches its attention between several sequential tasks
Application programs are typically easier to design and maintain if multitasking is used.

Task, or also called a thread, is a simple program that thinks it has the CPU all to itself.
Task is a function which Takes void and returns void only contains some lines of codes. Every task could be periodic task .

Tasks have main three parameters:
1. **Function** (pointer to function) *The lines of code that will be executed by CPU.* 

2. **Periodicity** *The periodic time of the task to be executed.*

3. **Priority** *the more importance the task , the higher priority given to it .*

a Task my be repsented as
```
typedef struct
{
    u8 periodiety;
    u8 priority;
    void *(Fptr)(void);
}Task;
```

Task States:

1. **Dormant** *Task that resides in memory but has not been passed to the RTOS to start scheduling.*

2. **Ready** *Task that can execute but its priority is less than the currently running task*

3. **Running** *Task that has the control of CPU.*

4. **Waiting** *Task that requires the occurrence of an event.(for ex “waiting for an I/o operation”)*

5. **ISR** *When an interrupt has occurred and the CPU is in the process of service the interrupt*


Types of RTOS
There're 2 famous types
the last two s not widely common
1. **Hard Real-Time Operating System**:  *These operating systems guarantee that critical tasks are completed within a range of time.*

For example, a robot is hired to weld a car body. If the robot welds too early or too late, the car cannot be sold, so it is a hard real-time system that requires complete car welding by the robot hardly on time., scientific experiments, medical imaging systems, industrial control systems, weapon systems, robots, air traffic control systems, etc.
 

2. **Soft real-time operating system**: *This operating system provides some relaxation in the time limit.* 

For example – Multimedia systems, digital audio systems, etc.


3. **Firm Real-time Operating System**: *is a middle ground between hard and soft RTOS types, RTOS of this type have to follow deadlines as well*. 

In spite of its small impact, missing a deadline can have unintended consequences, including a reduction in the quality of the product.

Example: Multimedia applications.

4. **Deterministic Real-time operating System**: *timing must be permanently precise , Consistency is the main key in this type of real-time operating system. It ensures that all the task and processes execute with predictable timing all the time*

which make it more suitable for applications in which timing accuracy is very important. Examples: INTEGRITY, PikeOS.


Multitasking operation is accomplished by scheduling processes for execution independently of each other. Each process is assigned a certain level of priority that corresponds to the relative importance of the event that it services. The processor is allocated to the highest-priority processes. This type of schedule, called, priority-based preemptive scheduling is used by real-time systems.

RTOS in layered architeture

| App |
| --- |
| RTOS |
| Hardware |

RTOS services

* Task management
* Inter-task communication
* Device I/O supervisory
* Dynamic memory allocation
* Timers

RTOS advantages

* **Reliability** *Real time operating systems, especially those which are of hard RTOS are completely free of errors. It ensures a better way of handling errors. Besides, operating systems experience an issue known as jitter in which the amount of errors between subsequent loops is measured. If programmed correctly, a RTOS can be optimized in a way that it undergoes less amount of jitters.*

* **Predictability** *A task can be predictable in time that it will be served and how much time and memory can be used for each task*
* **Performance** *Increases performance of timing and memory*
* **Compactness** 
* **Scalability** *Can be run for many compilers and targets with the same source code*