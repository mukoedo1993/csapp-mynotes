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
Input
