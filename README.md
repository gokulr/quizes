quizes
======
Sorry my bad :P

findParent:{parent:first exec p from t where n=x;$[parent=x;show x;[findParent[parent];show x]]}


q)findParent[`G]
`A
`C
`F
`G
q)findParent[`I]
`A
`D
`I
q)findParent[`B]
`A
`B

From: Ong, William [ICG-IT] 
Sent: Friday, October 31, 2014 5:02 PM
To: Yin, Henry [ICG-IT]; *GT AP ARB; Mehrotra, Mohit [ICG-IT]
Subject: RE: question.

Oh c’mon Henry don’t hardcode please.. 

From: Yin, Henry [ICG-IT] 
Sent: Friday, October 31, 2014 4:53 PM
To: Ong, William [ICG-IT]; *GT AP ARB; Mehrotra, Mohit [ICG-IT]
Subject: RE: question.

First attempt:
Recursively find  parent until A.

q)findParent:{if[not x=`A;show x];parent:first exec p from t where n=x;$[parent=x;show x;findParent[parent]]}
q)findParent[`B]
`B
`A
q)findParent[`G]
`G
`F
`C
`A

q)findParent[`I]
`I
`D
`A



Thanks and regards,
Henry

From: Ong, William [ICG-IT] 
Sent: Friday, October 31, 2014 4:38 PM
To: *GT AP ARB; Yin, Henry [ICG-IT]; Mehrotra, Mohit [ICG-IT]
Subject: question.

Assuming we have a tree like this

A
|_B
| |_H
|
|_C
| |_E
| |_F
|   |
|   |_G
|_ D
   |_I

We can represent that node and parent relationship as follow
q)t:([]n:`A`B`C`D`E`F`G`H`I;p:`A`A`A`A`C`C`F`B`D)
q)t
n p
---
A A
B A
C A
D A
E C
F C
G F
H B
I D

How do I find a path for example given a node `G

The path is `A`C`F`G   ?
