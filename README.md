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














