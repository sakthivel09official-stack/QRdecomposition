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
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
def QR_Decomposition(A):
    
    
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,m))
    for j in range(n):
        v=A[:,j].copy()
        for i in range(j):
            R[i,j]=np.dot(Q[:,i].T,A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
A=np.array(eval(input()))
q,r=QR_Decomposition(A)
print('The Q Matrix is\n',q.round(8))
print('The R Matrix is\n',r.round(8)
```

## Output
<img width="1920" height="1080" alt="Screenshot 2026-05-31 172953" src="https://github.com/user-attachments/assets/ae4eeaaf-7047-4a5c-aa62-818067ad0736" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
