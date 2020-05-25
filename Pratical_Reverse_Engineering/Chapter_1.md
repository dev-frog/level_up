# x86 and x64

 x86 architecture has eight 32bit general purpose register ```EAX, EBX, ECX, EDX, EDI, ESI, EBP, ESP ``` and some of then can be divided into 8-bit and 16-bit registers.


31               15                 0
+-----------------------------------+
|                EAX                |
+-----------------------------------+
                  +-----------------+
                  |         AX      |
                  +-----------------+
                  +--------++-------+
                  |   AH   ||   AL  |
                  +--------++-------+


          Figure 1.1

## Some GPRs abd Their Usage

| register | perpos |

 - ECX (Counter in loops)
 - ESI (Source in string/memory operations)
 - EDI (Destination in string/memory operations)
 - EBP (Base frame pointer)
 - ESP (Stack pointer)

## Register that control low-level system

 - CR 0 (control whether paging is on or off)
 - CR 2 (contains the linear address the cased a page fault)
 - CR 3 (Base address of a paging data structure)
 - CR 4 (Controls the hardware virtualization settings)
 - DR0-DR7 (Used to set memory breakpoint)


## Instruction Set

The x86 instruction set allows a hight level of flexibility in terms of data move-ment between registers and memory.The movement can be classified into five general methods
  - Immediate to register
  - Register to register
  - Immediate to memory
  - Register to memory and vice versa
  - Memory  to memory

First four method supported by all modern architecture,but the last one is specific to x86.Another important characteristic is that x86 uses variable-length instruction size.The instruction lenght can range 1 to 15 bytes.


## Syntax

Depending on the assembler/disassembler,there are tow syntax notations for x86 assembly code,Intel and AT&T


 *Intel*
 ```assembly
        mov ex
 ```
 


