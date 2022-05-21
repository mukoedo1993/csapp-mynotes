## Processors Read and Interpret Instructions ##
At this point, our `hello.c` source program has been translated by the comilation system into an <br>
executable object file called `hello` that is stored on disk. To run the executable file on a Unix system, 
we type its name to an application program known as a shell: 
```
 linux> ./hello
 hello, world
 linux>
```
The shell is a command-line intepreter that prints a prompt, waits for you to type a command line, and then performs the command.
If the first word of a command line doesn't correspond to a built-in shell command, then  the shell assumes that it is the name of
an executable file that it should load and run.

## 1.4.1 Hardward Organization of a System ##
### Buses ###
Running throughout the system is a collection of electrical conduits called *buses* that carry bytes of information back and forth between the
components. Buses are typically designed to transfer fixed-size chunks of bytes known as *words*. The number of bytes in a word (word size) is a
fundamental system parameter that varies across systems. Most machines today have word sizes of either 4 bytes or 8 bytes.

### I/O devices ###
Input/output (I/O) devices are the system's connection to the external world. 
e.g.: user's input: a keyboard and a mouse
user's output: a display and a disk drive(or simply disk) for long-term storage of data and programs.
Each I/O device is connected to the I/O bus by either a *controller* or an *adapter*. The distinction between the two is mainly one 
of packaging. Controllers are chip sets in the device itself or on the system's main printed circuit board(often called the *motherboard*). 
An adpater is a card that plugs into a slot on the motherboard. Regardless, the purpose of each is to transfer information back and forth
between the I/O bus and an I/O device.

### Main Memory ###
The *main memory* is a temporary storage device that holds a program and the data it manipulates while the processor
is executing the porgram. Physically, main memory consists of a collection of *dynamic random access memory* (DRAM) chips.

### Processor ###
The *central processing unit (CPU)*, or simply *processor*, is the engine that interprets (or executes) instructions in main memory.
At its core is a word-size storage device (or register) called the *program counter(PC)*.  At any point of time, the PC points at (contains
the address of) some machine-language instruction in main memory.
From the time that power is applied to the system until the time that the power is shut off, a processor repeatedly executes the instruction pointed
at by the program counter and updates the program counter to point to the next instruction. A processor appears to operates according to a very simple
instruction execution model, defined by its *instruction set architecture*. In this model, instructions execute in strict sequence, and executing a single instruction involves performing a series of steps. The processor reads the instruction from memory pointed at by the program counter(PC), intreprets the bits in the instruction, performs some simple operation dictated by the instruction, and then updates the PC to point to the next instruction, which may or may not be contiguous in memory to the instruction that was just excuted.
There are only a few of these simple operations, and they revolve around main memory, the register file, and the *arithmetic/logic unit*(ALU). The register file is a small storage device that consists of a collection of word-size registers, each with its own unique name. The ALU computes new data
and addresss values. Here are some examples of the simple operations that the CPU might carry out at the request of an instruction:
<ul>
  <li>Load: Copy a byte or a word from main memory into a register, overwriting the previous contents of the register.</li>
  <li>Store: Copy a byte or a word from a register to a location in main memory, overwriting the previous contents of that location.</li>
  <li>Operate: Copy the contents of two registers to the ALU, perform an arithmetic operation on the two words, and store the result in a register, overwriting the previous contents of that register.</li>
  <li>Jump: Extract a word from the instruction itself and copy that word into the program counter (PC), overwriting the previous value of the PC.</li>
 </ul>

## 1.4.2 Running the hello Program
Initially, the shell program is executing its instructions, waiting for us to type a command. As we type the characters `./hello` at the keyboard, the shell program reads each one into a register and then stores it in memory.
When we hit the `enter` key on the keyboard, the shell knows that we have finished typing the command. The shell then loads the executable `hello` file by executing a sequence of instructions that copies the code and data in the `hello` object file from disk to main memory. (Using a technique known as * direct memory access* )

