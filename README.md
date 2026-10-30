##Arithmetic-operation-using-8086
##8086 Assembly Language Programs for Arithmetic Operations
##AIM
To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.
##APPARATUS REQUIRED
- Personal Computer with MASM Software
##ADDITION
**Algorithm**
 1. Initialize memory location in HL register.
 2. Store 1st data.
 3. Increment HL to enter 2nd data.
 4. Move 2nd number to accumulator.
 5. Decrement HL.
 6. Add value in memory with accumulator.
 7. Store result.
 8. Stop.
##FLOWCHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/e780b4ac-e379-4d29-94d6-1cb447053778" />
##Program
```
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
##Output Table   
