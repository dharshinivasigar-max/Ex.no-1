## Arithmetic-operation-using-8086
## 8086 Assembly Language Programs for Arithmetic Operations
## AIM
To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.
## APPARATUS REQUIRED
- Personal Computer with MASM Software
## ADDITION
#### Algorithm

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
    MOV SI, 2000H        
    MOV AX, [SI]         
    MOV BX, [SI+02H]     
    MOV CL, 00H          
    ADD AX, BX           
    JNC L1               
    INC CL               
L1:
    MOV [SI+04H], AX     
    MOV [SI+06H], CL     
    MOV AH, 4CH          
    INT 21H
CODE ENDS
END START
END
```
## Output Table

| MEMORY LOCATION | INPUT | MEMORY LOCATION | OUTPUT |
|-----------------|-------|-----------------|--------|
|  2000           | FF    |      2006       |   01   |
|  2001           | FF    |      2005       |   FF   |
|  2002           | FF    |      2004       |   FE   |
|  2003           | FF    |                 |        |

## Manual calculations

<img width="1488" height="961" alt="image" src="https://github.com/user-attachments/assets/0babf9ba-be33-45ac-9ef3-57b9913b1a7d" />


## OUTPUT IMAGE FROM MASM SOFTWARE

<img width="628" height="265" alt="image" src="https://github.com/user-attachments/assets/11f26184-a1e8-4fb8-8685-3a8d99ca4ec5" />


## 2.SUBTRACTION
#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.
<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/15f06026-338b-42bc-883c-85bd2f8bf126" />

## Program
```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H
START:
    MOV AX, CODE
    MOV DS, AX
    MOV SI, 2000H        
    MOV AX, [SI]         
    MOV BX, [SI+02H]     
    MOV CL, 00H          
    SUB AX, BX           
    JNC L1               
    INC CL               
L1:
    MOV [SI+04H], AX     
    MOV [SI+06H], CL     
    MOV AH, 4CH          
    INT 21H
CODE ENDS
END START
END
```
#### Output Table

| MEMORY LOCATION | INPUT | MEMORY LOCATION | OUTPUT |
|-----------------|-------|-----------------|--------|
|  2000           | 22    |      2005       |   11   |
|  2001           | 22    |      2004       |   11   |
|  2002           | 11    |                 |        |
|  2003           | 11    |                 |        |

#### Manual Calculations
<img width="1488" height="900" alt="image" src="https://github.com/user-attachments/assets/30f4006d-b833-49c1-b4a2-0c9648481695" />



## OUTPUT SCREEN FROM MASM SOFTWARE

<img width="648" height="262" alt="image" src="https://github.com/user-attachments/assets/03134288-106b-4dcf-8438-03d4d178b979" />

## 3. MULTIPLICATION
#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

## FLOWCHART
<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />

## Program
```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H
START:
    MOV AX, CODE
    MOV DS, AX
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
END START
```
### Output Table

| MEMORY LOCATION | INPUT | MEMORY LOCATION | OUTPUT |
|-----------------|-------|-----------------|--------|
|  2000           | FF    |      2007       |   12   |
|  2001           | 44    |      2006       |   98   |
|  2002           | FF    |      2005       |   76   |
|  2003           | 44    |      2004       |   01   |

### Manual Calculations
<img width="1488" height="1027" alt="image" src="https://github.com/user-attachments/assets/22ed9dde-ef75-4d47-aa1f-032cdbdce5e9" />



## OUTPUT SCREEN FROM MASM SOFTWARE

<img width="622" height="252" alt="image" src="https://github.com/user-attachments/assets/9977f7d0-9ceb-4c99-b657-03d9294b166b" />

## 4. DIVISION
#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.
## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />

## Program
```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H
START:
    MOV AX, CODE
    MOV DS, AX
    MOV SI,2000H
    MOV DX,0000H        
    MOV AX,[SI]         
    MOV BX,[SI+02H]     
    DIV BX              
    MOV [SI+04H],AX     
    MOV [SI+06H],DX     
    INT 3               
CODE ENDS
END START
```

### Output Table

| MEMORY LOCATION | INPUT | MEMORY LOCATION | OUTPUT |
|-----------------|-------|-----------------|--------|
|  2000           | 44    |      2004       |   02   |
|  2001           | 00    |                 |        |
|  2002           | 22    |                 |        |
|  2003           | 00    |                 |        |

### Manual Calculations
<img width="1488" height="1080" alt="image" src="https://github.com/user-attachments/assets/2f95ab65-4c90-4ce6-83f6-bc9105633bcb" />



### OUTPUT FROM MASM SOFTWARE

<img width="647" height="371" alt="image" src="https://github.com/user-attachments/assets/4e009688-d195-4c6c-b78f-4a5ca8f4a43e" />



## RESULT
Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.


