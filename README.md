# Gaussian Elimination


## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. 
2. 
3. 
4. 
## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: praveen.v
RegisterNumber: 23013808
'''
import numpy as np
import sys
# Reading number of unknowns
n=int(input())
# Making numpy array of n x n+1 size and initializing
# to zero for storing augmented matrix
a=np.zeros((n,n+1))

# Making numnpy array of n size and initializing
# to zero for storing solution vector
x=np.zeros(n)
#Reading augmented matrix coefficients
for i in range(n):
    for j in range(n+1):
        a[i][j] =float(input())

for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('div by zero not found!')
    for j in range(i+1,n):
        scalar=a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k]= a[j][k]-scalar*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end = " ")
```
## Output:
![gaussian elimination]()


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

