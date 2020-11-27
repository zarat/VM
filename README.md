# vm
A virtual machine executing bytecode

<pre>
// compile and run a binary
as [assembly] [binary]
vm [binary]

// run in realtime mode
vm
</pre>

In realtime mode (will be removed soon) please only use digit numbers

<pre>
  mov ax 0x7e3 (2019)
  mov bx 0x7c0 (1984)
  mod ax bx
  ldr ax
  print
</pre>

You have 14 registers, each 32 bit

# Registers
* ax 
* bx 
* cx 
* dx
* r1 - r10

# Instruction set
* [mov](#mov)
* [push](#push)
* [pop](#pop)
* [ldr](#ldr)
* [str](#str)
* [ldm](#ldm)
* [stm](#stm)
* [ldmr](#ldmr)
* [stmr](#stmr)
* [add](#add)
* [sub](#sub)
* [mul](#mul)
* [div](#div)
* [mod](#mod)
* [eq](#eq)
* [lt](#lt)
* [gt](#gt)
* [leq](#leq)
* [geq](#geq)
* [jmp](#jmp)
* [jz](#jz)
* [jnz](#jnz)
* [ret](#ret)
* [print](#print)
* [printc](#printc)
* [read](#read)
* [write](#write)
* [puts](#puts) 
* [gets](#gets)
* [readc](#readc)
* [cmp](#cmp)
* [prc](#prc)
* [si](#si)

# Explaination
## mov
Move into register 
parameters can be 2 registers, or a register and an immediate value
when moving reg to reg, the value of the moved reg still remains

## push
Push a value on the stack
argument is a register or an immediate value
if its a register, it gets cleared, if you dont want to clear the register use ldr

## pop
Pop a value off the stack
argument is the register where to store the value

## ldr
Load a register on the stack
argument is the register
the value still remains in the register, if you want to clear it use pop

## str
Store a value from the stack into a register
the value remains on the stack, if you want to clear it use push

## ldm
Load a byte from memory location

## stm
Store a byte at a memory location

## ldmr
load memory range

## stmr
store memory range

## add
Add 2nd to 1st
The value of the 2nd register/value will be added to the 1st register
if 2nd was a reg it still remains
the result is in the 1st reg

## sub
Sub 2nd from 1st
The value of the 2nd register/value will be substracted to the 1st register
if 2nd was a reg it still remains
the result is in the 1st reg

## mul
Mul 1st times 2nd reg
The value of the 1st register will be multiplied times the 2nd register/value
if 2nd was a reg it still remains
the result is in the 1st reg

## div
Divide 1st by 2nd
The value of the 1st register will be divided by the 2nd reg/value
if 2nd was a reg it still remains
the result is in the 1st reg

## mod
Divide 1st by 2nd and get the modulo
the modulo is in the 1st reg

## jmp
jump to a label

## jz
jump to a label if the last conditional operation was true

## jnz
jump to a label if the last conditional operation was NOT true

## eq
compare 2 values on the stack

## lt
compare 2 values on the stack
if the top value on the stack is lower than the 2nd, it is true

## gt
compare 2 values on the stack
if the top value on the stack is greater than the 2nd, it is true

## leq
compare 2 values on the stack
if the top value on the stack is lower OR equal than the 2nd, it is true

## geq
compare 2 values on the stack
if the top value on the stack is greater OR equal than the 2nd, it is true

## ret
return to the last program counter, the program counter is automatically pushed/poped when using (jmp, jz, jnz)

## print
print a byte from the stack as number

## printc
print a byte from the stack as char

## read
read a line from stdin

## write
write data from memory to stdout

## puts
data, length and address on the stack, store in memory (NULL terminated)

## gets 
get a memory location onto the stack (NOT null terminated)

## readc
read a char from stdin onto the stack

## cmp
compare 2 memory locations on the stack

## prc
call a system command, the memory location of the commandstring and the memory location to store has to be on top of the stack

## si
get the stackpointer into ax
