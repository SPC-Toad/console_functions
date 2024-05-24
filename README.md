# Console Functions Project

## Overview

This project implements terminal functions to interact with memory addresses and symbol tables in both SAPC and LINUX environments. The key functionalities include reading and writing to memory addresses, handling segmentation faults, and understanding the memory layout of the program. The project also includes test cases written in TypeScript to validate the terminal functions.

## Files

- **syms**: Symbol table file for SAPC.
- **stubstart.s**: Assembly file for the startup code.
- **slex.h**: Header file for the slex component.
- **slex.c**: Source file for the slex component.
- **discussion.txt**: Discussion on various memory address manipulations and observations.
- **cmds.c**: Source file containing terminal command implementations.
- **makefile**: Build file for compiling the project.
- **tutor.c**: Main source file for the tutor program.
- **typescript**: TypeScript test cases for the terminal functions.

## Compilation

To compile the project, use the provided `makefile`:

```bash
make
```

## Running the Tutor Program

To run the tutor program, execute the following command after compilation:

```bash
./tutor
```

## Discussion Points

1. **Segmentation Fault Handling**:
    - Calling `md` for an address that does not correspond to a physical memory address results in a segmentation fault.
    - Writing to an address that is part of your tutor code or symbol table returns the value at that address.

2. **Symbol Table Analysis**:
    - The symbol table (`nm` output) is used to locate global variables and pointers.
    - Addresses of specific variables and pointers can be determined and verified using the tutor program.

3. **Memory Address Manipulations**:
    - Change the `stop` command from 's' to 'x' while the tutor program is running using the `ms` command.
    - Change the tutor prompt similarly.

4. **Code and Data Memory Locations**:
    - Code symbols (`T`) reside in specific address ranges.
    - Data (variables) reside in other specific address ranges.

5. **Program Stack Observations**:
    - The program stack can be observed using the stack pointer (`%esp`).
    - The `i reg` command in gdb and `rd` command in Tutor can be used to inspect the stack pointer.

6. **Crashing the Tutor Program**:
    - Random changes to the code can cause the tutor to crash, resulting in segmentation faults or page faults.
