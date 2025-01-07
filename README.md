Here’s the revised stepwise content with the inclusion of the  sum of 1 to \( n \)  explanation:

---

   RISC-V Talent Development Program 

The program, powered by  Samsung Semiconductor India Research (SSIR)  and  VLSI System Design (VSD) , is focused on developing talent in the RISC-V ecosystem.

 #  Participant Details: 
-  Name:  Lalu Prasad B  
-  Institution:  Sahyadri College of Engineering & Management, Mangaluru  
-  Email:  lalu.ec22@sahyadri.edu.in  
-  GitHub:  [Lalu-Sahyadri-ECE](https://github.com/Lalu-Sahyadri-ECE)  

   Task 1: Development and Compilation of a Parameterized C Program 

 #  1. Setting Up the Virtual Machine: 
I used  VirtualBox  to set up a virtual environment with  Ubuntu 18.04 :
1. Opened VirtualBox and clicked "New" to create a new virtual machine.
2. Selected  Linux  as the operating system and  Ubuntu 18.04  as the version.
3. Allocated memory and selected an existing virtual hard disk (the unzipped VDI file).
4. Launched the virtual machine and verified that it booted successfully.

 #  2. Writing, Compiling, and Running the C Program Locally: 
I wrote a parameterized C program (`sum1ton.c`) to compute the sum of numbers from 1 to \( n \). This program uses a loop for computation and dynamically accepts \( n \) as input from the user during execution.

1.  Sum of Numbers from 1 to \( n \): 
   - The sum of the first \( n \) natural numbers is mathematically calculated as:
     \[
     \text{Sum} = 1 + 2 + 3 + \dots + n = \frac{n \cdot (n + 1)}{2}
     \]
   - However, in the program, the sum is computed iteratively using a loop for practice with programming constructs.

2.  Steps: 
   - Used a text editor (e.g., leafpad) to write the program.
   - Compiled the program locally using the  GCC compiler  (`gcc`).
   - Executed the compiled binary (`./a.out`) and provided various inputs for \( n \) to validate the output.

    Sample Code (sum1ton.c): 
```c
#include <stdio.h>

int main() {
    int n, sum = 0;
    printf("Enter a positive integer: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        sum += i; // Add each number to the sum
    }

    printf("The sum of numbers from 1 to %d is: %d\n", n, sum);
    return 0;
}
```

 3. Cross-Compiling for RISC-V Architecture: 
I cross-compiled the same C program for the  RISC-V architecture :
1. Used the  RISC-V GCC Cross-Compiler  (`riscv64-unknown-elf-gcc`) to compile the program with the following options:
   -  Optimization flags:  `-O1` and `-Ofast` to improve performance.
   -  ABI:  `-mabi=lp64` to specify the Application Binary Interface.
   -  Architecture:  `-march=rv64i` for the 64-bit RISC-V instruction set.
2. Verified the creation of the optimized object file (`sum1ton.o`), ready for execution in a RISC-V simulation or hardware environment.
   Key Insights: 
1. Setting up a virtual development environment provides a controlled platform for development and testing.
2. Understanding the mathematical formula for the sum of numbers from 1 to \( n \) helps in validating the program logic.
3. Writing and compiling a parameterized C program locally ensures correctness before targeting specific hardware.
4. Cross-compilation using architecture-specific tools and optimizations is crucial for efficient code execution on embedded systems like RISC-V.
