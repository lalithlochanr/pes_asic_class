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

<details>
<summary>Introduction to RISC V & LAB</summary>

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

</details>

## DAY 2

<details>
 <summary>ABI,MEMMORY ALLOCATION & BASIC INSTRUCTIONS</summary>
### APPLICATION BINARY INTERFACE(ABI)

An Application Binary Interface (ABI) serves as a crucial bridge between software components at the binary level, defining the conventions and rules for communication between different parts of a computer system. It encompasses a set of protocols, data formats, and calling conventions that enable compatibility and interoperability between compiled code, libraries, and the operating system. ABIs ensure that software written in different languages or by different developers can interact seamlessly, allowing for the execution of programs across diverse hardware architectures and operating systems. It dictates aspects such as parameter passing, memory layout, system call invocation, and exception handling, facilitating the development of robust and portable software solutions.  
 ![Screenshot from 2023-08-23 17-49-50](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/1ac42ad1-9ba8-40d8-b87e-ad7fbf2f9f15)  

 ### MEMORY ALLOCATION

Memory allocation in registers is a fundamental concept in computer architecture where data is temporarily stored in processor registers for faster access than main memory. This technique enhances program performance by reducing memory latency.  
In RISC-V architecture, double word memory allocation in register refers to storing 64 bits (8 bytes) of data in a single register. This allows for efficient handling of larger data types and operations within the processor, promoting streamlined and optimized computation.  
![Screenshot from 2023-08-23 17-54-50](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/4e8162b5-fac0-4bf1-82ac-3109a9753847)  

### BASIC INSTRUCTIONS

* LOAD (LW):  
Purpose: Used to load data from memory into a register.  
Syntax: LW rd, offset(rs1)  
Functionality: Reads a 32-bit word from memory at the address (rs1 + offset) and stores it in register rd.  
* STORE (SW):  
Purpose: Used to store data from a register into memory.  
Syntax: SW rs2, offset(rs1)  
Functionality: Writes the value from register rs2 into memory at the address (rs1 + offset).  

* ADD (ADD):  
Purpose: Used to perform integer addition between registers.  
Syntax: ADD rd, rs1, rs2  
Functionality: Adds the values of registers rs1 and rs2, then stores the result in register rd.  

* SUBTRACT (SUB):
Purpose: Used to perform integer subtraction between registers.  
Syntax: SUB rd, rs1, rs2  
Functionality: Subtracts the value in register rs2 from the value in register rs1, then stores the result in register rd.

etc.  

Folders under riscv_workshop_collaterals and its content
![Screenshot from 2023-08-23 14-53-03](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/c311dad2-0a77-4037-acb7-c3a864f8bf1f)  
![Screenshot from 2023-08-23 14-53-27](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/908659d7-2f3e-4188-9731-b5cff5d3a9b5)  

* C code of summing numbers 1 to N with reveiwing assembly language.  
![Screenshot from 2023-08-23 14-32-38](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/d5fe0c3f-620e-41dc-9b65-d33995edb924)  
![Screenshot from 2023-08-23 14-32-23](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/8fd1e745-fd6e-49ec-a3d8-daefbfbf5a7b)  
![Screenshot from 2023-08-23 14-37-46](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/1af1a024-6548-4ea2-bf88-d1725e58e5e3)  
![Screenshot from 2023-08-23 14-38-50](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/7949bae5-e933-4172-aa65-7a48868a0751)

</details>

## RTL DESIGN using Verilog with SKY130 Technology  

## DAY 3


### Introduction to iverilog design (open source simulator) test bench  

<details>
 <summary> Introduction </summary>

* Simulator  
A simulator is a computer program or tool used to replicate real-world processes, systems, or environments for the purpose of analysis, training, or experimentation. It allows users to interact with a virtual representation of a system or scenario, providing insights into how it behaves without the need for real-world implementation. Simulators are widely used across various fields, including engineering, aviation, healthcare, and gaming, to study and understand complex systems in a controlled and safe manner.    
Simulators work by emulating the underlying dynamics and behaviors of a target system. They use mathematical models, algorithms, and input data to create a simulated environment that responds to user inputs or predefined conditions. As users interact with the simulator, it processes these inputs and computes the corresponding outputs based on the underlying model. This allows users to observe and analyze the system's behavior, responses, and outcomes, enabling experimentation and learning without the risks associated with manipulating real systems directly.    

* Design  
Structured description of circuits using a hardware description language like Verilog which has intended functionality to meet with required specifications. It outlines how registers and logic elements are interconnected and operate, forming the blueprint for the eventual hardware implementation.
![Screenshot from 2023-08-29 08-22-09](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/0e7aa501-a0ab-426f-a316-4b49339dd1bd)  

* Simulation  
A testbench is a set of simulation code written to verify the functionality and performance of a digital design described in RTL (Register Transfer Level) by generating stimulus, applying inputs, and comparing outputs to expected results. It aids in identifying design flaws and ensuring the design's correctness before hardware fabrication.
iverilog based simulation flow 
![Screenshot from 2023-08-29 08-22-32](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/32deb679-3003-4d40-8a57-4837497d1949)
- a vcd(value change dump) is obtained as output of the simulator
- gtkwave tool - lets you view the waveform
</details>

<details>
 <summary> Labs using iverilog and gtkwave </summary>  

 - make a directory using command mkdir vsd
 - then cd vsd

 * git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git 
![Screenshot from 2023-09-03 18-52-01](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/c8660419-7260-4096-93f6-7df8295ead8b)  

* All library files are stored in my_lib  
-verilog_model : contains standard cell verilog modules in the .lib file   
-verilog_files : contains verilog source files and testbench files

* cd sky130RTLDesignAndSynthesisWorkshop  
* cd verilog_files  
![Screenshot from 2023-09-03 18-58-44](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/9e776502-a51e-4efa-b3b5-09bae149fdfc)
![Screenshot from 2023-09-03 19-00-44](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/8a2b7d24-0bb4-436e-8a28-1b4362022fb7)  



* Verilog and testbench file  
 ![Screenshot from 2023-09-03 19-05-16](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/228e3a53-f63d-459c-9a5c-30d95622ff06)

- Open gtkwave to view waveform  
![Screenshot from 2023-09-03 19-05-26](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/65228ea8-64f9-488b-bb35-600390348b61)

* The waveform of mux is obtained  
  - after going to uut under tb_good_mux  
  - drag and drop the inputs and outputs  
  - verify the output from inputs for a 2:1 mux by navigating through the waveform
![Screenshot from 2023-08-29 09-22-00](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/725085fe-9ed8-46a2-9f8e-a6cd3ee7ccbb)  

* Two files of good_mux.v and its testbench  
![Screenshot from 2023-08-29 09-30-12](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/b8f18e2f-2400-4523-977b-e38989ca7ed0)  
![Screenshot from 2023-08-29 09-29-32](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/d42b41f9-aac8-45ce-9f91-4c0f9cfe5eec)

</details>

<details> 
 <summary> Yosys and Logic Synthesis </summary>  
 
* Synthesizer
  - tool used for converting RTL to netlist  
  - Yosys is synthesizer used here  
 ![Screenshot from 2023-08-29 09-35-18](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/0b8c9d26-6fe1-4377-bdc9-91a0ea40d6c6)
- Verifying the synthesis is by gtkwaveform from vcd file of iverilog from netlist and testbench
![Screenshot from 2023-08-29 09-38-09](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/d855904e-8594-4de6-9340-acf7a0b0deff)  

** Logic Synthesis
* RTL Design
-behavioural representation of required specification

- Synthesis is RTL to gate level translation with connections made between gates and the file given out is called netlist.
  ![Screenshot from 2023-08-29 09-42-47](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/e0676dbf-0eb2-4933-a22c-61863263fdd3)

- The .lib file holds collection all logical modules including basic gates with different flavors of same gate slow,medium and fast.

![Screenshot from 2023-08-29 09-43-21](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/de4851b3-bb12-4f28-ab22-2845bd61d0a2)  
- fclk(max) =1/Tclk(min)

* Why do we need slow cells?
![Screenshot from 2023-08-29 09-48-12](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/c3a27b41-5083-4317-8cdc-1c835171fd34)

* Faster Cells vs Slower Cells  
Faster the charging / discharging of capacitance - Lesser the cell delay  
- To charge / discharge the capacitance fast, we need transistors capable of sourcing more current  
- Wider transistors -> Low Delay -> More Area and Power as well   
- Narrow transistors -> More Delay -> Less Area and Power  
- Faster cells donot come free, they come at penalty of area and power

** With the help of constraints we need to guide the synthesiser to the optimum choosing of flavor of cells for efficient working  

* More use of faster cells
  -leads to bad circuit in terms of power and area and also hold time violations
* More use of slower cells
  -leads to sluggish circuits amd may not meet the performance needs.

![Screenshot from 2023-08-29 10-04-42](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/48a6a174-a620-4ca3-8009-26f993561829)  

* Open yosys on terminal  

</details>

<details>
 <summary> Labs using Yosys and Sky130 PDKs </summary>  

 * Yosys Installation

git clone https://github.com/YosysHQ/yosys.git  
cd yosys  
sudo apt install make  
sudo apt-get update  
sudo apt-get install build-essential clang bison flex  libreadline-dev gawk tcl-dev libffi-dev git  graphviz xdot pkg-config python3 libboost-system-dev libboost-python-dev libboost-filesystem-dev zlib1g-dev  
make config-gcc  
make  
sudo make install  

 * Read Commands used in Yosys
 
 1. `read liberty`: In Yosys, the "read liberty" command is used to import Liberty Standard Cell Library files, which contain information about the logical and timing characteristics of standard cells in digital designs.  

2. `read verilog`: The "read verilog" command allows users to read Verilog hardware description language files, enabling Yosys to analyze and synthesize digital designs specified in Verilog.  

3. `read_ilang`: This command reads the ILANG (Intermediate Language for FPGA) format, which is a Yosys-specific intermediate representation of a digital design.  

4. `read_blif`: "read_blif" is used to import designs in the Berkeley Logic Interchange Format (BLIF), a common format for representing digital logic circuits.  

5. `read_json`: Yosys can read JSON files that contain digital design information, allowing for the import and manipulation of designs in this structured data format.  

6. `read_hdl`: This command is used for reading custom hardware description languages (HDLs) supported by Yosys, extending its compatibility with various HDLs beyond Verilog and VHDL.  

7. `read_aiger`: Yosys can read AIGER format files, which represent And-Inverter Graphs (AIGs) and are often used in formal verification and synthesis tasks.  

8. `read_fsm`: For finite state machine (FSM) synthesis, the "read_fsm" command allows Yosys to interpret and work with FSM specifications in a specific format.    

9. `read_smtlib`: Yosys can read SMT-LIB format files, which are commonly used for formal verification and symbolic model checking of digital designs.    

10. `read_xdc`: When working with Xilinx FPGAs, the "read_xdc" command is used to read Xilinx Design Constraints (XDC) files, which define placement and routing constraints for the design.

* Open Yosys at the verilog_files path
* read library using command: read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
* read design using command: read_verilog good_mux.v

![Screenshot from 2023-09-03 19-16-22](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/2413d7da-388d-430e-b4d3-4c83828f4a4a)  

* Use synth -top good_mux to synthesize good_mux module
![Screenshot from 2023-09-03 19-24-30](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/a5f55e3d-3ced-448b-ad94-b682f28e8056)  
![Screenshot from 2023-09-03 19-21-39](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/d4203c0d-471f-4752-ae6d-1529923052eb)  

* realize the logic in library using command:  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
![Screenshot from 2023-09-03 19-23-27](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/0243d0aa-0f5f-4666-b858-069350a2c3e0)  
![Screenshot from 2023-09-03 19-27-41](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/a893727a-ffed-4e05-b028-365c5d86682b)

* to show the logic that is realized tht command used is: show
![Screenshot from 2023-09-03 19-29-31](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/d3b76302-06ca-47d3-a3f4-6235229a2d50)  
![Screenshot from 2023-09-03 19-29-56](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/8fbca4e9-9e67-4a04-baaa-e87ed73f757e)  

* Explanation of realization of two input mux
![Screenshot from 2023-09-03 19-40-47](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/71414591-cdf4-4069-8f98-c4cd72da91db)

* write netlist using command: write_verilog good_mux_netlist.v
* then open command using: !vim good_mux_netlist.v
![Screenshot from 2023-09-03 19-45-28](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/44a086ba-c8e8-4560-a9e1-93840889e34a)  
![Screenshot from 2023-09-03 19-45-34](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/84a6a5a7-cbf5-4f98-9947-e02417ee08df)  
![Screenshot from 2023-09-03 19-44-55](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/7d9f897e-5919-44bc-a043-3a84f03660b7)  

** To view simplified netlist  
* write netlist using command: write_verilog -noattr good_mux_netlist.v  
* then open command using: !vim good_mux_netlist.v  
![Screenshot from 2023-09-03 19-51-00](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/9334dce3-df54-45ea-844b-4c97ddc5c229)  
![Screenshot from 2023-09-03 19-50-22](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/ac278f1e-508f-4e5c-b108-5abd94a3ba6d)  

</details>

### Day 4
### Timing libs,heirarchial v/s flat synthgesis and efficient flop coding styles

<details>
 <summary> Introduction to timing.libs </summary>    
* Introduction to Dot lib  
 - To view the contents in the .lib file use command: vim ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
 ![Screenshot from 2023-09-03 20-01-25](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/2214cc47-613f-4cf6-83b9-f9a9a2cdf1a2)
 -Additional information required can be obtained in the file as shown above like CMOS,different flavors of cell,area(area inversely proportional to delay and directionly proportional to power), etc.  
** Here the line "library ("sky130_fd_sc_hd__tt_025C_1v80")"  gives you the name of library and from it we can infer some information.   
 - Important parameters for variation (eg. machine variation, voltage variation, etc)  
 * P - Process - Variations due to fabrication    
 * V - Voltage  
 * T - Temperature  
 so we need to factorize all these variations for effficient working.  
tt- typical process(type)  
025C- indicates temperature  
1v8- indicates voltage  
 
</details>

<details>
 <summary> Heirarchial v/s Flat Synthesis </summary>
 
 ### Heirarchial Synthesis
 
 * gvim multiple_modules.v
 
 ![Screenshot from 2023-09-03 20-34-44](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/b6bc7bca-dba2-445d-ae4e-37c293615186)  

 * Launch yosys    
 * read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
 * read_verilog multiple_modules.v    
 * synth -top multiple_modules  
   ![Screenshot from 2023-09-03 20-42-56](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/5446a193-e027-4754-a8d6-0eaeb536c065)  
   ![Screenshot from 2023-09-03 20-44-08](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/404e59c2-7807-4f80-8ed5-9e7cc07641fe)

 * abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
   ![Screenshot from 2023-09-03 20-45-00](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/0bab2ccf-3986-45ce-93cc-0e99f4b88cb9)

 * show multiple_modules  
   ![Screenshot from 2023-09-03 20-45-45](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/35d1f989-6c5a-4e46-b85a-6ecc3fe2f5c8)

![Screenshot from 2023-09-03 20-46-21](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/ef0f7622-e6ca-4a32-91c4-eb2b1e346877)

* The Heirarchial result of netlist   
*  write_verilog -noattr multiple_modules_hier.v  
*  !gvim multiple_modules_hier.v
*  So here we can the heirarchy preserved with respect to sub modules.
![Screenshot from 2023-09-03 20-49-03](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/69ff405b-2cf3-41e5-a417-99c066dd7bef)
-(Stacked NMOS is GOOD)
-(Stacked PMOS is BAD)

### Flattened Synthesis
* yosys
* read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
* read_verilog multiple_modules.v
* synth -top multiple_modules
* abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
* flatten
* show
![Screenshot from 2023-09-03 21-03-38](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/f275c7b2-3f1e-43fb-bbbc-df4c3f8555da)

* write_verilog -noattr multiple_modules_flat.v
* !gvim multiple_modules_flat.v
** The submodules are not preserved as in heirarchy in Flattened synthesis.
  ![Screenshot from 2023-09-03 21-06-11](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/195ef32e-acce-4ab4-85f2-85b5790a63f5)

So the key difference is that hierarchy synthesis maintains the hierarchical structure of the design, while flattened synthesis removes all hierarchy, treating the entire design as a single-level entity.  

** Why sub-modules of top module??
- Used for divide and conquer also when multiple instances of same module is present.

</details>

<details>
 <summary> Various Flop Coding Styles and Optimization </summary>
 
 ### Why Flop and Flop coding style
 
 * Glitch
   - A glitch is a temporary and unintended pulse or fluctuation in the output of a digital logic circuit that occurs due to transient changes in input signals.  
   - Glitches can happen when signals in a combinatorial logic circuit propagate at different speeds, causing momentary incorrect outputs before settling to the correct logic level.  
   - Proper design techniques, like adding hazard detection and correction logic or using synchronous design practices, can help minimize or eliminate glitches.
  
   * Flip-Flop
   -A flip-flop is a fundamental digital electronic circuit element used to store and control binary information (0 or 1). It is a bistable multivibrator, meaning it has two stable states and can be used to store a single binary bit of data and is also a flip flop is edge triggered.  
   - Flip-Flops are essential components in digital circuits that help mitigate glitches by providing latching behavior, synchronizing data, and enabling glitch-avoidance techniques in the design. Their role in controlling the timing and stability of signals is critical for reliable circuit operation.  

1. Latching Behavior: Flip-flops are designed to capture and hold a digital value until a clock edge. This latching behavior helps prevent glitches from propagating through the circuit. When an input signal experiences a glitch, the flip-flop typically filters it out and ensures only stable values are passed to subsequent stages.  

2. Synchronization: Flip-flops play a key role in synchronizing data in sequential circuits. Data is sampled and synchronized with the clock signal, minimizing the chances of glitches causing incorrect data transitions between different parts of the circuit.  

3. Glitch Avoidance: Flip-flops are often used to eliminate glitches intentionally. By properly designing the combinational logic feeding into a flip-flop, it's possible to avoid generating glitches in the first place. This is achieved by ensuring that inputs to the flip-flop switch only during a specific clock phase, reducing the likelihood of glitches.

    #### D FLIP FLOP

#### D Flip Flop with Asynchronous Reset

- Data Storage: It stores a single binary bit (0 or 1) of data.  

-Asynchronous Reset: It has an additional input called "RESET" or "CLR" (clear), which when asserted (typically set to logic 0), immediately forces the output Q to 0, irrespective of the clock or data input.  

- Clock-Controlled: Like other flip-flops, it's edge-triggered and changes its output state (Q) on the rising or falling edge of a clock signal.  

- Memory Element: It's commonly used in digital systems to create memory elements that can be cleared asynchronously to a specific state (usually 0) for initialization or error recovery purposes.  

- Synchronization: The D flip-flop with asynchronous reset helps synchronize and control the timing of data transitions in sequential logic circuits, ensuring proper behavior during both normal operation and exceptional conditions.  

* gvim dff_asyncres.v
![Screenshot from 2023-09-03 21-37-01](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/1bb9dbc7-0e80-4129-bda3-b4c1ce4b9bba)

* Simulation(Outside of yosys)
  ````
  cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
  iverilog dff_asyncres.v tb_dff_asyncres.v
  ./a.out
  gtkwave tb_dff_asyncres.vcd
  ````

![Screenshot from 2023-09-03 22-10-05](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/4084290c-faac-49ab-a993-a0882c264039)

![Screenshot from 2023-09-03 22-04-15](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/18115d55-c7fa-4d14-b603-9c885ad0a8b6) 

* Synthesis
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog dff_asyncres.v

synth -top dff_asyncres

dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show
````
![Screenshot from 2023-09-03 23-08-12](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/ffaa5031-50a1-4743-b962-8022c57131d5)


  

#### D Flip Flop with Synchronous Reset
* Data Storage: It can store a single binary bit (0 or 1) of data.  

* Synchronous Reset: It includes a reset input (often labeled "RST" or "CLR") that, when asserted, synchronously forces the output Q to a known state (usually logic-low, 0) on the clock edge. Unlike asynchronous reset, this reset operation occurs in coordination with the clock signal.  

* Clock-Controlled: Similar to other flip-flops, it operates on the rising or falling edge of a clock signal. The output state (Q) changes only when the clock edge occurs.  

* Memory Element: D flip-flops with synchronous reset are widely used in digital systems to create memory elements that can be cleared synchronously to a known state as part of the clocked logic operation. This ensures predictable behavior during system initialization or reset conditions.  

* Synchronization: The synchronous reset feature ensures that the reset operation is synchronized with the clock signal, making it suitable for controlling the state of flip-flops and data paths in sequential logic circuits, ensuring consistent and reliable operation.

* gvim dff_syncres.v
![Screenshot from 2023-09-03 21-49-43](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/e86541ed-6199-4d12-b996-46b8dd8a30b6)

* Simulation(outside of yosys)
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
iverilog dff_syncres.v tb_dff_syncres.v
./a.out
gtkwave tb_dff_syncres.vcd
```` 
![Screenshot from 2023-09-03 22-12-29](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/98c1ca99-ae0f-4d35-90b5-a529d31b074d)  
![Screenshot from 2023-09-03 22-12-16](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/78722d28-fbfd-4323-b618-f71a3e46796d)  

* Synthesis
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog dff_syncres.v
synth -top dff_syncres
dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
````
![Screenshot from 2023-09-03 23-10-28](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/73aca21b-f654-4c5c-a32a-b4863de5fc84)



#### D Flip Flop with Asynchronous Set  

* Data Storage: It stores a single binary bit (0 or 1) of data.  

* Asynchronous Set: This flip-flop includes an extra input called "SET" or "SETB" (set) that, when asserted (typically set to logic 1), immediately forces the output Q to 1, regardless of the clock or data input.  

* Clock-Controlled: Similar to other flip-flops, it operates on the rising or falling edge of a clock signal, and its output state (Q) changes accordingly.  

* Memory Element: It is commonly used in digital systems to create memory elements that can be set asynchronously to a specific state (usually 1) for initialization or error recovery purposes.  

* Synchronization: The D flip-flop with asynchronous set helps synchronize and control the timing of data transitions in sequential logic circuits, ensuring proper behavior during both normal operation and exceptional conditions.  
  
* gvim dff_async_set.v
![Screenshot from 2023-09-03 21-53-22](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/8094e53f-bbdc-4e99-b78c-aa1fe0c8c9b4)

* Simulation(Outside of Yosys)
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
iverilog dff_async_set.v tb_dff_async_set.v
./a.out
gtkwave tb_dff_async_set.vcd
````
![Screenshot from 2023-09-03 22-18-58](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/df4a571d-1df3-49a7-b1af-1646f169e89f)
![Screenshot from 2023-09-03 22-19-27](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/775657df-cab1-4bc6-840c-4254bffda128)
* Synthesis
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog dff_async_set.v
synth -top dff_async_set
dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
````
![Screenshot from 2023-09-03 23-13-12](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/4ac273dc-2a76-4753-b4bd-41d2eecd4666)




#### D Flip Flop with Asynchronous Reset and Synchronous Reset 

* Data Storage: This flip-flop can store a single binary bit (0 or 1) of data, just like a regular D flip-flop.  

* Asynchronous Reset: It features an "ASYN_RESET" or "CLR" input for asynchronous reset, which, when asserted (typically set to logic 0), immediately forces the output Q to 0, regardless of the clock or data input. This provides a rapid and asynchronous means of clearing the flip-flop's state.  

* Synchronous Reset: In addition to the asynchronous reset, it also has a "SYN_RESET" input for synchronous reset. When the "SYN_RESET" signal is asserted synchronously with the clock edge, it clears the flip-flop's state to a known value (usually 0) but only during the clock transition.  

* Clock-Controlled: Like all flip-flops, it operates on the rising or falling edge of a clock signal, ensuring that data changes and resets occur at well-defined moments.  

* Memory Element: This combined flip-flop serves as a memory element and can be cleared both asynchronously for immediate reset and synchronously to control the timing of resets, making it versatile for various applications in digital systems.  

* Synchronization: It aids in synchronizing data transitions and provides flexible reset options, accommodating different design requirements, such as initialization, error recovery, or controlled state changes during specific clock cycles.

* gvim dff_asyncres_syncres.v
![Screenshot from 2023-09-03 21-55-41](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/6bf78b4a-7aa2-47f4-956b-f54423d5e53d)
*Simulation(Outside of Yosys)
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
iverilog dff_asyncres_syncres.v tb_dff_asyncres_syncres.v
./a.out
gtkwave tb_dff_asyncres_syncres.vcd
````
![Screenshot from 2023-09-03 22-27-43](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/4f4c6dc3-0230-4abf-9a6a-ecda234500b7)
![Screenshot from 2023-09-03 22-27-53](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/797c66bd-58ce-4297-a433-ae744276eb24)  
* Synthesis
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog dff_asyncres_syncres.v
synth -top dff_asyncres_syncres
dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
````
![Screenshot from 2023-09-03 23-15-52](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/cef54d29-d0d7-41a8-8486-703611c4ee5f)  

</details>
<details>
<summary>Interesting Optimizations</summary>
* Outside of Yosys
* gvim mult_2.v
 
![Screenshot from 2023-09-03 23-24-44](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/2dda0623-34eb-4a9b-b79e-cf27f16ce522)

````
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog mult_2.v
synth -top mul2
````
![Screenshot from 2023-09-03 23-26-50](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/08e77f94-a021-469a-81fd-a5edb52f5176)  

````
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
````
![Screenshot from 2023-09-03 23-27-44](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/db7b2dfc-a79e-4d5e-873f-866f90e6ee6b)

````
write_verilog -noattr mul2_netlist.v
!gvim mul2_netlist.v
````
![Screenshot from 2023-09-03 23-29-59](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/1517e29e-c925-461c-965e-6925d3a0cb7c)

* !gvim mult_8.v
![Screenshot from 2023-09-03 23-31-34](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/f209f693-a0f1-4f5d-a0f1-ddcbd7835bab)

````
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
read_verilog mult_8.v
synth -top mult8
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
````
![Screenshot from 2023-09-03 23-33-12](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/2bb81941-bf23-4c66-b1ba-1e136211ef2d)  

![Screenshot from 2023-09-03 23-33-51](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/965d4559-6492-4cb1-b196-e58e0816f399)

````
yosys
write_verilog -noattr mult8_netlist.v
!gvim mult8_netlist.v
````
![Screenshot from 2023-09-03 23-35-26](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/7ff13d84-a272-41d1-ad61-66f84f66a544)


</details>

### Day 5
#### Combinational and Sequential optimizations
<details>
 <summary>Introductions to optimizations</summary>

* Combinational Logic Optimisation

1.Squeezing the logic to get the most optimised design
-Area and Power savings

2.Constant Propagation
-Direct Optimisation

3.Boolean Logic Optimisation
-K-Map
-Quine McKluskey

* Sequential logic Optimisation
1.Basic
-Sequential Constant propagation

2.Advanced
-State optimisation
-Retiming
-Sequential Logic Cloning (Floor Plan Aware Synthesis)

</details>

<details>
 <summary> Combinational Logic Optimizations </summary>
<details>
 <summary> opt_check</summary>

 ````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

gvim opt_check.v

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog opt_check.v

synth -top opt_check

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show
````
![Screenshot from 2023-09-04 02-05-55](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/f7f10495-4986-4496-8cb4-89717427c2e4)
![Screenshot from 2023-09-04 02-06-18](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/b03eb181-69f8-4f75-a3e2-fcfe2b8944eb)
![Screenshot from 2023-09-04 02-08-18](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/5074021d-5d65-45c4-a8e2-2d2fcec98c97)
![Screenshot from 2023-09-04 02-09-29](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/ea9a9bb2-2f32-4f7a-af7a-01461b1f9676)

</details>

<details>
 <summary> opt_check2 </summary>
 
 ````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

gvim opt_check2.v

cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog opt_check2.v

synth -top opt_check2

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show
````
![Screenshot from 2023-09-04 02-14-29](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/8911da1f-5264-4114-9fe9-2de671b2e17b)
![Screenshot from 2023-09-04 02-15-33](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/3f13a289-efb6-491f-ad01-83253faf358e)
![Screenshot from 2023-09-04 02-16-26](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/e383aa64-c344-4b03-bcfe-c8967a0d94ad)

</details>

<details>
 <summary>opt_check3</summary>

 ````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

gvim opt_check3.v

cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog opt_check3.v

synth -top opt_check3

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show
````
![Screenshot from 2023-09-04 02-18-35](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/cf371d0b-dde6-4157-af30-8e9f45e26cfa)
![Screenshot from 2023-09-04 02-19-14](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/29b34ec1-dde5-45c5-8511-f96f25350e9f)
![Screenshot from 2023-09-04 02-19-38](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/3cea66a4-4a2f-46d7-94d4-f68c4e4d733f)

</details>

<details>
 <summary>opt_check4</summary>

 ````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

gvim opt_check4.v

cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog opt_check4.v

synth -top opt_check4

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show
````
![Screenshot from 2023-09-04 02-29-06](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/49b0c511-3400-4941-a9c0-ece7e2c922ca)
![Screenshot from 2023-09-04 02-29-30](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/a03a0e3c-3609-44b1-bc04-fb12e5bd335f)
![Screenshot from 2023-09-04 02-29-50](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/7947607a-c8ad-4dc0-9d13-2bc5f967ff4e)


</details>

<details>
 <summary> multiple_module_opt </summary>

  ````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

gvim multiple_module_opt.v

cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog multiple_module_opt.v

synth -top multiple_module_opt

flatten

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show
````
![Screenshot from 2023-09-04 02-35-21](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/22154e3a-29f4-441e-ad54-38a41b697a2c)
![Screenshot from 2023-09-04 02-36-32](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/b98d744b-2a4f-4c47-bfa2-1af3a4fd82a6)
![Screenshot from 2023-09-04 02-36-46](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/149b6965-2a71-47a8-8592-21f489518c60)
![Screenshot from 2023-09-04 02-37-59](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/7646be9f-db3a-4e03-82ff-f58ee107e0e4)

</details>

</details>

<details> 
 <summary>Sequential Logic</summary>
<details>
 <summary>dff_const1</summary>

 ````
 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
 
 gvim dff_const1.v

 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

 iverilog dff_const1.v tb_dff_const1.v

 ./a.out

 gtkwave tb_dff_const1.vcd

 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog dff_const1.v

synth -top dff_const1

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

````

![Screenshot from 2023-09-04 02-43-54](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/f7158103-855c-43fe-8a4f-167d3197f862)
![Screenshot from 2023-09-04 02-46-24](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/6b2acd13-2746-4d94-aca3-8edfb00d1fe7)
![Screenshot from 2023-09-04 02-47-35](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/d3635f1e-3ab5-435d-9295-cac9ea8a7d77)
![Screenshot from 2023-09-04 02-48-15](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/37062bce-4323-446b-9b4e-6ba441458555)

</details>

<details>
 <summary>dff_const2</summary>

 ````
 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
 
 gvim dff_const2.v

 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

 iverilog dff_const2.v tb_dff_const2.v

 ./a.out

 gtkwave tb_dff_const2.vcd

 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog dff_const2.v

synth -top dff_const2

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

````
![Screenshot from 2023-09-04 02-50-57](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/64acf4fc-085b-4fe4-82e1-d5512a217299)
![Screenshot from 2023-09-04 02-53-17](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/6d2a2023-48b1-4cc3-8ccb-4312a2dadafb)
![Screenshot from 2023-09-04 02-53-50](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/7ee62cdb-b859-4097-a0dc-721c3990d7a3)
![Screenshot from 2023-09-04 02-54-11](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/adfc7166-8862-4377-8977-b02fd04f94e3)



</details>

<details>
 <summary>dff_const3</summary>

 ````
 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
 
 gvim dff_const3.v

 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

 iverilog dff_const3.v tb_dff_const3.v

 ./a.out

 gtkwave tb_dff_const3.vcd

 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog dff_const3.v

synth -top dff_const3

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

````
![Screenshot from 2023-09-04 02-56-40](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/70d193dc-0e02-4f5b-81ab-07844ee97d24)
![Screenshot from 2023-09-04 02-58-01](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/9d26f8b4-a985-4dd8-9506-bee12423cd88)
![Screenshot from 2023-09-04 02-58-25](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/2d9cdd9d-3aa2-4f4e-ba87-ad43bb7acd05)
![Screenshot from 2023-09-04 02-58-49](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/2f214d22-3627-463e-bb0f-2a7e9554cf5f)

</details>

<details>
 <summary>dff_const4</summary>

 ````
 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
 
 gvim dff_const4.v

 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

 iverilog dff_const4.v tb_dff_const4.v

 ./a.out

 gtkwave tb_dff_const4.vcd

 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog dff_const4.v

synth -top dff_const4

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

````
![Screenshot from 2023-09-04 03-05-43](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/7c5bfa05-f3e3-4835-a480-041566c1dc50)
![Screenshot from 2023-09-04 03-07-27](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/0c689153-7c98-4870-84e6-6b6cb2fecf6c)
![Screenshot from 2023-09-04 03-08-02](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/5056054e-1d85-4f8d-b453-c7af9760e195)
![Screenshot from 2023-09-04 03-08-15](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/6182c8e0-b352-4e23-b598-5d47341e04b0)

</details>

<details>
 <summary>dff_const5</summary>

 ````
 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
 
 gvim dff_const5.v

 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

 iverilog dff_const5.v tb_dff_const5.v

 ./a.out

 gtkwave tb_dff_const5.vcd

 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog dff_const5.v

synth -top dff_const5

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

````
![Screenshot from 2023-09-04 03-09-46](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/4a20dab3-db28-4e88-9d62-5ff96520adf8)
![Screenshot from 2023-09-04 03-10-30](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/b89fb7f8-e104-4701-9aaf-287285c1dae5)
![Screenshot from 2023-09-04 03-10-56](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/5df7549a-bee1-458f-92f2-3216dfb49ed6)
![Screenshot from 2023-09-04 03-14-41](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/90fbcbf6-2576-46f6-b14b-66588fe3cd5f)

</details>

</details>

<details>
 <summary> Sequential Logic for Unused Outputs</summary>
 
<details>
<summary> counter_opt </summary>

 ````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

gvim counter_opt.v

cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog counter_opt.v

synth -top counter_opt

dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

````
![Screenshot from 2023-09-04 03-19-47](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/f101d988-2f27-4d52-a646-6c42c7d423d4)
![Screenshot from 2023-09-04 03-20-42](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/af5b7da8-552d-45f9-b44b-c7f1413832ea)
![Screenshot from 2023-09-04 03-21-38](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/4b3ab355-26dd-403d-a997-4c1add151b2f)

</details>

<details>
<summary> counter_opt2 </summary>

 ````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

gvim counter_opt2.v

cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog counter_opt2.v

synth -top counter_opt

dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

````
![Screenshot from 2023-09-04 03-23-42](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/03ea848e-402b-4e26-84cb-950f7109bc72)
![Screenshot from 2023-09-04 03-26-30](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/af38f5b2-693e-48b4-a356-e911753004c9)
![Uploading Screenshot from 2023-09-04 03-27-01.png…]()

</details>

</details>
 
</details>

### Day 6

#### GLS, blocking vs non-blocking and Synthesis-Simulation mismatch

<details>
 <summary> GLS, Synthesis-Simulation mismatch and Blocking/Non-blocking statements </summary>
 
* GLS is GATE LEVEL SIMULATION     


* What is GLS?  
-Running the test bench with Netlist as Design Under Test.  
-Netlist is logically same as RTL Code.  
  -Same Test Bench will align with the Design.  

* Why GLS?  
-Verify the logical correctness of design after synthesis  
-Ensuring the timing of the design is met.  
  -For this GLS needs to be run with delay annotation.  

![Screenshot from 2023-09-04 04-28-20](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/ea0acd39-2602-4176-a7c9-0cf019c3fa91)  

* Gate level models  
  - Timing aware(functionality+timing) validation  
  - Functional validation   

* Synthesis-Simulation mismatch  
  A synthesis-simulation mismatch is a discrepancy between the expected behavior of a digital circuit during the design phase (synthesis) and its actual behavior during simulation. It often occurs due to timing issues, optimization, modeling errors, or simulation setup problems and requires debugging to ensure the circuit functions correctly.  

*Some examples of why synthesis simulation mismatch  

*Missing Sensitivity List  
Not including all relevant signals into the always block. This can lead to a synthesis-simulation mismatch where the simulation works as expected, but the synthesized hardware behaves differently.  

*Blocking and Non-Blocking Statements in verilog  
 
 Blocking Statements:  

 Sequential Execution: Blocking assignments (=) are used for sequential execution within an always block. This means that statements are executed one   after the other in the order they appear in the code.  
 Simulation-Synthesis Mismatch (Blocking): In simulation, blocking assignments behave predictably and are often used for testbench modeling. However,   when it comes to synthesis, blocking assignments can lead to mismatches because synthesis tools might optimize the order of execution differently,     potentially causing differences in behavior between simulation and the actual synthesized hardware.  

 Non-Blocking Statements:  

 Parallel Execution: Non-blocking assignments (<=) are used for parallel execution within an always block. This means that all non-blocking             assignments within the same block are executed concurrently, without regard to the order in which they appear.  
 Simulation-Synthesis Mismatch (Non-Blocking): Non-blocking assignments are generally preferred for synthesizable RTL (Register-Transfer Level) code    because they accurately model parallel hardware behavior. However, if you misuse non-blocking assignments or use them inappropriately in simulation-   only code, it can lead to mismatches, as the simulation might behave differently due to the concurrent execution of assignments.  
    
-Synthesis-Simulation mismatches:
Blocking assignments are sequentially executed and can lead to mismatches when synthesis tools optimize differently.
Non-blocking assignments represent parallel hardware behavior and can lead to mismatches if misused or applied to non-synthesizable constructs in simulation-only code.

* Cavets with Blocking statements

1. Order of Execution(Sequential): Blocking assignments (`=`) specify a strict sequential order of execution within an `always` block. Each statement is executed one after the other, following the order in the code.  

2. Potential for Mismatches: Synthesis tools aim to optimize hardware for area, speed, and other factors. They may re-order or parallelize operations differently than the strict sequential execution implied by blocking assignments. This can result in significant mismatches between simulation and synthesized hardware behavior.  

3. Race Conditions: In some cases, blocking assignments can introduce race conditions in simulation that don't exist in hardware. For instance, if multiple signals are updated sequentially in a clocked `always` block using blocking assignments, it can create a race condition that doesn't accurately represent the behavior of flip-flops and combinatorial logic in the synthesized design.  

4. Debugging Challenges: Synthesis-simulation mismatches stemming from the use of blocking assignments can be challenging to debug. The code may work correctly in simulation but fail in actual hardware due to optimizations made by the synthesis tool. Debugging such issues often requires a deep understanding of both Verilog and the specific synthesis tool's optimization techniques.  

5. Best Practices: To mitigate synthesis-simulation mismatches related to blocking assignments, it's essential to follow best practices. This includes using non-blocking assignments (`<=`) for sequential logic, avoiding race conditions, and ensuring that the Verilog code accurately represents the intended hardware behavior. Behavioral simulations may often suffice with blocking statements to model functionality, but RTL simulations require a meticulous choice between blocking and non-blocking assignments to accurately replicate hardware behavior and minimize synthesis-simulation mismatches.

</details>

<details>
 <summary> Labs on GLS and Synthesis-Simulation Mismatch </summary>
 <details> 
  <summary>ternary_operator_mux</summary>
 
  ````
  cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
  
  gvim ternary_operator_mux.v
  ````

![Screenshot from 2023-09-04 04-57-04](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/9997b190-c4db-4a40-9b33-f7a788ce08ec)

* Simulation
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

iverilog ternary_operator_mux.v tb_ternary_operator_mux.v

./a.out

gtkwave tb_ternary_operator_mux.vcd

````
![Screenshot from 2023-09-04 04-59-52](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/9d806333-605f-461e-8a43-9e4a8ed4b2dd)


* Synthesis
  
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog ternary_operator_mux.v

synth -top ternary_operator_mux

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show
````
![Screenshot from 2023-09-04 05-02-14](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/d29ef34a-c7fd-43fc-a720-f75c4bc356b9)
![Screenshot from 2023-09-04 05-02-34](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/cf99a79a-164e-4916-8d3d-73363837f099)

* GLS
````
iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v ternary_operator_mux_net.v tb_ternary_operator_mux.v

./a.out

gtkwave tb_ternary_operator_mux.vcd

````
![Screenshot from 2023-09-04 04-59-52](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/74b8c697-24a8-4ac8-afda-ea43e033ef92)

</details>

<details>
 <summary>bad_mux</summary>
 
 ````
 cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
 
 gvim bad_mux.v
 ````
![Screenshot from 2023-09-04 05-09-25](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/390f1333-ea56-416f-90e0-0b680c72fcb2)


* Simulation
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

iverilog bad_mux.v tb_bad_mux.v

./a.out

gtkwave tb_bad_mux.vcd

````
![Screenshot from 2023-09-04 05-11-33](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/b6fa5f48-f251-4748-9ea3-a05f6f0e15da)
* With the variations of select lines the output obtained from the mux is not accurate.

* Synthesis
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog bad_mux.v

synth -top bad_mux

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show
````
![Screenshot from 2023-09-04 05-17-35](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/c32a48ba-10f1-433a-b1c6-a1e225be4d39)

![Screenshot from 2023-09-04 05-19-38](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/6f9c3796-d20c-41a3-9f91-e48e7f74aeaa)  

* GLS
````
iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v bad_mux_net.v tb_bad_mux.v

./a.out

gtkwave tb_bad_mux.vcd
````
![Screenshot from 2023-09-04 05-21-55](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/e4e341e8-e311-47af-95ad-29f1457f88dd)

** Bad mux with respect to Synthesis Simulation mismatch
![Screenshot from 2023-09-04 05-23-46](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/89f41537-4d0a-4c5b-bf2f-545fa3d12bc9)  


</details>
</details>

<details>
 <summary> Labs on Synthesis-Simulation Mismatch for Blocking Statement </summary>
 <details>
  <summary>Blocking caveat</summary>
  
  ````
  cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
  
  gvim blocking_caveat.v
  ````
![Screenshot from 2023-09-04 05-29-03](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/a43bb4f2-a60d-4af2-88d4-42347bd97b32)

* Simulation
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

iverilog blocking_caveat.v tb_blocking_caveat.v

./a.out

gtkwave tb_blocking_caveat.vcd

````

![Screenshot from 2023-09-04 05-32-46](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/d695ab3b-c095-4e9b-9f5f-83001a6606eb)

* Synthesis
````
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog blocking_caveat.v

synth -top blocking_caveat

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show
````
![Screenshot from 2023-09-04 05-34-14](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/42de4dc1-758a-482b-9157-cca008afc6d3)
![Screenshot from 2023-09-04 05-34-25](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/4f7601ee-dc0e-44e1-9ce1-84ba6b649a9b)

* GLS
````
iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v blocking_caveat_net.v tb_blocking_caveat.v

./a.out

gtkwave tb_blocking_caveat.vcd   
````
![Screenshot from 2023-09-04 05-36-40](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/7e1e465b-7f4a-4648-9ddf-b5a744343353)

** Blocking caveat Synthesis Simulation mismatch
![Screenshot from 2023-09-04 05-37-49](https://github.com/lalithlochanr/pes_asic_class/assets/108328466/7e831276-344d-4a88-92e5-9cc200348fc1)


 </details>
 
</details>












