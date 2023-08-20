# Physical VLSI Design for ASIC
(Guided by Kunsal Ghosh)

## Objective

The VLSI Physical Design for ASIC (Application-Specific Integrated Circuit) using RISC-V aims to provide participants with a comprehensive understanding of the physical design process for integrated circuits, specifically focusing on ASICs implemented with the RISC-V architecture. 

## Installation

git clone https://github.com/kunalg123/riscv_workshop_collaterals  
cd riscv_workshop_collaterals  
chmod 755 run.sh  
./run.sh  
For the bin file of gcc ubuntu riscv64 in the riscv_toolchain file enter into root privileges and export PATH. 
Restart the terminal.

## Course

### Day 1

### Introduction to RISC V

* Instruction Set Architecture(ISA) defines the programming interface between software and hardware. It specifies the instructions that a CPU can understand and execute, along with their formats, addressing modes, and behavior.  
* The RISC-V instruction set architecture (ISA) is a modern and open-source approach to designing processor architectures. It is characterized by its simplicity, modularity, and flexibility. RISC-V follows the Reduced Instruction Set Computing (RISC) philosophy, aiming to minimize the complexity of instructions and emphasize a streamlined execution pipeline. The ISA is designed with a modular structure, allowing for easy customization and extension to cater to various application domains.
** In this course we will be using RISC V ISA and picorv32a.


### Basics  
* Pseudo Instructions (e.g., mv): Pseudo instructions like mv (move) in RISC-V provide code readability; e.g., mv t0, t1 copies the value from register t1 to t0 without a dedicated "copy" instruction.  
* Base Integer Instructions (RV64I): RV64I, RISC-V's base integer instruction set for 64-bit architectures, includes common operations like add, sub, and, or, etc., e.g., add a0, a1, a2 computes the sum of values in registers a1 and a2 and stores it in a0.  
* Multiplication Extension (RV64M): RV64M adds hardware multiplication instructions; e.g., mul rd, rs1, rs2 multiplies values in rs1 and rs2, storing the result in rd.  
* Single and Double Precision Floating Point Extension: Floating-point extension handles real numbers; e.g., fadd.s f1, f2, f3 adds single-precision floating-point values in f2 and f3, storing the result in f1.
* Application Binary Interface (ABI): The ABI defines software-hardware interaction; e.g., parameter passing in RISC-V often uses registers like a0, a1 for function arguments and a7 for system calls.  
* Memory Allocation and Stack Pointer: Stack management is crucial; e.g., the stack pointer (sp) tracks function call frames, and memory allocation functions like malloc allocate dynamic memory, e.g., ptr = malloc(size).  

### 1. Create a simple C program that calculates the sum from 1 to N integers.  
* Open the terminal.
* Open any text editor(eg.leafpad) and create a file sum1ton.c 
![Screenshot from 2023-08-20 16-18-22](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/b8b9d236-6cff-4674-99ed-1574a3a358b1)  
![Screenshot from 2023-08-20 16-16-16](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/1e03ac92-d965-4ea1-998d-2e1854b3713b)  
![Screenshot from 2023-08-20 16-16-59](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/75ef4f0b-9152-4b34-8e68-f6c64e300a67)  
* Open an another terminal
![Screenshot from 2023-08-20 22-31-21](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/5d056956-c19d-4e96-9e36-9fef38ef60fb)  
* Type main
* You can see there are 15 instructions which can be verified using hexadecimal values.
* Quit this terminal.

* Now on a new terminal
![Screenshot from 2023-08-20 16-13-18](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/64be52ef-731a-434e-9c03-0aa98bd1878b)  
![Screenshot from 2023-08-20 22-31-21](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/39c1b559-a03a-49da-bfae-b692228417d6)  
* Type main
* Now you can see there are 12 instrcutions because of change of command to -0fast.

* Now to verify on RISCV compiler
  ![Screenshot from 2023-08-20 16-21-19](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/8e9d3334-7030-4749-a193-f4fbe5421678)  
* To Debug, open another terminal
![Screenshot from 2023-08-20 22-31-21](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/7e29b270-e2d9-4172-a0a5-eaf7a7dd101f)  
* Back to main terminal
  ![Screenshot from 2023-08-20 17-29-32](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/e14d2bf9-4e95-431e-b9e5-5da654346bf9)  
* From the provided image, you can observe a clear demonstration of the sequential debugging process, illustrating how to proceed through the code one step at a time.

