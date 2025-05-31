# Ex 1B Conversion of the infix expression into postfix expression
## DATE: 22/02/2025
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
1. Start the program.
2. Include the required libraries.
3. Define functions for push and pop operations to handle the stack and define a function to return the priority of the operators.
4. Construct the function to convert an infix expression into postfix following the logic. 
5. End the program.

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: Kurapati Vishnu Vardhan Reddy
RegisterNumber: 212223040103
*/

#include<stdio.h>
#include<ctype.h>

char stack[100];
int top = -1;

void push(char x)
{
   top++;
   stack[top]=x;
}

char pop()
{
    if(top==-1)
    return -1;
    else
    return stack[top--];
}
int priority(char x)
{
    if(x=='(')
    return 0;
    if(x=='&'||x=='|')
    return 1;
    if(x=='+'||x=='-')
    return 2;
    if(x=='*'||x=='/'||x=='%')
    return 3;
    if(x=='^')
    return 4;
    return 0;
}
char IntoPost(char *exp)
{
    char *e,x;
    e=exp;
    while(*e!='\0')
    {
        if(isalnum(*e))
        printf("%c ",*e);
        else if(*e=='(')
        push(*e);
        else if(*e==')')
        {
            while((x=pop())!='(')
            printf("%c ",x);
        }
        else
        {
            while(priority(*e)<=priority(stack[top]))
            printf("%c ",pop());
            push(*e);
        }
        e++;
    }
    
    while(top != -1)
    {
       printf("%c ",pop());
    }
    return 0;
}


int main()
{
    char exp[100]="4*(2+5)*9";
    IntoPost(exp);
    return 1;
}

```

## Output:

![image](https://github.com/user-attachments/assets/35572033-dc59-462a-bdb6-9f4eb1513e71)

## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
