## Assembling Programs in Assembly Language

The assembler converts the program in assembly language to machine language and stores it in an object file (`.o`).
To directly invoke the GNU assembler, you can use the as command, as illustrated below.

**Note**: By default, the `as` program assembles programs in assembly language for the native architecture.
Therefore, if you are running the as tool on a machine that does not have a RISC-V processor, it will generate an error if you try to assemble a RISC-V assembly program.

```
as prog.s -o prog.o
```

In this case, the assembler will store the result in the `prog.o` file.
Instead of directly calling the `as` command, you can use the compiler driver itself (`gcc` for GCC and `clang` for CLANG) to invoke the assembler.
To do this, simply use the command that invokes the compiler driver and pass the assembly language file as a parameter.
For example, with `clang`, you can execute:

```
clang --target=riscv32 -march=rv32g -mabi=ilp32d -mno-relax prog.s -c -o prog.o
```

In this example, we use the `-c` flag to instruct the compiler driver to stop the process after generating the object file.
If we didn't do this, the compiler driver would attempt to call the linker to generate the final executable.

You should not open the produced file (`prog.o`) in your text editor, as it is a binary file.
To analyze this file, you need special programs called "disassemblers" that interpret the file's content and convert its representation to human readable text.
These tools will be discussed in Chapter 2.6.
