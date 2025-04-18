## Compiling C Code to RISC-V Assembly Language

By default, compilers perform the entire compilation, assembly, and linking process when invoked from the command line.
To interrupt the compilation process after translating C code to assembly language, you must pass a flag to the compiler on the command line.
In the case of `gcc` and `clang`, this flag is `-S`.
The following command illustrates how to translate C code from the file `prog.c` to assembly language and save the result in the `prog.s` file.

```bash
clang -S prog.c -o prog.s
```

To test the above command, you can create a text file called `prog.c` and place the following content:

```c
/* Program that returns the answer to the Ultimate Question of
 * Life, the Universe, and Everything */
int main(void) {
  return 42;
}
```

The command `clang -S prog.c -o prog.s` will produce code for the native machine's assembly language, i.e., for the machine running the compiler.
If you are running the compiler on a computer with an Intel or AMD processor, this means you will produce assembly language code for the x86 architecture family.
Since we are interested in producing code for RISC-V, we need to inform the compiler with special flags.
In the case of `clang`, we will use the flags `--target=riscv32`, `-march=rv32g`, and `-mabi=ilp32d`.
These flags configure the compiler to emit code for 32-bit RISC-V.
The code below illustrates the compilation of the code from the file `prog.c` to RISC-V assembly language:

```
clang --target=riscv32 -march=rv32g -mabi=ilp32d -mno-relax prog.c -S -o prog.s
```

You can check the contents of the `prog.s` file (produced by the above command) by opening it in your favorite text editor.
It is a text file and contains the same program you wrote in C, but transcribed into assembly language for the RISC-V RV32 architecture.
Note that assembly language refers to instructions (add, mv, etc.) and other elements specific to each type of processor and, consequently, is dependent on the processor's interface.

**Note**: In case your system runs on x86 or ARM based processors, if you compare the code produced for the native architecture and the code produced for RISC-V RV32, you will notice that the instructions generated by the compiler are quite different.
