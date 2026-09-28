#include<stdio.h>
#include<ctype.h>
char stack[100];
int top=-1;
void push(char c){stack[++top]=c;}
char pop(){return stack[top--];}
int prec(char c)
{
    if(c=='^') return 3;
    if(c=='*'||c=='/') return 2;
    if(c=='+'||c=='-') return 1;
    return 0;
}
int main()
{
    char exp[100],res[100];
    int i=0,k=0;
    printf("Enter infix expression:");
    scanf("%s",exp);
    while(exp[i]!='\0')
    {
        char c=exp[i];
        if(isalnum(c))
            res[k++]=c;
        else if(c=='(')
            push(c);
        else if(c==')')
        {
            while(top!=-1 && stack[top]!='(')
                res[k++]=pop();
            pop();
        }
        else
        {
            while(top!=-1 && prec(stack[top])>=prec(c) && !(c=='^' && stack[top]=='^'))
                res[k++]=pop();
            push(c);
        }
        i++;
    }
    while(top!=-1)
        res[k++]=pop();
    res[k]='\0';
    printf("Postfix=%s\n",res);
    return 0;
}
