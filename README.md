# Norm of a matrix
## Aim
To write a program to find the 1-norm, 2-norm and infinity norm of the matrix and display the result in two decimal places.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
	1. Get the input matrix using np.array()   
    2. Find the 2-norm of the matrix using np.linalg.norm()
	3. Print the norm of the matrix in two decimal places.
## Program:
```
# 1-Norm of a Matrix

A = eval(input())

rows = len(A)
cols = len(A[0])

max_sum = 0

for j in range(cols):
    col_sum = 0
    for i in range(rows):
        col_sum += abs(A[i][j])
    if col_sum > max_sum:
        max_sum = col_sum

print("{:.2f}".format(max_sum))


# 2-Norm of a Matrix

A = eval(input())

m = len(A)
n = len(A[0])

ATA = [[0]*n for _ in range(n)]

for i in range(n):
    for j in range(n):
        s = 0
        for k in range(m):
            s += A[k][i] * A[k][j]
        ATA[i][j] = s

x = [1]*n

for _ in range(25):
    y = [0]*n
    for i in range(n):
        for j in range(n):
            y[i] += ATA[i][j] * x[j]
    norm = (sum(v*v for v in y))**0.5
    x = [v/norm for v in y]

num = 0
den = 0
for i in range(n):
    t = sum(ATA[i][j]*x[j] for j in range(n))
    num += x[i]*t
    den += x[i]*x[i]

lmax = num/den

print("{:.2f}".format(lmax**0.5))


# Infinity Norm of a Matrix

A = eval(input())

max_sum = 0

for row in A:
    s = 0
    for v in row:
        s += abs(v)
    if s > max_sum:
        max_sum = s

print("{:.2f}".format(max_sum))



```
## Output:
### 1-Norm of a Matrix
<br>
<br>
<br>
<img width="1232" height="252" alt="image" src="https://github.com/user-attachments/assets/ca4180b5-3d81-4b9d-bc34-d1f93e752fa7" />

### 2-Norm of a Matrix
<br>
<br>
<br>
<img width="1236" height="291" alt="image" src="https://github.com/user-attachments/assets/daa9338f-7826-4aeb-8670-4c73291a98f6" />

### Infinity Norm of a Matrix
<br>
<br>
<br>
<img width="1232" height="245" alt="image" src="https://github.com/user-attachments/assets/20ad3c5c-47d8-49f0-b529-da842b47dc24" />

## Result
Thus the program for 1-norm, 2-norm and Infinity norm of a matrix are written and verified.
