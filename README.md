# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Forward Elimination (Pivot Selection & Scaling)
2. Row Reduction
3. Back Substitution
4. Solution Extraction

## Program:
```python
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:ALLEN PRAKASH J 
RegisterNumber:212225040017 
*/
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
        sys.exit("Divide by zero detected")
    for j in range(1+i,n):
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
    print('X%d = %0.2f'%(i,x[i]),end=" ")
        
```

## Output:


<img width="1269" height="590" alt="Screenshot 2026-02-24 221203" src="https://github.com/user-attachments/assets/5a273874-7aea-4a32-b14c-f157b1a507d5" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

