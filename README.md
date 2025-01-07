# Assembly Program: Product Sequence Calculator

## Description

This repository contains a 32-bit Intel syntax assembly program that calculates a specific product sequence based on a user-provided positive integer `n`.

**Formula:**

The program computes the following product:

```
Product = (n + 1/1) × (n - 1 + 1/2) × (n - 2 + 1/3) × ... × (1 + 1/n)
```

**Example:**

For `n = 3`:

```
Product = (3 + 1/1) × (2 + 1/2) × (1 + 1/3)
        = (3 + 1) × (2 + 0.5) × (1 + 0.333...)
        = 4 × 2.5 × 1.333...
        ≈ 13.333
```

## Getting Started

### Prerequisites

- **Assembler:** `nasm` or any assembler that supports Intel syntax assembly.
- **Linker:** `ld` or a compatible linker to create the executable.
- **Operating System:** Linux or any OS capable of running 32-bit executables.

### Building the Program

1. **Assemble the code:**

   ```bash
   nasm -f elf32 -o program.o program.asm
   ```

2. **Link the object file:**

   ```bash
   ld -m elf_i386 -o program program.o
   ```

### Running the Program

Execute the compiled program:

```bash
./program
```

## Usage

- **Input:** When prompted, enter a positive integer `n`.
- **Output:** The program will display the calculated product based on the formula.

### Sample Run

```bash
$ ./program
Please, input a number: 3
The program output: 13.333333
```

## Program Details

The assembly code performs the following steps:

1. **Prompt for Input:** Asks the user to input a positive integer `n`.
2. **Input Validation:** Checks if `n` is positive. If not, it displays a warning message.
3. **Calculation Loop:**
   - Iteratively calculates each term `(n - i + 1 / (i + 1))` where `i` ranges from `0` to `n - 1`.
   - Multiplies all terms together to compute the final product.
4. **Display Output:** Prints the calculated product to the console.

## Notes

- **Negative Input Handling:** If a negative number or zero is entered, the program will display:

  ```
  Can't calculate a negative number...
  ```

- **Precision:** The program uses double-precision floating-point arithmetic for accurate calculations.

## Compatibility

- Designed for 32-bit environments.
- May require compatibility settings or multilib support on 64-bit systems.

