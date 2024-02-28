+++
title = 'A Test Post'
date = 2024-02-23T23:02:03-06:00
draft = false
+++
Formatting Example:
```asm
.global _start

_start:

    LDR R1, =_test
    MOV R3, #0x1, LSL 2
    STR R0, [R1, #0x2]!
    ADD R2, R1, R3

.data
_test: .ascii "Test!"
```
