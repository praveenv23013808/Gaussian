# Gaussian Elimination
EX 06 Gaussian Elimination
Date: 22.09.2023
## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.
## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm
1.Import the numpy module to use the built-in functions for calculation.

2.Import the sys module to use the built-in functions.

3.Get input from the user for number of rows and add it by 1 for number of columns.

4.Using np.zeros() set the matrix as null matrix.

5.Using nested for loop get input from the user for each element in the matrix.

6.Using nested for loop find the ratio and perform the elementary row operations and find the final matrix.

7.Use back substitution method to find the value of the variables and print it.

8.End the program.  
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
![Screenshot 2023-11-18 101851](https://github.com/praveenv23013808/Gaussian/assets/145824728/e5816fdd-e448-4a8a-bb76-f0fa0950b659)
## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.
