# Sesson 1: Basic Concept

## Assembly Language Applications

1.   Business application for single platform
2.   Hardware device driver
3.   Business application for multiple platform
4.   Embedded system (嵌入式系統) and computer game

## Virtual Machine Concept

### Programming language:

1.   L0: Native language, run directly on its hardware.
2.   L1: A more human-friendly language, usually constructed by machine language.

### L1 Programs can run in 2 different ways

1.   Interpretation: L0 program interprets and executes L1 instructions one by one.
2.   Translation: L1 program is completely translated into an L0 program.

## Specific Machine Levels

1.   High-Level Language (Level 5):
     1.   Application-oriented language(C++, Java, Pascal, Visual Basic)
     2.   Programs compile into assembly language.
2.   Assembly Language (Level 4): 
     1.   Instruction ”words” that have a one-to-one correspondence to machine language.
     2.   Programs are translated into Instruction Set Architecture Level – machine language.

3.   Operating System (Level 3):
     1.   Provides services to Level 4 programs.
     2.   Translated and run at Level 2.
     3.   Operating System understands interactive commands by users to load and execute programs, display directories, etc.
4.   Instruction Set Architecture (Level 2)
     1.   Also known as Conventional Machine Language.
     2.   Executed by Microarchitecture (Level 1).
5.   Microarchitecture (Level 1):
     1.   Interprets conventional machine instructions (Level 2).
     2.   Executed by digital hardware (Level 0).
     3.   Specific microarchitecture commands are often a proprietary secret.
6.   Digital Logic (Level 0):
     1.   CPU, constructed from digital logic gates.
     2.   System Bus•Memory.
     3.   Implemented using bipolar transistors.