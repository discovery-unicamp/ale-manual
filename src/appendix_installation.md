## Installing Compilation Tools on Your Computer

The examples in this manual use the CLANG compiler.
The compiler is available in the computers at the Institute of Computing labs; however, if you wish to use it on your own computer, you can try the following options:

### Installing on a GNU/Linux Distribution

You can install a Linux distribution on your machine or on a virtual machine using, for example, Oracle VirtualBox.

On Debian-based distributions (e.g., Ubuntu 22.04), type the following commands in the terminal (in this tutorial we install CLANG 15 and LLD 15, but newer versions should work, in case version 15 is no longer available in your distro repository):

```
sudo apt update
sudo apt install clang-15 lld-15
```

The system will ask for your password (or the superuser password of the machine).
Once the process is complete, you will have the environment set up to execute the commands used in the examples in this manual.

### Installing on Windows with WSL2

Starting with Windows 10, Microsoft allows users to install a GNU/Linux environment on Windows.
The following tutorial discusses this process: [Install WSL | Microsoft Learn](https://learn.microsoft.com/en-us/windows/wsl/install#manual-installation-steps).
There are also several tutorials on YouTube (_e.g._: [1](https://www.youtube.com/watch?v=24T7V7e5rGY) e [2](https://www.youtube.com/watch?v=1DcFIVKbOyE)).

After installation, start a terminal from your WSL distribution and type the following commands (for Debian-based distributions):

```
sudo apt update
sudo apt install clang-15 lld-15
```

The system will ask for your password (or the superuser password of the machine).
Once the process is complete, you will have the environment set up to execute the commands used in the examples in this manual.

**Note**: Depending on the version of the Linux distribution being used, the version of clang may not be available in the Package Manager repositories.
This can be resolved by manually adding the repository or by upgrading to a more recent version (e.g., Ubuntu 20.04 => Ubuntu 22.04).
Also, different versions of CLANG can be used, but different behavior may arise. 
