# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Eswar S
RegisterNumber: 25017992
'''
import numpy as np
def QR_Decomposition(A):
    A=np.array(A,dtype=float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,m))
    
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
a = np.array(eval(input()))
Q,R=QR_Decomposition(a)
print("The Q Matrix is\n",Q)
print("The R Matrix is\n",R)
```

## Output
```
<img width="837" height="825" alt="Screenshot 2025-11-27 104453" src="https://github.com/user-attachments/assets/6267d237-e68d-470d-8f87-6f7d0abf1815" />
```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
