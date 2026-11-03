## Arithmetic-operation-using-8086
## 8086 Assembly Language Programs for Arithmetic Operations
## AIM
To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.
## APPARATUS REQUIRED
- Personal Computer with MASM Software
## ADDITION
**Algorithm**
 1. Initialize memory location in HL register.
 2. Store 1st data.
 3. Increment HL to enter 2nd data.
 4. Move 2nd number to accumulator.
 5. Decrement HL.
 6. Add value in memory with accumulator.
 7. Store result.
 8. Stop.
## FLOWCHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/e780b4ac-e379-4d29-94d6-1cb447053778" />

## Program

```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H
START:
    MOV AX, CODE
    MOV DS, AX
    MOV SI, 2000H        ; Point to first number
    MOV AX, [SI]         ; Load first 16-bit number
    MOV BX, [SI+02H]     ; Load second 16-bit number
    MOV CL, 00H          ; Clear carry flag storage
    ADD AX, BX           ; AX = AX + BX
    JNC L1               ; Jump if no carry
    INC CL               ; Store carry = 1
L1:
    MOV [SI+04H], AX     ; Store sum
    MOV [SI+06H], CL     ; Store carry
    MOV AH, 4CH          ; Exit to DOS
    INT 21H
CODE ENDS
END START
END
```
## Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
|--------------------------|---------------------------|
| 1200H  01  12           |                           |

## Manual calculations

<img width="1535" height="1215" alt="image" src="https://github.com/user-attachments/assets/fa87f5a2-37f7-47fe-99c3-7f50efe3cc46" />

## OUTPUT IMAGE FROM MASM SOFTWARE

<img width="636" height="431" alt="image" src="https://github.com/user-attachments/assets/10765e58-b820-4cfa-89fc-2a149ec4caa6" />

## 2.SUBTRACTION
**Algorithm**
  1.Initialize memory and store 1st data.
  2.Increment to get 2nd data.
  3.Move 2nd data to accumulator.
  4.Subtract memory content.
  5.Store result.

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/15f06026-338b-42bc-883c-85bd2f8bf126" />

## Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```
#### Output Table

| **MEMORY LOCATION (INPUT)** | **MEMORY LOCATION (OUTPUT)** |
| --------------------------- | ---------------------------- |
|                             |                              |

#### Manual Calculations
<img width="790" height="610" alt="WhatsApp Image 2026-11-03 at 2 00 23 PM" src="https://github.com/user-attachments/assets/14bd87c2-2e42-45ae-98e1-a61c606735d7" />

## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="636" height="431" alt="image" src="https://github.com/user-attachments/assets/752825cf-e4d6-4023-8a65-63582fc89df6" />

## 3. MULTIPLICATION
**Algorithm**
 1.Initialize memory and store operands.
 2.Move operands to registers.
 3.Multiply.
 4.Store result.

## FLOWCHART
<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />

## Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```
### Output Table

| **MEMORY LOCATION (INPUT)** | **MEMORY LOCATION (OUTPUT)** |
|:----------------------------:|:-----------------------------:|
|                              |                               |
|                              |                               |
|                              |                               |

### Manual Calculations
<img width="1535" height="1304" alt="image" src="https://github.com/user-attachments/assets/3bf5ed08-056d-4270-9bd3-40c7004e56b1" />

## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="642" height="435" alt="image" src="https://github.com/user-attachments/assets/e4d34710-40da-479a-80f1-57fdf6f49b37" />

## 4. DIVISION
**Algorithm**
  1.Load memory location of operands.
  2.Perform division.   
  3.Store result.
## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />

## Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

### Output Table

| **MEMORY LOCATION (INPUT)** | **MEMORY LOCATION (OUTPUT)** |
|:---------------------------:|:----------------------------:|
|                             |                              |
|                             |                              |
|                             |                              |

### Manual Calculations

<img width="1535" height="1094" alt="image" src="https://github.com/user-attachments/assets/15f34063-e143-4bb3-a046-3a0d32850e70" />

### OUTPUT FROM MASM SOFTWARE
<img width="635" height="427" alt="image" src="https://github.com/user-attachments/assets/fb099757-da8a-415b-be83-8cb4083341be" />


## RESULT
Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.


