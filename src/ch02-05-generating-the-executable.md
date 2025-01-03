## Generating the Executable from Object Files and Libraries

Once you have produced all the object files for your program, as illustrated in Figure 2.1, you need to combine all these files with libraries into a single executable file.
This process, called linking, is performed by the linker.
There are several tools that link object files with libraries.
The following example shows how we can use the `ld.lld` tool to combine the contents of the `prog.o`, `module1.o`, and `module2.o` files and produce the executable file `prog.x`.

```
ld.lld prog.o module1.o module2.o -o prog.x
```

If your program contains only one source file (e.g., `prog.o`), then simply pass this file to the linker, as illustrated below:

```
ld.lld prog.o -o prog.x
```
