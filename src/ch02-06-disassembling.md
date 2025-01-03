## Disassembling object and executable files

Object files (.o) and executable files (.x) are binary files, and common text editors cannot display their contents in a readable form.
To analyze these files, you need special programs called "disassemblers", which interpret the file's contents and convert its representation to text.
You can use the GNU disassembler tool, `objdump`, or the `llvm-objdump` tool to disassemble the binary file and display its information in a textual format.
To do this, simply execute the command:

```
llvm-objdump -D prog.o
```

Compare the output produced by the disassembler (`llvm-objdump`) with the assembly language program file used during the assembly process (`prog.s`).
You'll notice that they are different, but share several common elements (e.g., lists of instructions to be executed by the processor).
