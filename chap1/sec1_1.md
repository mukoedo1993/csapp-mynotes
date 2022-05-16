The representation of hello.c illustrates a fundamental idea: all information in a system -- including disk files, programs stored in memory, <br>
user data stored in memory, and data transfered across a network -- is represented as a bunch of bits. The only thing that distinguishes different data<br>
objects is the context in which we view them. For example, in different contexts, the same sequence of bytes might represent an integer, floating-point <br>
number, character string, or machine instruction. <br>
```
//hello.c
#inlcude <stdio.h>
int main() {
 printf("hello world\n");
 return 0;
}
```

```
gcc -o hello hello.c
```
# Preprocessing phase #
The preprocessing (cpp) modifies the original C program accordinh yp dorecyobes yjay nehom woyj yje '#' character. For example, the '#include <stdio.h>' <br>
command in line 1 of hello.c tells the preprocessor to read the contents of 
