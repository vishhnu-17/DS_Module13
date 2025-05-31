# Ex 1C Implementation of Tower of Hanoi
## DATE: 24/02/2025
## AIM:
To write a C program to implement Tower of Hanoi

## Algorithm
1. Start the program.
2. Include the required libraries.
3. Define a recursive function to handle the tower of hanoi problem.
4. Call the defined function in the main function and print the moves.
5. End the program.

## Program:
```
/*
Program to implement Tower of Hanoi
Developed by: Kurapati Vishnu Vardhan Reddy
RegisterNumber: 212223040103
*/

#include<stdio.h>
void TOH(int n,char x,char y,char z)
{
    if(n==1)
    {
        printf("%c to %c\n",x,y);
        return;
    }
    TOH(n-1,x,z,y);
    printf("%c to %c\n",x,y);
    TOH(n-1,z,y,x);
    
}
int main()
{
   int n=4;
   TOH(n,'A','B','C');
}
```

## Output:

![image](https://github.com/user-attachments/assets/66cc3a23-c072-4750-b207-6c8182ad3401)

## Result:
Thus, the C program to implement Tower of Hanoi using recursion is implemented successfully.
