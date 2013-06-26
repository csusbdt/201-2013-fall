# What Is a Computer?

## Von Neumann Architecture

A computer is divided into 2 main parts: memory and a central processing unit (CPU).
When the computer runs, the CPU executes machine instructions that are stored in memory.
When an instruction executes, it may read and write data from and to memory.
This approach to computer design is called the Von Neumann Architecture.

## Computer Programs

Computer programs are collections of data and machine instructions 
that are loaded into memory and executed by the CPU. 

## Processes

The running instance of a program in memory is referred to as a process. 
Processes will generally get data from input devices 
-- such as keyboards, mouses and network interfaces -- 
as well as from the executable files from which they were loaded.

## Operating System

When a computer starts up, it loads and runs a program called the operating system. 
The operating system manages the execution of other programs.

## Computer Memory

The smallest piece of information that can be represented in a computer is a bit.
A bit can be in one of 2 states: off (zero) or on (one).

Sequences of bits are used to represent numbers in the binary representation system.
For example, a sequence of 2 bits represent the values 0 through 3 as follows.

| binary | decimal |
|:------:|:-------:|
| 00     | 0       |
| 01     | 1       |
| 10     | 2       |
| 11     | 3       |

Sequences of 4 bits have 16 possible states.
These states can be represented in decimal form (base 10) and in hexadecimal form (base 16) as follows.

| binary | decimal | hexadecimal |
|:------:|:-------:|:-----------:|
| 0000   | 0       | 0           |
| 0001   | 1       | 1           |
| 0010   | 2       | 2           |
| 0011   | 3       | 3           |
| 0100   | 4       | 4           |
| 0101   | 5       | 5           |
| 0110   | 6       | 6           |
| 0111   | 7       | 7           |
| 1000   | 8       | 8           |
| 1001   | 9       | 9           |
| 1010   | 10      | A           |
| 1011   | 11      | B           |
| 1100   | 12      | C           |
| 1101   | 13      | D           |
| 1110   | 14      | E           |
| 1111   | 15      | F           |

Sequences of 8 bits are called bytes. 
Using decimal notation, bytes can take on values in the range [0, 255]. 
Using hexadecimal notation, bytes can take on values in the range [0, FF]. 

|   binary  | decimal | hexadecimal |
|:---------:|:-------:|:-----------:|
| 0000 0000 | 0       | 0           |
| 0000 0001 | 1       | 1           |
| 0000 0010 | 2       | 2           |
| 0000 0011 | 3       | 3           |
| 0000 0100 | 4       | 4           |
| ...       |         |             |	
| 1111 1110 | 254     | FE          |
| 1111 1111 | 255     | FF          |

The maximum value of a byte is 255, but there are a total of 256 possible values.
This fact is an example of the _off-by-one problem_
that appears in many contexts when working with computers.

Computer memory (RAM) is organized as a sequence of bytes.
These bytes are sequentially numbered starting from zero.
For example, if a computer has 4 GB of memory,
then it has 4 GB bytes that are numbered from 0 to 4 GB minus one.

The position of a byte in memory is referred to as an address or location.
In a 32-bit computer, the memory addresses are represented using 4 bytes.
In a 64-bit computer, the memory addresses are represented using 8 bytes.

## Central Processing Unit

The CPU repeats a fetch-execute cycle in which machine instructions
are sequentially read from memory and executed.
On a 32-bit computer, the cycle roughly includes the following steps:

- Read the instruction from RAM that is located at the address stored
  in the program counter and increment the program counter by the byte
  length of an instruction (4 on a 32-bit computer).
- Depending on the instruction, data in memory referenced by the instruction
  is loaded into one or more registers.
- The instruction is executed.
- Depending on the instruction, data in registers may be written into memory.

## Assembly Language

As opposed to a high-level language such as C++,
assembly language is a low-level language
that provides a simple representation of machine instructions.
Unlike C++, programs written in assembly language
are neither portable across different processors nor across different operating systems.
Before high-level languages, the only languages that existed were assembly languages.

The following is an example program written in assembly language.
When the program runs, it writes "hello\n" into the standard output stream.
This program is written specifically for the Linux operating system.

````
# This program writes "hello" to  
# the standard output stream.

.section .data

hello:
.ascii "hello\n"

.section .text
.globl _start        # Tells assembler to generate information for the
                     # operating system to find the first instruction
                     # in the file.

_start:

movl $4, %eax        # Store 4 in register eax. This value is interpreted
                     # by Linux as the write bytes command, which is a
                     # command to copy bytes from main memory (RAM) into
                     # an output stream.

movl $1, %ebx        # Store 1 in register ebx. The write bytes command will
                     # look in register ebx to determine which output stream
                     # to copy the bytes into.  The number 1 means the 
                     # standard output stream.  The standard output stream is
                     # determined at runtime; it is the console window by
                     # default.

movl $hello, %ecx    # When the operating system loads this program into main 
                     # to make it a running process, a numerical representation
                     # of the string "hello" will be placed into memory and the
                     # address of the first character will be placed in
                     # the first argument of this instruction
                     # (which is also stored in main memory).  This numerical
                     # representation includes 5 bytes, one for each character,
                     # followed by a sixth byte that contains zero.
                     #
                     # The write bytes command will look in register ecx to
                     # get the address of the first byte to copy into the
                     # output stream.

movl $6, %edx        # Store 6 in register edx. The write bytes command will
                     # look in edx to determine how many bytes to copy into 
                     # the output stream.

int $0x80            # Pass the hexadecimal number 80 to the operating system
                     # through a software interrupt.  Linux interprets 0x80
                     # as a command to run the command in register eax.

movl $1, %eax        # Store the exit command in register eax.

movl $0, %ebx        # Store the status code in register ebx; this is
                     # expected by the exit command.

int $0x80            # Tell Linux to execute the command in register eax.
````

To transform the above code into an executable program, you need to do 2 things.
First, you need to pass the code into an assembler,
which transforms the code into machine instructions and stores the result in a file
called an object file.
Second, you pass the object file to a linker,
which packages the program into an executable file.

Assuming that the above program is stored in a file named _say_hello.s_,
the following command invokes the assembler to produce an object file called _say_hello.o_.

    as say_hello.s -o say_hello.o

The following command transforms the object file say_hello.o
into an executable file named _say_hello_ (without a file extension).

    ld say_hello.o -o say_hello

At this point, you can run the program with the following command.

    ./say_hello

All programs return a status code.
By convention, a value of 0 means that the program terminated normally;
a value other than 0 means the program terminated due to an error.
These returned values are used by scripts that start programs.
The above program returns 0 when it exits.

