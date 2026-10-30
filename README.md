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
MOV CL,00H
MOV AX,1234H
MOV BX,1234H
ADD AX,BX
JNC L1
INC CL
L1:MOV SI,1200H
MOV [SI],AX
MOV [SI+2],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```
## Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
|--------------------------|---------------------------|
| 1200H  01  12           |                           |

##OUTPUT IMAGE FROM MASM SOFTWARE
##2.SUBTRACTION
Algorithm
1.Initialize memory and store 1st data.
2.Increment to get 2nd data.
3.Move 2nd data to accumulator.
4.Subtract memory content.
5.Store result.

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/15f06026-338b-42bc-883c-85bd2f8bf126" />

##program
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

(Add your calculation here)
