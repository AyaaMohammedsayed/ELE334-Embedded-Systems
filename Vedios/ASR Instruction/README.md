# SHIFT OPERATIONS README

## Overview
Register shift operations are essential for manipulating the bits within a register by moving them left or right by a specified number of bits, referred to as the shift length. These operations can be performed directly using instructions such as ASR, LSR, LSL, and ROR, with the results written to a destination register.

## ASR Instruction

### Description
The **Arithmetic Shift Right (ASR)** instruction shifts the bits in a register to the right by a specified number of places (`n`).

- **Operation**: The left-hand `32-n` bits of the source register `Rm` are shifted right by `n` places into the right-hand `32-n` bits of the result. 
- The original sign bit (bit[31] of `Rm`) is copied into the left-hand `n` bits of the result.

### Usage
- **Dividing Signed Values**: The ASR operation effectively divides the signed value in the register `Rm` by `2^n`, rounding towards negative infinity.
### Flags
When executing the instruction `ASRS`, the carry flag is updated to reflect the last bit shifted out (bit[n-1]) of the register `Rm`.
## Additional Resources
For a visual explanation of shift operations, check out this [YouTube video](https://www.youtube.com/watch?v=your_video_link_here).

![Example Image](https://github.com/AyaaMohammedsayed/ELE334-Embedded-Systems/blob/main/Vedios/ASR%20Instruction/ASR.png)


## Conclusion
The ASR instruction is a powerful tool for bit manipulation, especially useful for signed integer arithmetic. It is crucial to understand its operation and implications for effective programming and optimization in low-level applications.
i want to edit it to make readme file on github
### Example
In the following assembly code, the value `0x80000000` is loaded into register `R0`, and an arithmetic shift right operation is performed:

```assembly
    AREA MyData, DATA
    AREA MyCode, CODE
       ENTRY
       EXPORT __main
__main
    LDR R0, =0x00000002     ; Load value 0x80000000 into R0
    ASR R1, R0, #1          ; Arithmetic shift right R0 by 1, result in R1
    B __main                ; Loop indefinitely
    END

