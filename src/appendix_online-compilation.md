## Using Compilation Tools in Online Systems

### REPLIT Compilation Tools

Replit is an online integrated development environment (IDE) that gives you access to a small virtual machine that can be accessed with the browser.
It allows you to edit and compile programs using tools such as `clang` and `lld`.
To do so, you must install the tools `clang` and `lld`.
The installation might be different, given that this environment has evolved in recent years.
The tested installation process consisted in the following steps:

- log in the platform
- create a `repl` to C language
- execute the command in the Shell (here version 15 is beiung used, but newer versions should work)
  ```
  sudo apt install clang-15 lld-15
  ```

Replit automatically saves your files (as long as you are logged in), but installed packages are erased when the virtual machine is turned off or restarted. Therefore, CLANG must be installed again (command above) every time the virtual machine is started.

### Compilation toolds in Google Colab

Google Colab is also an online integrated development environment (IDE) that gives access to a small virtual machine that can be accessed with the browser.
It is also possible to use this environment to edit and compile programs with `clang` and `lld`.
The following tutorial shows how to install such tools and compile a small program written in assebly to RISC-V.

Assembling RISC-V programs with Colab: https://colab.research.google.com/drive/1PM-3ulMFqeo4Ce2hIwir3IftcWyQ0SMh?usp=sharing
