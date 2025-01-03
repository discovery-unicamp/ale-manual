# RISC-V ALE Manual

This repository contains the Markdown files and images used to build the `ALE Manual` used in the `MC404 - Computer Organization and Assembly Language` course at Universidade Estadual de Campinas (UNICAMP).

The manual contains a set of tutorials that present the RISC-V ALE Simulator capabilities and how to properly use them.

The built book is available at https://riscv-programming.org/ale-manual.html

## Building the book

In order to generate the HTML files for the book Rust's [mdBook] is used.
You can install it from its [GitHub repository](https://github.com/rust-lang/mdBook).

At the root of this repository run

```bash
$ mdbook build
```

The resulting HTML files can be found in the `book` subdirectory.

### Authors

For further reference, below the authors list:

* João Seródio (@SerodioJ)
* Edson Borin (@eborin)
