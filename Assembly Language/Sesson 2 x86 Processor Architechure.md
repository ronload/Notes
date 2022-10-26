# Sesson 2: x86 Processor Architecture

## Basic Microcomputer design

### Central Processor Unit (CPU):

 Where calculations and logic operations take place, which contains:

1.   Registers (暫存器): Storage locations.

2.   Clock: Synchronizes the internal operations of the CPU with other system component.

3.   Control Unit (CU) : Coordinates the sequencing of steps involved in executing machine instruction.

4.   The Arithmetic Logic Unit (ALU): Performs arithmetic operations such as addition and subtraction and logical operations such as AND, OR, NOT.<img src="Photos/Screen Shot 2022-10-26 at 6.55.58 PM.png" alt="Screen Shot 2022-10-26 at 6.55.58 PM" style="zoom:40%;" />

5.   Memory Storage Unit: Where instructions and data are held while a computer program is running.

6.   Bus: A bus is group of parallel wires that transfer data from one part of the computer to another. A computer’s system bus usually consists of there separate buses:
     1.   Data bus: Transfers instructions and data between the CPU and memory.
     2.   Control bus: Uses binary signals **synchronize actions of all device** attached to the system bus.
     3.   Address bus: Holds the addresses of instructions and data when the currently executing instruction transfers data **between the CPU and memory**.

7.   Clock: 

     Each operation involving the CPU and the system bus is synchronized by an internal clock pulsing at a constant rate.

     1.   **The basic unit of time for machine instruction is a machine cycle (or clock cycle).**

          <img src="Photos/Screen Shot 2022-10-26 at 7.07.18 PM.png" alt="Screen Shot 2022-10-26 at 7.07.18 PM" style="zoom:40%;" />

     2. A clock that oscillates(震盪) 1 billion times per second (1 GHz), for example, produces a clock cycle with a duration of one billionth of a second (1 nanosecond).

     3. A machine instruction required **at least one clock cycle** to execute, and a few require in excess of 50 clocks.

     4. Instructions requiring memory access often have empty clock cycles called **wait states** because of the differences in the speeds of the CPU, the system bus, and memory circuits.

8.   Instruction Execution Cycle:

     The execution of a single machine instruction can be divided into a sequence of individual operations called the **instruction execution cycle**.

     1.   Fetch: The control unit fetches the instruction from the instruction queue and **increments the instruction pointer** (IP).
          1.   The instruction queue holds a group of instructions about to be executed.
          2.   The instruction is also known as the program counter.
          3.   The instruction pointer contains the **address** of the next instruction.
     2.   Decode: The control unit decodes the instruction's function to determine what the instruction will do.
     3.   Fetch operands: The instruction uses an input operand located in memory, the control unit uses a read operation to retrieve the operand and copy it into internal registers.
     4.   Execute: The ALU executes the instruction using the **named registers and internal registers** as operands and sends the output to **named registers and/or memory**. The ALU updates status flags providing information about the processor state.
     5.   Store output operand: If the output operand is in memory, the control unit uses a write operation to store the data.

9.   Reading from Memory:

     Multiple machine cycles are required when reading from memory, because it responds much more slowly than the CPU. The steps are:

     1.   Place the address of the value you want to read on the address bus.

     2.   Assert (changing the value of) the processor’s RD (read) pin.
     3.   Wait one clock cycle for the memory chips to respond.
     4.   Copy the data from the data bus into the destination operand.<img src="Photos/Screen Shot 2022-10-26 at 7.45.47 PM.png" alt="Screen Shot 2022-10-26 at 7.45.47 PM" style="zoom:40%;" />

10.   Cache memory:

      1.   High-speed expensive static RAM both inside and outside the CPU.

           1.   Level-1 cache: inside the CPU.

           2.   Level-2 cache: outside the CPU.

      2.   Cache hit: When data to be read is already in cache memory.

      3.   Cache miss: When data to be read is not in cache memory.

### How a Program Runs:

#### 1. Load and execute process:

1.   The program begins running, it is called a **process**.

2.   The OS assigns the process an identification number (process ID), which is used to keep track of it while running.

     <img src="Photos/Screen Shot 2022-10-26 at 7.54.51 PM.png" alt="Screen Shot 2022-10-26 at 7.54.51 PM" style="zoom:50%;" />

#### 2. Multitasking: 

1.   Task:

     1.   A task is defined as either a program (a process) or a thread of execution.

     2.   A process has it own memory area and many contain multiple threads.

     3.   A thread shares its memory with other threads **belonging to the same process**.
2.   Scheduler:

     1.   A CPU can really execute **only one instruction** at a time.

     2.   Scheduler utility assigns a given amount of CPU time to each running program.

     3.   One type of scheduling used by the OS is called round-robin scheduling.
3.   Task switching:
     1.   A multitasking OS runs on a processor that supports task switching.
     2.   The processor saves the state of each task **before switching to a new one**.
     3.   A task’s state: Contents of the processor registers, program counter, and status flags...
4.   Priority:
     1.   A multitasking OS will usually assign varying priorities to tasks (larger or smaller time).
     2.   A preemptive multitasking OS (such as Windows XP or Linux) permits a higher priority task to interrupt a lower-priority one, leading to better system stability.

### IA-32 Processor Architechture

#### Modes of Operation:

1.   Protected mode: Native mode (Windows, Linux).
2.   Real-address mode: Native MS-DOS.
3.   System management mode: Power management, system security, diagnostics.
4.   Virtual-8086 mode: 
     1.   Hybrid of Protected.
     2.   Each program has its own 8086 computer.

#### Basic Execution Enviroment:

1.   Addressable Memory:
     1.   Protected mode:
          1.   4 GB.
          2.   32-bits address.
     2.   Real-address and Virtual-8086 modes
          1.   1 MB space.
          2.   20-bit address.

2.   General-Purpose Register:

     Named storage locations inside the CPU, optimized for speed.<img src="Photos/Screen Shot 2022-10-26 at 8.25.38 PM.png" alt="Screen Shot 2022-10-26 at 8.25.38 PM" style="zoom:40%;" />

     **Accessing part of register:**

     1.   Use 8-bit name, 16-bit name, or 32-bit name.

     2.   Applies to **EAX, EBX, ECX, and EDX**. 

          <img src="Photos/Screen Shot 2022-10-26 at 8.29.00 PM.png" alt="Screen Shot 2022-10-26 at 8.29.00 PM" style="zoom:40%;" />

3.   Index and Base Registers:

     1.   Some registers have only a 16-bit name for their lower half: 

          <img src="Photos/Screen Shot 2022-10-26 at 8.32.46 PM.png" alt="Screen Shot 2022-10-26 at 8.32.46 PM" style="zoom:50%;" />

     2.   Some Specialized Register Uses (1 of 2):

          1.   General-Purpose: 
               1.   EAX – accumulator
               2.   ECX – loop counter
               3.   ESP – stack pointer
               4.   ESI, EDI – index registers
               5.   EBP – extended frame pointer (stack)
          2.   Segment:
               1.   CS – code segment
               2.   DS – data segment
               3.   SS – stack segment
               4.   ES, FS, GS - additional segments

     3.   Some Specialized Register Uses (2 of 2):

          1.   EIP – instruction pointer
          2.   EFLAGS
               1.   Status and control flags.
               2.   Each flag is a single binary bit.

4.   Status Flags:

     1.   Carry: Unsigned arithmetic out of range.
     2.   Overflow: Signed arithmetic out of range.
     3.   Sign: Result is negtive.
     4.   Zero: Result is zero.
     5.   Auxiliary Carry: Carry from bit 3 to bit.
     6.   Parity: Sum of 1 bits is an even number.

5.   Floating-Point, MMX, XMM Register:

     1.   Eight 80-bit floating-point data registers

          1.   ST(0), ST(1), ..., ST(7)

          2.   Arrange in stack.

          3.   Used for all floating-point arithmetic.

               <img src="Photos/Screen Shot 2022-10-26 at 8.43.15 PM.png" alt="Screen Shot 2022-10-26 at 8.43.15 PM" style="zoom:50%;" />

     2.   Eight 64-bit MMX register.

     3.   Eight 128-bit XMM registers for single-instruction multiple-data (SIMD) operations.

### IA-32 Memory Management

#### Real-address mode

1 MB RAM maximum addressable, from hexadecimal 00000 to FFFFF

1.   Application programs can access any area of memory.

2.   Single tasking.

3.   Support by MS-DOS operating system: Windows 95 and WIndows 98 can be booted into this mode.

4.   Segmented Memory:

     1.   All memory is devided into 64KB(216bytes) units called segments.

     2.   Segmented memory adddressing:

          Absolute(linear) address is a combination of a 16-bits segment value add to a 16-bits offset.