# Sesson 2: x86 Processor Architecture

## Basic Microcomputer design

### Central Processor Unit (CPU):

 Where calculations and logic operations take place, which contains:

1.   Registers (暫存器): Storage locations.
2.   Clock: Synchronizes the internal operations of the CPU with other system component.
3.   Control Unit (CU) : Coordinates the sequencing of steps involved in executing machine instruction.
4.   The Arithmetic Logic Unit (ALU): Performs arithmetic operations such as addition and subtraction and logical operations such as AND, OR, NOT.<img src="/Users/luoyongneng/Working/Notes/Assembly Language/Photos/Screen Shot 2022-10-26 at 6.55.58 PM.png" alt="Screen Shot 2022-10-26 at 6.55.58 PM" style="zoom:40%;" />

5.   Memory Storage Unit: Where instructions and data are held while a computer program is running.
6.   Bus: A bus is group of parallel wires that transfer data from one part of the computer to another. A computer’s system bus usually consists of there separate buses:
     1.   Data bus: Transfers instructions and data between the CPU and memory.
     2.   Control bus: Uses binary signals synchronize actions of all device attached to the system bus.
     3.   Address bus: Holds the addresses of instructions and data when the currently executing instruction transfers data between the CPU and memory.

7.   Clock: 

     Each operation involving the CPU and the system bus is synchronized by an internal clock pulsing at a constant rate.

     1.   The basic unit of time for machine instruction is a machine cycle (or clock cycle).

          <img src="/Users/luoyongneng/Working/Notes/Assembly Language/Photos/Screen Shot 2022-10-26 at 7.07.18 PM.png" alt="Screen Shot 2022-10-26 at 7.07.18 PM" style="zoom:40%;" />

     2. A clock that oscillates(震盪) 1 billion times per second (1 GHz), for example, produces a clock cycle with a duration of one billionth of a second (1 nanosecond).
     
     3. A machine instruction required at least one clock cycle to execute, and a few require in excess of 50 clocks.
     
     4. 
