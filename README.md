# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm:
1. Import the module numpy and sys to use the build-in functions for calcution
2. Get the size of the martix(order) from the user and initialize an empty matrix and vector 
3. Using for loop get elements of the matrix and vector from the user.
4. Using another for loop to take each element in the matrix and solve in row echoloen form 
5. Perform back subsitution and print the values with two decimal places
6. End the program


## Program:
```python
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: R SUDHIR KUMAR
RegisterNumber: 23000604
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('divide by zeros detected !')
    for j in range(i+1,n):
        rao=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k] - rao * a[i][k]
x[n-1]= a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```

## Output:
![gaussian elimination](scr5.png)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

