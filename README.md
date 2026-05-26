# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Step 1: Import the NumPy library.

Step 2: Define the coefficient matrix A and constant matrix B.

Step 3: Form the augmented matrix [A∣B].

Step 4: Apply forward elimination to convert the matrix into upper triangular form.

Step 5: Apply back substitution to find the values of unknowns.

Step 6: Display the solution of the system of equations.

Step 7: Stop the program.git add -A

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:BHARGAVI S 
RegisterNumber:212225230033 
*/
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range (i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
            x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' % (i,x[i]) ,end=" ")
```

## Output:
<img width="1013" height="720" alt="image" src="https://github.com/user-attachments/assets/fdb29b85-fd86-4687-8828-90ff51dcfc5e" />
<img width="1007" height="392" alt="image" src="https://github.com/user-attachments/assets/e3e77de7-290e-4939-9323-9ab6cb04b401" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

