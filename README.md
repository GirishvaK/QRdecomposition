# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
<img width="263" height="97" alt="ex4" src="https://github.com/user-attachments/assets/28f94db7-c035-4188-9ab9-464677fea604" />
<img width="82" height="52" alt="ex6" src="https://github.com/user-attachments/assets/f898915c-461b-4dd0-843a-cc3c345cef08" />
<img width="90" height="56" alt="ex3" src="https://github.com/user-attachments/assets/7ecc651c-02cf-4ebf-adf5-79b8c4deff4b" />

3.	Obtain the Q matrix   
    <img width="181" height="37" alt="ex1" src="https://github.com/user-attachments/assets/e79fc415-b948-4c84-9db4-102a4ef9a2d4" />

4.	Construct the upper triangular matrix R
   <img width="232" height="80" alt="ex2" src="https://github.com/user-attachments/assets/e33816e5-f1f3-4c8a-9bd2-a23d7461873a" />




## Program:
### Gram-Schmidt Method
```
'''
Program to QR decomposition using the Gram-Schmidt method
Developed by: Girishva.K
RegisterNumber: 212225040094
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
def QR_Decomposition(a):
    # Write your code 
    a=np.array(a,dtype=float)
    m,n=a.shape
    q=np.zeros((m,n))
    r=np.zeros((n,n))
    for j in range(n):
        v=a[:,j]
        for i in range(j):
            r[i,j]=np.dot(q[:,i],a[:,j])
            v=v-r[i,j]*q[:,i]
        r[j,j]=np.linalg.norm(v)
        q[:,j]=v/r[j,j]
    return q,r
a = np.array(eval(input()))
q,r=QR_Decomposition(a)
print("The Q Matrix is\n",q)
print("The R Matrix is\n",r)






```

## Output
```
<img width="1327" height="565" alt="image" src="https://github.com/user-attachments/assets/2484afd6-9a78-474e-9176-fec45350bac0" />


```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
