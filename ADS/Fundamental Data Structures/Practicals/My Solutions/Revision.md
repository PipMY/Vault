## 1. 

#### a) 

A stack is a data structure that applies the Last-in-first-out principle (LIFO) this means that whatever is the last element to be pushed to the stack will be the first to be popped and vice-versa. 

#### b) 

| Operation | Contents | Output |
| --------- | -------- | ------ |
| $push(5)$ | $5$      |        |
| $push(3)$ | $5,3$    |        |
| $pop()$   | $5$      | $3$    |
| $push(2)$ | $5,2$    |        |
| $push(8)$ | $5,2,8$  |        |
| $pop()$   | $5,2$    | $8$    |
| $pop()$   | $5$      | $2$    |
| $push(9)$ | $5,9$    |        |
| $push(1)$ | $5,9,1$  |        |
| $pop()$   | $5,9$    | 1      |
Therefore, the final contents of the stack would be {5,9}

#### c i) 

if $n=14$ 

| $n$  | Contents of Stack |
| ---- | ----------------- |
| $14$ | $0$               |
| 7    | $0,1$             |
| 3    | $0,1,1$           |
| 1    | $0,1,1,1$         |
| 0    |                   |
Therefore the code would print $1110$.

#### ii)

if the code outputs $10011$ then the stack must have held the contents: $1,1,0,0,1$, so what we are trying to do is find a number $n$ that is odd and when divided by 2 must be odd again and then even then even then finally odd. In order to find this value of $n$, we must also take into account that the code terminated with only 5 values in the stack this means that $2^5 > n \geq 2^4$ and $n$ must be $odd$. This leaves the options of $17,19,21,23,25,27,29,31$ upon inspection, it cannot be $17,21, 25, 29$ because when these undergo integer division by 2 they are even, meaning the next element couldn't be 1. This leaves $19,23, 27, 31$ if we test each answer we can see that it is $19$.

## 2.

#### a) 

| Operation    | Contents | Output |
| ------------ | -------- | ------ |
| $Enqueue(7)$ | $7$      |        |
| $Enqueue(9)$ | $7,9$    |        |
| $Dequeue()$  | $9$      | $7$    |
| $Enqueue(4)$ | $9,4$    |        |
| $Enqueue(2)$ | $9,4,2$  |        |
| $Dequeue()$  | $4,2$    | $9$    |
| $Dequeue()$  | $2$      | $4$    |
| $Enqueue(4)$ | $2,4$    |        |
Therefore, the final contents of the queue are $2,4$.

#### b) 

#### i)

| Operation | Contents  | Output                |
| --------- | --------- | --------------------- |
| push()    | $0$       |                       |
| push()    | 0,1       |                       |
| push()    | 0,1,2     |                       |
| pop()     | 0,1       | $2$                   |
| push()    | 0,1,3     |                       |
| push()    | 0,1,3,4   |                       |
| push()    | 0,1,3,4,5 |                       |
| pop()     | 0,1,3,4   | $2,5$                 |
| push()    | 0,1,3,4,6 |                       |
| pop()     | 0,1,3,4   | $2,5,6$               |
| push()    | 0,1,3,4,7 |                       |
| pop()     | 0,1,3,4   | $2,5,6,7$             |
| pop()     | 0,1,3     | $2,5,6,7,4$           |
| push()    | 0,1,3,8   |                       |
| pop()     | 0,1,3     | $2,5,6,7,4,8$         |
| push()    | 0,1,3,9   |                       |
| pop()     | 0,1,3     | $2,5,6,7,4,8,9$       |
| pop()     | 0,1       | $2,5,6,7,4,8,9,3$     |
| pop()     | 0         | $2,5,6,7,4,8,9,3,1$   |
| pop()     |           | $2,5,6,7,4,8,9,3,1,0$ |

#### ii)

| Operation  | Contents | Output |
| ---------- | -------- | ------ |
| push()     | 0        |        |
| push()     | 0,1      |        |
| pop()      | 0        | 1      |
| push()     | 0,2      |        |
| push()<br> | 0,2,3    |        |
| push()     | 0,2,3,4  |        |
| pop()      | 0,2,3    | 1,4    |


Here we can see it is not possible because the 2 needs to be popped but it cannot as it's hidden behind the 3.

## 3.

```
FUNCTION Loan(borrowed, interest_rate, repayment, monthsPassed):

    if monthsPassed = 1:

        return borrowed * (1 + interest_rate) - repayment

    else:

        return Loan(borrowed * (1 + interest_rate) - repayment, interest_rate, repayment, monthsPassed - 1)
        
END FUNCTION
```








