# RUN1718
This is the processor that has been designed for the course PROCESSORS in year 17-18. It is fully functioning, the assignment can be read under practical_assignment.pdf


We are not (yet) aware of any concrete bugs.

We took care of POPing R14 by checking if the instruction is equal to a POP R14 (without the condition). 
If it is equal to we send 0x00000000 instead of the pop.


#Testing
Tested with, among other things, the following code:

C++ Code:
```
for(int i = 33; i <= 126; i++){
cout << char(i);
}

```
Written in Assembly Code:        
```
.START 0        
READ [a],R1        
MOVE 33,R2  
loop: CMPf R1,R2        
WRITE R2,[-512]        
ADD 1,R2,R2        
JUMP.G loop        
HALT        
a:  .DATA 126
```
Assembled to Machine Code:
```
00000000:c01c001f
00000001:0021002f
00000002:7c00120f
00000003:e200200f
00000004:6001022f
00000005:63f00ffc
00000006:ffffffff
00000007:0000007e
```
