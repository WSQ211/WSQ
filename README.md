# Grover Algorithm Qiskit

>> A fast quantum mechanical algorithm for database search (Lov K. Grover)

<br/><br/><br/>
[Blog Address / 블로그주소](https://wsquantum.tistory.com/41)
<br/><br/><br/>
### example

<br/>

### Let S = 101001 s.t. want to search.

<br/>

![1](https://github.com/WSQ211/WSQ/assets/165191088/a37d29bd-405b-4b42-8d93-da4218ede404)

<br/>

![1-1](https://github.com/WSQ211/WSQ/assets/165191088/42e31273-100e-4df9-bfcb-4f651341e9cf)

<br/><br/><br/>

![2](https://github.com/WSQ211/WSQ/assets/165191088/78399ce8-3cdb-4a04-9b16-d3e6fead6b33)

<br/>

![2-1](https://github.com/WSQ211/WSQ/assets/165191088/5a0cb727-dd61-48a7-af43-efdb4d5ac707)

<br/><br/><br/>

![3](https://github.com/WSQ211/WSQ/assets/165191088/e6d1d597-c1ab-4337-8e6e-d47b85801256)
```
def RMatrix(num_bits):
    mat_R = np.zeros((2**num_bits, 2**num_bits))
    for i in range(2**num_bits):
        for j in range(2**num_bits):
            if i != j:
                mat_R[i][j] = 0
            else:
                if i == 0:
                    mat_R[i][j] = 1
                else:
                    mat_R[i][j] = -1
    return mat_R
```

<br/><br/><br/>

![4](https://github.com/WSQ211/WSQ/assets/165191088/51a364ae-3f66-44e1-851c-cbe8b7e3d923)
```
def WMatrix(num_bits):
    mat_W = np.zeros((2**num_bits, 2**num_bits))
    for i in range(2**num_bits):
        for j in range(2**num_bits):
            i_b = get_bin(i, num_bits)
            j_b = get_bin(j, num_bits)
            bitsum = 0
            for k in range(num_bits):
                if int(i_b[k])*int(j_b[k]) == 1:
                    bitsum += 1
            if bitsum % 2 == 0:
                mat_W[i][j] = 1
            else:
                mat_W[i][j] = -1
    return mat_W
```

<br/><br/><br/>

![5](https://github.com/WSQ211/WSQ/assets/165191088/f5bbc241-221d-491c-92ff-6f4f2d3e4542)
```
D = np.dot(np.dot(W,R), W) / 2**num_bits
```

<br/><br/><br/>

![6](https://github.com/WSQ211/WSQ/assets/165191088/33cef3ef-cf07-47ff-a9bf-2cf8d7ef1276)

<br/>

![6-1](https://github.com/WSQ211/WSQ/assets/165191088/6af42ae6-6ac4-400c-85c8-6cd311f9b539)

<br/>

### simulator
![6-2](https://github.com/WSQ211/WSQ/assets/165191088/2bef8a30-6363-4706-9ced-e13d7fb05bd5)

<br/>

### QiskitRuntimeService
![6-3](https://github.com/WSQ211/WSQ/assets/165191088/9a59876e-910d-4dfc-acd4-490263b6e5b6)
