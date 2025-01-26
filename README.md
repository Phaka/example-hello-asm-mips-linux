# Hello World in MIPS Assembly (Linux)

A simple Hello World implementation in 32-bit MIPS assembly language for Linux systems. MIPS32 represents the 32-bit version of the MIPS architecture, which has been widely used in embedded systems and early gaming consoles.

## Installation

On a MIPS Linux system, you'll need the standard GNU toolchain:

```bash
sudo apt-get update
sudo apt-get install binutils gcc
```

## Running

Assemble and link:
```bash
as -o main.o main.s
ld -o hello main.o
./hello
```

## Code Explanation

The MIPS32 implementation demonstrates several important differences from its 64-bit counterpart. The most notable changes are in the system call numbers and the use of 32-bit instructions instead of their 64-bit equivalents.

Key differences from MIPS64:
- System call numbers are different (4004 for write, 4001 for exit)
- Uses 32-bit instructions (li, la) instead of 64-bit versions (dli, dla)
- Register width is 32 bits instead of 64 bits
- Memory alignment requirements are different (.align 2 instead of 3)

The program uses MIPS register conventions:
- $v0: System call number
- $a0-$a2: Function arguments and system call parameters
- All registers in MIPS32 are 32 bits wide

Instructions used:
- li (Load Immediate): Loads a 32-bit immediate value into a register
- la (Load Address): Loads a 32-bit address into a register
- syscall: Makes a system call

The implementation demonstrates several MIPS architectural features:
- Fixed 32-bit instruction size
- Load-store architecture
- Branch delay slots (though not used in this simple example)
- Register-based procedure calling convention

The .align directives ensure proper alignment for both code and data, which is important for performance on MIPS processors.
