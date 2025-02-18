# RISC-V Talent Development Program Powered by SAMSUNG and VSD
This is a RISC-V Internship using VSDSquadron Mini based  on RISC-V architecture and uses open-source tools to teach students about VLSI SoC design and RISC-V. The instructor and guide for this internship program is Mr. Kunal Ghosh, Co-Founder of VSD.

# ABOUT ME🚀
Name: Lalu Prasad B 
-
College: Sahyadri College of Engineering and Management, Adyar, Mangaluru.
-
Email ID: lalu.ec22@sahyadri.edu.in
-
LinkedIn: [Lalu Prasad B](https://www.linkedin.com/in/lalu-prasad-81411932b)
-
<details>
<summary>TASK1:Development of C Based LAB</summary>
<img 
src="https://github.com/user-attachments/assets/987c79c7-2625-4d94-bfee-caa7b83a0f86" alt="Task Icon"/>
  <img
src="https://github.com/user-attachments/assets/7c267db8-2335-45b8-8d9b-0cce32154878" alt="Task Icon"/>
<img
src="https://github.com/user-attachments/assets/137dd367-5b26-44bf-90b4-cf600cbdb893" alt="Task Icon"/>
<img
src="https://github.com/user-attachments/assets/529e2e98-6f3b-435d-95ed-dc0c0c8dd226" alt="Task Icon"/>
</details>
<details>
<summary>TASK2:Simulation with Spike</summary>
<img 
src="https://github.com/user-attachments/assets/3d4b94d7-228a-4194-bdac-4de226cb30d4" alt="Task Icon"/>
  <img
src="https://github.com/user-attachments/assets/ca35703a-e970-4f79-8563-3136212948a3" alt="Task Icon"/>
<img
src="https://github.com/user-attachments/assets/c932e8ef-bf9a-474b-a709-53bfc0aeee55" alt="Task Icon"/>
<img
src="https://github.com/user-attachments/assets/6e18d0c5-f06c-4410-b013-d62eafa4aceb" alt="Task Icon"/>
</details>

<details>
<summary>TASK3:Identification of RISCV instructions</summary>
  <img
src="https://github.com/user-attachments/assets/e82da314-af58-47fb-b68a-eb1a51822319" alt="Task Icon"/>
<summary>1. addi sp, sp, -32</summary>

Opcode(ADDI): 0010011  
Immediate: -32 = 11111111111111100000 (12 bits)  
Registers: sp(rd) = 00010, sp(rs1) = 00010  

| imm[11:0]       | rs1    | funct3 | rd    | opcode  |
|------------------|--------|--------|-------|---------|
| 111111100000     | 00010  | 000    | 00010 | 0010011 |

---
<summary>2. sd ra, 24(sp)</summary>

Opcode(SD): 0100111  
Immediate: 24 (split into two parts: imm[11:5] and imm[4:0])  
Registers: rs1 = sp = 00010, rs2 = ra = 00001  

| imm[11:5] | rs2   | rs1   | funct3 | imm[4:0] | opcode  |
|-----------|-------|-------|--------|----------|---------|
| 0000000   | 00001 | 00010  | 011    | 11000    | 0100111 |

---

<summary>3. jal ra, 10448</summary>

Opcode(JAL): 1101111  
Immediate: 10448  
Register (rd): ra = 00001  

| imm[20] | imm[10:1] | imm[11] | imm[19:12] | rd    | opcode  |
|---------|-----------|---------|------------|-------|---------|
|   0    | 0010100000 |    0    | 10100000   | 00001 | 1101111 |

---

<summary>4. ld ra, 24(sp)</summary>

Opcode(LD): 0000011  
Immediate: 24  
Registers: rd = ra = 00001, rs1 = sp = 00010  

| imm[11:0]      | rs1   | funct3 | rd    | opcode  |
|-----------------|-------|--------|-------|---------|
| 000000011000    | 00010 | 011    | 00001 | 0000011 |

---

<summary>5. lw a1, 8(sp)</summary>

Opcode(LW): 0000011  
Immediate: 8  
Registers: rd = a1 = 01011, rs1 = sp = 00010  

| imm[11:0]      | rs1   | funct3 | rd    | opcode  |
|-----------------|-------|--------|-------|---------|
| 000000001000    | 00010 | 010    | 01011 | 0000011 |

---

<summary>6. li a0, 0</summary>

Opcode(ADDI): 0010011  
Immediate: 0  
Registers: rd = a0 = 01010, rs1 = x0 = 00000  

| imm[11:0]     | rs1   | funct3 | rd    | opcode  |
|---------------|-------|--------|-------|---------|
| 000000000000  | 00000 | 000    | 01010 | 0010011 |

---

<summary>7. jalr x0, 0(ra)</summary>

| imm[11:0]     | rs1   | funct3 | rd    | opcode  |
|---------------|-------|--------|-------|---------|
| 000000000000  | 00001 | 000    | 00000 | 1100111 |

---

<summary>8. addi a0, a0, -920</summary>

Opcode(ADDI): 0010011  
Registers: rd = a0 = 01010, rs1 = a0 = 01010  
Immediate: -920 = 110001101000 (sign-extended 12-bit value)  

| imm[11:0]     | rs1   | funct3 | rd    | opcode  |
|---------------|-------|--------|-------|---------|
| 110001101000  | 01010 | 000    | 01010 | 0010011 |

---

<summary>9. sd s0, 16(sp)</summary>

Opcode(SD): 0100111  
Registers: rs1 = sp = 00010, rs2 = s0 = 01000  
Immediate: 16 (split into imm[11:5] and imm[4:0])  
imm[11:5] = 0000000, imm[4:0] = 10000  

| imm[11:5]     | rs2   | rs1   | funct3 | imm[4:0] | opcode  |
|---------------|-------|-------|--------|----------|---------|
| 0000001       | 01000 | 00010 | 011    | 10000    | 0100111 |

---

<summary>10. lw a5, 12(sp)</summary>

Opcode(LW): 0000011  
Registers: rd = a5 = 01000, rs1 = sp = 00010  
Immediate: 12 = 000000001100  

| imm[11:0]     | rs1   | funct3 | rd    | opcode  |
|---------------|-------|--------|-------|---------|
| 000000001100  | 00010 | 010    | 01000 | 0000011 |

---

<summary>11. add a1, a1, a5</summary>
Opcode: 0110011

| funct7   | rs2   | rs1   | funct3 | rd    | opcode  |
|----------|-------|-------|--------|-------|---------|
| 0000000  | 01000 | 01011 | 000    | 01010 | 0110011 |

---

<summary>12. add a0, a1, a5</summary>

Opcode(ADD): 0110011  
Registers: rd = a0 = 01010, rs1 = a1 = 01011, rs2 = a5 = 01000  
Funct3: 000  
Funct7: 0000000  

| funct7   | rs2   | rs1   | funct3 | rd    | opcode  |
|----------|-------|-------|--------|-------|---------|
| 0000000  | 01000 | 01011 | 000    | 01010 | 0110011 |

---

<summary>13. addw a1, a1, a5</summary>

Opcode(ADDW): 0111011  
Registers: rd = a1 = 01011, rs1 = a1 = 01011, rs2 = a5 = 01000  
Funct3: 000  
Funct7: 0000000  

| funct7   | rs2   | rs1   | funct3 | rd    | opcode  |
|----------|-------|-------|--------|-------|---------|
| 0000000  | 01000 | 01011 | 000    | 01011 | 0111011 |

---
<summary>14. lui a0, 0x2b</summary>

Opcode(LUI): 0110111  
Immediate (0x2b << 12): 0000000000101011  
Register (rd): a0 = 01010  

| imm[31:12]      | rd      | opcode  |
|------------------|---------|---------|
| 0000000000101011 | 01010   | 0110111 |

 ---                   
<summary> 15. li a0,0</summary>

|imm[11:0] | 	rs1 	|funct3 |	 rd   	|opcode |
|----------|-------|-------|--------|-------|
|000000000000|	00000	|000	|01010	|0010011|
---
</details>
<details>
<summary>TASK4:Functional Simulation of RISC-V Core</summary>
</summary>
<br>
Steps to perform functional simulation of RISCV

1. Download Files:
Download the code from the reference github repo.

2. Set Up Simulation Environment:
Install iverlog using commands:

        sudo apt install iverilog
        sudo apt install gtkwave

3. To run and simulate the verilog code, enter the following command:

        iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
        ./iiitb_rv32i

4. To see the simulation waveform in GTKWave, enter the following command:

        gtkwave iiitb_rv32i.vcd

32-bits instruction used in the code:

![Instructions](<TASK4/instructions.png>)

Analysing the Output Waveform of various instructions that we have covered in this task.

1. ADD R6,R1,R2

![ADD R6,R1,R2](<TASK4/add.png>)

  32 bit instruction:32'h02208300

2. SUB R7,R1,R2

![SUB R7,R1,R2](<TASK4/sub1.png>)

32 bit instruction:32'h02209380

3. And R8,R1,R3

![And R8,R1,R3](<TASK4/and.png>)

32 bit instruction:32'h0230a400

4. OR R9,R2,R5

![OR R9,R2,R5](<TASK4/or.png>)

32 bit instruction:32'h02513480

5. XOR R10,R1,R4

![XOR R10,R1,R4](<TASK4/xor.png>)

32 bit instruction:32'h0240c500

6. SLT R11,R2,R4

![SLT R11,R2,R4](<TASK4/slt.png>)

32 bit instruction:32'h02415580

7. ADDI R12,R4,5

![ADDI R12,R4,5](<TASK4/addi.png>)

32 bit instruction:32'h00520600

8. BEQ R0,R0,15

![BEQ R0,R0,15](<TASK4/beq.png>)

32 bit instruction:32'h00f00002

</details>
