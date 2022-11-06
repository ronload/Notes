# Sesson 3: Assembly Language Fundamentals

## Basic Elements of Assembly Language

### Integer constants

1.   Optional leading + or – sign

2.   binary, decimal, hexadecimal, or octal digits

3.   Common radix characters:

     1.   h – hexadecimal

     2.   d – decimal

     3.   b – binary

     4.   r – encoded real

     5.   Examples: 30d, 6Ah, 42, 1101b 
     > Hexadecimal beginning with letter: 0

### Character and String Constants

1.   Enclose character in single or double quotes
     1.   'A', "x"
     2.   ASCII character = 1 byte
2.   Enclose strings in single or double quotes
     1.   "ABC"
     2.   'xyz'
     3.   Each character occupies a single byte
3.   Embedded quotes:
     1.   'Say "Goodnight,"

### Reserve Words and Identifiers

1.   Reserved words cannot be used as identifiers

     1.   Instruction mnemonics, directives, type attributes, operators, predefined symbols

2.   Identifiers

     1.   1-247 characters, including digits

     2.   not case sensitive

     3.   first character must be a letter, _, @, ?, or $

### Directives

1.   Commands that are recognized and acted upon by the assembler
     
     1.   Not part of the Intel instruction set
        
     2.   Used to declare code, data areas, select memory model, declare procedures, etc.
          
     3.   not case sensitive
2.   Different assemblers have different directives

     1.   NASM not the same as MASM, for example

### Instructions

1.   Assembled into machine code by assembler

2.   Executed at runtime by the CPU

3.   We use the Intel IA-32 instruction set

4.   An instruction contains:

     1.   Label(optional)

     2.   Mnemonic(required)

     3.   Operand(depends on the instruction)

     4.   Comment(optional)

     >   [Label:] Mnemonic Operand(s) [; Commen]

### Lables

1.   Acts as place marker
     1.   Marks the address(offset) of code and data
    
2.   Follow identifier rules

3.   Data label
     1.   Must be unique
     2.   example: myArray (not follow by colon)
     
4.   Code label
     1.   Target of jump and loop instructions
     2.   example: L1: (follow by colon)
### Mnemonics and Operand

1.   Instruction Mnemonics
     
     1.   memory aid
     
     2.   examples: mov, add, sub, inc, dec
     
2.   Operands
     
     1.   Constant
     2.   Constant expression
     3.   Register
     4.   Memory (data label)
     
     >   Constant and constant label are often are often called immediate values
     
### Comments

1.   Adventages

     1.   explain the program's purpose

     2.   when it was written, and by whom

     3.   revision information

     4.   tricky coding techniques

     5.   application-specific explanation

2.   Single line comments: begin with ';'

     ```assembly
      code ;comments
     ```

3.   Multiple line comments:

     1.   begin with "COMMENT" directive and programmer-chosen character

      2.   end with the same programmer-chosen character

           ```assembly
           code
           COMMENT !
           	;Here is the comment
           	mov ax, bx
           	add ax, 7
           !
           ```

           ​    

#### Instruction Format Example

1.   No operands:  

     ```assembly
     stc ;set Carry flag
     ```

2.   One operands:

     ```assembly
     inc eax      ;register
     inc myByte   ;memory
     ```

3.   Two operands:

     ```assembly
     add ebx, ecx    ;register, register
     sub myByte, 25  ;memory, constant
     add eax, 36*25  ;register, constant-expression
     ```

## Example: Adding and Substracting Integers

```assembly
;AddTwo.asm - adds two 32-bits integets

.386
.model flat, stdcall
.stack 4096
ExitProcess PROTO, dwExitCode: DWORD
.code
main PROC
	mov eax, 5 ; int eax = 5;
	add eax, 6 ; eax = eax + 6;
	
	INVOKE ExitProcess 0
main ENDP
END main
```

## Suggested Coding Standards

1.   Some approaches to capitalize

     1.   capitalize nothing
     2.   capitalize evetything
     3.   capitalize all reserve words, including instruction mnemonics and register names
     4.   capitalize only directives and operators

2.   Other

     1.   descriptive identifiers name
     2.   spaces surrounding arithmetic operators
     3.   blank lines between procedure

3.   Indentation and spacing

     1.   code and labels: no indentation
     2.   executable instructions: indent
     3.   comments: right side of page, aligned vertically
     4.   1-2 blank lines between procedure

4.   Program template

     ```assembly
     ; Program template
     
     ; Description:
     ; Author: 
     ; Creation Date:
     ; Revisions:
     ; Date:
     ; Modified by:
     
     .386
     .model flat, stdcall
     ExitProcess PROTO, dwExitCode:DWORD
     .data
     ; declare variables here......
     
     .code
     main PROC
     	; write yout code here......
     	INVOKE ExitPrcess, 0
     main ENDP
     
     ; insert additional procedures here
     END main
     ```

     

## Assembly, Linking, and Running Programs

### Assemble-Link Execute Cycle

1.   The following diagram describes the step from creating a source program through executing the compiled program.
2.   If the source file is modified, step 2 though 4 must be repeat.

<img src="Photos/Screenshot 2022-11-05 at 7.44.55 PM.png" alt="Screenshot 2022-11-05 at 7.44.55 PM" style="zoom:30%;" />

3.   The assembler contains a **preprocessor** to process directives, etc.

### LIsting FIle

1.   Use it to see how your program is compiled.

2.   Contains

     1.   source code
     2.   addresses
     3.   object code (machine language)
     4.   segment names
     5.   symbols (variables, procedures, constants)


### The NOP Instruction

1.   Code alignment: Align next instruction.

2.   Check from a list file

3.   Debug from DIsassembly window:

     ``` assembly
     ...
     ...
     ...
     .code
     main PROC
     	mov ax, bx
     00401010 66 8B C3      mov  ax,bx
     	nop
     00401013 90            nop
     	mov edx, ecx
     00401014 8B D1         mov  edx,ecx
     
     exit
     ```

### Map File

Information about each program segment:

1.   starting address
2.   ending address
3.   size
4.   segment type

## Defining Data

### Instrinsic Data Types

1.   BYTE, SBYTE: 8-bit unsigned integer; 8-bit signed integer

2.   WORD, SWORD: 16-bit unsigned & signed integer

3.   DWORD, SDWORD: 32-bit unsigned & signed integer

4.   QWORD: 64-bit integer

5.   TBYTE: 80-bit integer

6.   REAL4: 4-byte IEEE short real

7.   REAL8: 8-byte IEEE long real

8.   REAL10: 10-byte iEEE extended real

### Data Definition Statement

1.   A data definition statement setss aside storage in memory for a variable.

2.   May optionally assign a name(label) to the data.

3.   Syntax: [name] [directive initializer] [initializer]

     ```assembly
     value1 BYTE 10
     ```

4.   All initializers become binary data in memory.

### Define BYTE and SBYTE Data

Each of the following defines a single byte of storage:

```assembly
value1 BYTE 'A'   ; charactar constant
value2 BYTE 0     ; smalllest unsigned vyte
value3 BYTE 255   ; largest unsigned byte
value4 SBYTE -128 ; smallest signed byte
value5 SBYTE +127 ; largest signed byte
value6 BYTE ?     ; uninitialized byte
```

>   MASM does not prevent you from initializing a BYTE with a negative  vlaue, but it's considered poor style.
>
>   If you declare a SBYTE variable, the Microsoft debugger will automatically display its value in decimal with a leading sign.

### Define Byte Arrays

Examples that use multiple initializers:

```assembly
list1 BYTE 10, 20, 30, 40
list2 BYTE 10, 20, 30, 40
			BYTE 50, 60, 70, 80
			BYTE 81, 82, 83, 84
list3 BYTE ?, 32, 41h, 00100010b
list4 BYTE 0Ah, 20b, 'A', 22h
```

### Define Strings

1.   A string is implemented as an array of characters

     1.   From convenience, it is usually enclosed in quotation marks.
     2.   It often will be null-terminated.

2.   Examples:

     ```assembly
     str1 BYTE "Enter your name", 0
     str2 BYTE "Error: halting program", 0
     str3 BYTE 'A', 'E', 'I', 'O', 'U'
     greeting BYTE "Welcome to the Encryption Demo program "
     				 BYTE "created by Kip Irvine.", 0
     ```

3.   To continue a single string across multiple lines, end each line with a comma

     ```assembly
     menu BYTE "Checking Account", 0dh, 0ah, 0dh, 0ah
     		"1. Create a new account", 0dh, 0ah
     		"2. Open an existing account", 0dh, 0ah
     		"3. Credit the account", 0dh, 0ah
     		"4. Debit the account", 0dh, 0ah
     		"5. Exit", 0dh, 0ah
     		"Choice> ", 0
     ```

4.   End-of-line character sequence:

     1.   0Dh = carriage return

     2.   0Ah = line feed

          ```assembly
          str1 BYTE "Enter your name: ", 0Dh, 0Ah
          		 BYTE "Enter your address: ", 0
          newLine BYTE 0Dh, 0Ah, 0
          ```

>   Define all strings used by your program in the same area of the data segment.

### Using the DUP Operator

1.   Use DUP to allocate(create space for) an array or string.

     Syntax: counter DUP(argument)

2.   Counter and argument must be constants or constant expressions

``` assembly
var1 BYTE 20 DUP(0)				  ; 20 bytes, all equal to zero
var2 BYTE 20 DUP(?)				  ; 20 bytes, uninitialized
var3 BYTE 4 DUP("STACK")    ; 20 bytes, "STACKSTACKSTACKSTACK"
var4 BYTE 10, 3 DUP(0), 20  ; 5 bytes
```

### Define WORD and SWORD Data

1.   Define storage for 16-bit integers
     1.   or double characters
     2.   Single value or multiple values

```assembly
word1  WORD 65535					 ; largest unsigned value
word2  SWORD -32768				 ; smallest signed value
word3  WORD ?					 		 ; uninitialized, unsigned
word4  WORD "AB"					 ; double characters
myList WORD 1, 2, 3, 4, 5  ; array of words
array WORD 5 DUP(?)				 ; uninitialized array
```

2.   Storage definitions for signed and unsigned 32-bit integers:

```assembly
val1 DWORD  12345678h    		 ; unsigned
val2 SDWORD -2147483648  		 ; signed
val3 DWORD  20 DUP(?)  		   ; unsigned array
val4 SDWORD -3, -2, -1, 0, 1 ; signed array
```

### Defining QWORD, TBYTE, Real Data

Storeage definitions for quadwords, ten byte values, and real numbers:

``` assembly
quad1 QWORD  1234567812345678h
val1	TBYTE  1000000000123456789Ah
rVal1 REAL4  -2.1
rVal2 REAL8  3.2E-260
rVal3 REAL10 4.6E+4096
ShortArray REAL4 20 DUP(0.0)
```

### Little Endian Order

1.   All data types larger than a byte store thier individual bytes in reverse order. The least significant byte occurs at the first(lowest) memory address.

2.   Example: 

     ```assembly
     val1 DWORD 12345678h
     ```

     <img src="Photos/Screenshot 2022-11-05 at 9.50.21 PM.png" alt="Screenshot 2022-11-05 at 9.50.21 PM" style="zoom:30%;" />

### Big Endian Order

1.   All data types larger than a byte store their individual bytes in "usual" order. The most significant byte occurs at the first(lowest) memory address.

2.   Example:

     ```assembly
     var1 DWORD 12345678h
     ```

     <img src="Photos/Screenshot 2022-11-05 at 9.50.21 PM.png" alt="Screenshot 2022-11-05 at 9.50.21 PM" style="zoom:30%;" />

### Adding Variables to AddSub

```assembly
; AddSub2.asm
; This program adds and substracts 32-bit unsigned integers
; and stores the sum in a variable.

INCLUDE Irvine32.inc

.data
val1 DWORD 10000h
val2 DWORD 40000h
val3 Dword 20000h
finalVal DWORD ?

.code
main PROC
	mov eax, var1			; start with 10000h
	add eax, val2			; add 40000h
	sub eax, val3			; substract 20000h
	mov vinalVal eax  ; store the result (30000h)
	call DumpRegs			; display the registers
	exit
main ENDP

END main
```

