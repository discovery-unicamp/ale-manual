## Automating the Code Generation Process with Makefiles

The software development process involves multiple iterations of bug fixes and recompilations.
However, many of these projects have a large amount of source code files, and compiling all of them is a slow process.
The object files (`.o`) need to be linked again to form the new binary, but only the modified files need to be recompiled.
Therefore, it is important to have an automatic mechanism to recompile only the necessary files.
For this purpose, there is a specific type of script designed to automate software compilation.
The GNU Makefile is a widely used example in the GNU/Linux world.
To install it on a Debian-based distribution, you can run the following command:

```
sudo apt-get install build-essential
```

To create your own script that will instruct GNU Make to build your program, you should create a text file named `Makefile`, which should be in the same directory as the source code, containing rules for creating each file.
For example, you can create rules to specify how the `.s` file (in assembly language) is generated (using the `clang` compiler), how the object files `.o` (object code) are created (using the assembler), and so on.
Here is an example of some rules:

```
ola.s: ola.c
	clang --target=riscv32 -march=rv32g -mabi=ilp32d -mno-relax ola.c -S -o ola.s

ola.o: ola.s
	clang --target=riscv32 -march=rv32g -mabi=ilp32d -mno-relax ola.s -c -o ola.o
```

In this example, there are two rules named `ola.o` and `ola.s`.
The rule name should correspond to the file that is produced by the rule, followed by a colon ":".
For example, the rule that produces the `ola.o` file should be named "ola.o:".
The files required to produce the `ola.o` file should appear in a list (separated by spaces) after the colon ":" (in our case, `ola.s` is required to create `ola.o`).
Then, on the next line, you must use a tab (press the tab key) and type the command that will be executed in the shell to produce that file.
In our example, we call the `clang` compiler to translate a C file into assembly language, and in another rule, we call the assembler to transform an assembly language `.s` file into an object file `.o`.
Note that you can specify the name of another rule as the input file for a rule, and that rule will be invoked first to produce the required input file.
**IMPORTANT**: The script will not work if there is no tab (tab) before the commands "clang ..."!
Do not use spaces!
Additionally, note that some text editors insert spaces instead of tab characters when the tab key is pressed.

You can create multiple rules in the same Makefile.
To run the script, on the command line, type `make rule-name`. For example:

```
make ola.o
```

The `make` program will execute the commands associated with the `ola.o` rule described in the Makefile.
Note that the make program always reads the file named Makefile in the current directory and uses it as a script.
If you do not use this file name (Makefile with a capital "M"), the script will fail.
If you invoke the `make` command without any parameters, it will execute the first rule in the Makefile.

The links below provide more information about Makefiles:

- [Original Manual (English)](http://www.gnu.org/software/make/manual/make.html#Simple-Makefile)
- [Portuguese guide](http://pt.wikibooks.org/wiki/Programar_em_C/Makefiles)
