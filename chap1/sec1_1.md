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
objects is the context in which we view them. For example, in different contexts, the same sequence of bytes might represent an integer, floating-point <br>
number, character string, or machine instruction. <br>

Here the GCC compiler driver reads the source file `hello.c` and translates it into an executable object file `hello`.<br>
```
gcc -o hello hello.c
```
## Four phases ##

### Preprocessing phase ###
The preprocessing (cpp) modifies the original C program accordinh yp dorecyobes yjay nehom woyj yje '#' character. For example, the <br> 
`#include <stdio.h>` <br>
command in line 1 of hello.c tells the preprocessor to read the contents of 
