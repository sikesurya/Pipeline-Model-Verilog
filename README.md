# 4-Stage-Pipeline-Model

Tool(s) used: Xilinx Vivado

This pipeline carries out the following stage-wise operations:

1. Inputs: Three register addresses("rs1", "rs2" and "rd"), an ALU function (func) and a memory address (addr)
2. Stage 1:
   Read two 16bit numbers from "rs1" and "rs2", and store them in A and B respectively
3. Stage 2:
   Perform an ALU operation on A and B specified by "func", and store in Z.
4. Stage 3:
   Write the value of Z in register "rd".
5. Stage 4:
   Also write the value of Z in memory location "addr".

Assumptions:

1. There is a register bank containing 16 16-bit registers.
   - 4 bits are needed to specify a register address.
   - 2 registers read, 1 writes at every clock cycle.
   - Register address are "rs1", "rs2", "rd".

2. Memory is organized as 256x16.
   - 8 bits are required to specify memory address.
   - Every memory location contains 16 bits of data, which can be read in a single clock cycle.
   - Memory addresses are specified as "addr"

ALU Functions:

| func  | Operation |
| ------------- | ------------- |
| 0000  | ADD  |
| 0001  | SUB  |
| 0010  | MUL  |
| 001l  | SELA  |
| 0100  | SELB  |
| 0101  | AND  |
| 0110  | OR  |
| 0111  | XOR  |
| 1000  | NEGA  |
| 1001  | NEGB  |
| 1010  | SRA |
| 1011  | SLA  |

BLOCK DIAGRAM:

![bd](https://github.com/user-attachments/assets/4ba07e02-224a-46b3-be8a-00ec219e055e)

Simulation Waveform:

![image](https://github.com/user-attachments/assets/3cd5dd51-26b5-4a50-9d46-dadae8828c9d)



   
