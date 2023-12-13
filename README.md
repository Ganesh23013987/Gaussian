# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### Step1:
Import necessary modules:    
import sys                  
import numpy as np
### Step2:
Take input for the size of the matrix n:        
n = int(input())
### Step3:
Initialize matrices and arrays:     
matrix = np.zeros((n, n+1))     
x = np.zeros(n)
### Step4:
Populate the augmented matrix with input values:                    
for i in range(n):   
  for j in range(n+1):    
        matrix[i][j] = int(input())
### Step5:
Check for divide by zero error and exit if necessary:     
for i in range(n):                       
    if matrix[i][i] == 0.0:           
        sys.exit("Divide by zero error")  
### Step6:
Perform Gaussian Elimination:   
for i in range(n):   
    for j in range(i+1, n):    
        ratio = matrix[j][i] / matrix[i][i]

        for k in range(n+1):
            matrix[j][k] = matrix[j][k] - ratio * matrix[i][k]       
### Step7:       
Perform Back Substitution:       
x[n-1] = matrix[n-1][n] / matrix[n-1][n-1]

for i in range(n-2, -1, -1):   
    x[i] = matrix[i][n]

    for j in range(i+1, n):
        x[i] = x[i] - matrix[i][j] * x[j]

    x[i] = x[i] / matrix[i][i]
### Step8:
Print the results:    
for i in range(n):   
    print("X%d = %0.2f" % (i, x[i]), end=" ")    
### Step9:
End program.    
## Program:
```
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:   Ganesh.D
RegisterNumber: 23013987

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
    print("X%d = %0.2f"%(i,x[i]),end=" ")
    

```

## Output:
![Alt text](gaussian.png)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

Then, the program is successully executed.

