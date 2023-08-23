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

## Course Log

### Day 1

### Introduction to RISC V

* Instruction Set Architecture(ISA) defines the programming interface between software and hardware. It specifies the instructions that a CPU can understand and execute, along with their formats, addressing modes, and behavior.  
* The RISC-V instruction set architecture (ISA) is a modern and open-source approach to designing processor architectures. It is characterized by its simplicity, modularity, and flexibility. RISC-V follows the Reduced Instruction Set Computing (RISC) philosophy, aiming to minimize the complexity of instructions and emphasize a streamlined execution pipeline. The ISA is designed with a modular structure, allowing for easy customization and extension to cater to various application domains.
** In this course we will be using RISC V ISA and picorv32a.  
![Screenshot from 2023-08-23 17-44-47](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/b8cea55b-7b8c-481a-80ac-5a8014bce29e)  
![Screenshot from 2023-08-23 17-47-52](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/0b8dd410-793a-4d7a-9943-0f6824e9b6a5)  

### Basics  
* Pseudo Instructions (e.g., mv): Pseudo instructions like mv (move) in RISC-V provide code readability; e.g., mv t0, t1 copies the value from register t1 to t0 without a dedicated "copy" instruction.  
* Base Integer Instructions (RV64I): RV64I, RISC-V's base integer instruction set for 64-bit architectures, includes common operations like add, sub, and, or, etc., e.g., add a0, a1, a2 computes the sum of values in registers a1 and a2 and stores it in a0.  
* Multiplication Extension (RV64M): RV64M adds hardware multiplication instructions; e.g., mul rd, rs1, rs2 multiplies values in rs1 and rs2, storing the result in rd.  
* Single and Double Precision Floating Point Extension: Floating-point extension handles real numbers; e.g., fadd.s f1, f2, f3 adds single-precision floating-point values in f2 and f3, storing the result in f1.
* Application Binary Interface (ABI): The ABI defines software-hardware interaction; e.g., parameter passing in RISC-V often uses registers like a0, a1 for function arguments and a7 for system calls.  
* Memory Allocation and Stack Pointer: Stack management is crucial; e.g., the stack pointer (sp) tracks function call frames, and memory allocation functions like malloc allocate dynamic memory, e.g., ptr = malloc(size).  
![Screenshot from 2023-08-23 17-48-59](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/846d5744-1fe5-45f9-bb93-91d1695954c8)  



### Create a simple C program that calculates the sum from 1 to N integers.  
* Open the terminal.
* Open any text editor(eg.leafpad) and create a file sum1ton.c 
![Screenshot from 2023-08-20 16-18-22](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/73bbd99a-e44c-4212-85ca-0bf7236d0c0e)

![Screenshot from 2023-08-20 16-16-59](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/80534baf-66da-4362-b185-fd45d1a9aefa)  

* Open an another terminal
 ![Screenshot from 2023-08-20 22-31-21](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/1ded2b58-db5c-461d-9494-918b401b447e)
![Screenshot from 2023-08-20 16-12-43](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/170f3366-3af7-4532-8c7d-33f8b098f23d)

* Type main
* You can see there are 15 instructions which can be verified using hexadecimal values.
* Quit this terminal.

* Now on the main terminal
  ![Screenshot from 2023-08-20 16-13-18](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/e2d9a269-bcc4-4039-bf78-29f4daa46cbb)
  
![Screenshot from 2023-08-20 16-13-56](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/d0425a08-7c9b-4538-805a-b37407f50743)

* Type main
* Now you can see there are 12 instrcutions because of change of command to -0fast.

### Now to verify on RISCV compiler - SPIKE 
   ![Screenshot from 2023-08-20 16-21-19](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/68abb024-c7b6-4377-b3e5-c73a7eb904af)

* To Debug, open another terminal
![Screenshot from 2023-08-20 22-31-21](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/beaf8ce2-e9de-43fc-9be5-db1fd301b40a)

* Back to main terminal
   ![Screenshot from 2023-08-20 17-29-32](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/eb76f402-6831-444e-8fa6-33455af1b9b6)

* From the provided image, you can observe a clear demonstration of the sequential debugging process, illustrating how to proceed through the code one step at a time.

## Signed and Unsigned Numbers

* Signed numbers:  
Signed numbers include both positive and negative integers, allowing for representation of values in both directions.  
The range of signed numbers depends on the number of bits used for representation. For example, with 8 bits, the range for a signed 8-bit integer is -128 to 127.

* Unsigned numbers:  
Unsigned numbers only represent positive integers, lacking the ability to represent negative values.  
The range of unsigned numbers also depends on the number of bits used. For an unsigned 8-bit integer, the range is 0 to 255, covering a larger positive range compared to signed numbers due to the absence of negative values.
![Screenshot from 2023-08-23 10-40-41](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/77e4b225-2548-41fc-9160-8a5dc9bab2f7)  
![Screenshot from 2023-08-23 10-37-55](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/662e9d31-32a1-4e77-a18c-a0b4062f2321)
![Screenshot from 2023-08-23 10-41-05](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/3ced5be4-09a8-41dd-9e0c-6491b0b55cb4)
![Screenshot from 2023-08-23 10-41-47](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/56056194-d8ef-4961-9bb4-9a61370cadea)
* The answer is same for both the above codes as unsigned long long int datatype max value is same.  
![Screenshot from 2023-08-23 10-42-02](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/975ec542-5e4a-4f2e-8a52-236d31ac9c25)
![Screenshot from 2023-08-23 10-42-35](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/bc58429e-722a-43ff-8663-d529d51c2356)
* For 2^10 - 1 = 1023.
![Screenshot from 2023-08-23 13-46-28](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/5d5e1970-7728-4caf-b247-25fc66a134c2)  
![Screenshot from 2023-08-23 13-46-48](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/40063e96-c596-4e38-bcc7-41829c9b30ed)
* Unsigned long long int datatype the lowest is 0, won't enter negative.
![Screenshot from 2023-08-23 13-50-12](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/a8efc65c-a17f-4635-b113-a67e2c3b7131)
![Screenshot from 2023-08-23 13-49-34](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/0bca4782-abaf-439a-a2e8-9184a257ef22)
* You can now observe negative number is being displayed for the current datatype.
![Screenshot from 2023-08-23 15-30-25](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/bdd47b1e-47a6-450f-9342-8eb520706947)
![Screenshot from 2023-08-23 15-30-51](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/40a754b0-cc28-43af-ac25-c7037e9fcc67)

## DAY 2

### * APPLICATION BINARY INTERFACE(ABI)

An Application Binary Interface (ABI) serves as a crucial bridge between software components at the binary level, defining the conventions and rules for communication between different parts of a computer system. It encompasses a set of protocols, data formats, and calling conventions that enable compatibility and interoperability between compiled code, libraries, and the operating system. ABIs ensure that software written in different languages or by different developers can interact seamlessly, allowing for the execution of programs across diverse hardware architectures and operating systems. It dictates aspects such as parameter passing, memory layout, system call invocation, and exception handling, facilitating the development of robust and portable software solutions.  
 ![Screenshot from 2023-08-23 17-49-50](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/1ac42ad1-9ba8-40d8-b87e-ad7fbf2f9f15)  









