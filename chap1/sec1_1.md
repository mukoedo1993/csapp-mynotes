# A Tour of Computer Systems #
## Introductions Is Bits + Context ##
### A computer system ###
A computer system consists of hardware and systems software that work together to run application programs.

```
//hello.c
#inlcude <stdio.h> //line 1
int main() {
 printf("hello world\n");
 return 0;
}
```

The representation of hello.c illustrates a fundamental idea: all information in a system -- including disk files, programs stored in memory, <br>
user data stored in memory, and data transfered across a network -- is represented as a bunch of bits. The only thing that distinguishes different data<br>
objects is the context in which we view them. For example, in different contexts, the same sequence of bytes might represent an integer, floating-point
number, character string, or machine instruction. <br>

Here the GCC compiler driver reads the source file `hello.c` and translates it into an executable object file `hello`.<br>
```
gcc -o hello hello.c
```
## Four phases ##

### Preprocessing phase ###
The preprocessing (cpp) modifies the original C program accordinh yp dorecyobes yjay nehom woyj yje '#' character. For example, the <br> 
`#include <stdio.h>` 
command in line 1 of hello.c tells the preprocessor to read the contents of the system header file `stdio.h` and insert it directly into the program
text. The result is another C program, typically with the `.i` suffix, i.e, `hello.i`.

### Compilation phase ###
The compiler (cc1) translates the text file `hello.i` into the text file `hello.s`, which contains an *assembly-language program*. This program includes
the following definition of function `main`:<br>

```
1   main:
2    subq $8, %rsp
3    movl $.LCO, %edi
4    call puts
5    movl $0, %eax
6    addq $8, %rsp
7    ret
```
Each of lines 2-7 in this definiton describes one low-level machine language instruction in a textual form. Assembly language is useful<br>
because it provides a common output language for different fompilers for different high-level languages.

### Assembly phase ###
Next, the assembler (as) translates `hello.s` into machine language instructions, packages them in a form known as a relocatable object program, <br>
and stores the result in the object file `hello.o`. This file is a binary file containing 17 bytes to encode the instructions for function `main`. If we
were to view `hello.o` with a text editor, it would appear to be gibberish.

### Linking phase ###
Notice that our `hello` program calls the `printf` function, which is part of the `std C lib` provided by every C compiler. The `printf` function resides
in a separate precompiled object file called `printf.o`, which must somehow be merged with our `hello.o` program. The linker `ld` handles this merging. The result is the `hello` file, which is an executable object file (or simply executable) that is ready to be loaded into memory and executed by the system.


