# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
1.Input: Read the number of equations (n) from the user. Create a matrix (a) of size (n x n+1) to store the coefficients and constants of the equations.
Fill the matrix (a) with the values entered by the user.
2.Iterate through each row (i) of the matrix (a): 
Check for division by zero: If a[i][i] is 0, exit with an error message. 
For each row (j) below the current row (i)
: Calculate a ratio: ratio = a[j][i] / a[i][i]
Subtract a multiple of row (i) from row (j) to make a[j][i] zero: 
a[j][k] = a[j][k] - ratio * a[i][k] for all columns (k)
3.Directly calculate the last unknown (x[n-1]): x[n-1] = a[n-1][n] / a[n-1][n-1]
Iterate backward from the second-to-last row (i = n-2) to the first row:
Initialize x[i] with the value in the last column of that row:
x[i] = a[i][n] For each row (j) below the current row (i):
Subtract the product of a[i][j] and x[j] from x[i]: x[i] = x[i] - a[i][j] * x[j]
Divide x[i] by the diagonal element to get the final value: x[i] = x[i] / a[i][i]
4.Print the values of the unknowns (x) in the specified format.
```
## Program:
```
Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: akash m
RegisterNumber:212223240003 

import sys
import numpy as np
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        matrix[i][j]=int(input())
for i in range(n):
    if matrix[i][i]==0.0:
        sys.exit("Divide by zero error")
    for j in range(i+1,n):
            ratio=matrix[j][i]/matrix[i][i]
            for k in range(n+1):
                matrix[j][k]=matrix[j][k]-ratio*matrix[i][k]
x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-matrix[i][j]*x[j]
        x[i]=x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]),end=" ")
```

## Output:
![image](https://github.com/akashmano/Gaussian/assets/137408306/92b68865-d3d6-4826-b0fc-de096c94b8b4)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

