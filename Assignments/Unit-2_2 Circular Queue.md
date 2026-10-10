#include<stdio.h>
#define SIZE 5
int q[SIZE],front=-1,rear=-1;
int main()
{
    int ch,val;
    while(1)
    {
        printf("\n1.Insert 2.Delete 3.Display 4.Exit\nEnter your choice:");
        scanf("%d",&ch);
        if(ch==1)
        {
            if((rear+1)%SIZE==front)
                printf("Queue full\n");
            else
            {
                printf("Enter value:");
                scanf("%d",&val);
                if(front==-1)
                    front=0;
                rear=(rear+1)%SIZE;
                q[rear]=val;
                printf("Inserted\n");
            }
        }
        else if(ch==2)
        {
            if(front==-1)
                printf("Queue empty\n");
            else
            {
                printf("Deleted %d\n",q[front]);
                if(front==rear)
                    front=rear=-1;
                else
                    front=(front+1)%SIZE;
            }
        }
        else if(ch==3)
        {
            if(front==-1)
                printf("Queue empty\n");
            else
            {
                int i=front;
                while(1)
                {
                    printf("%d ",q[i]);
                    if(i==rear) break;
                    i=(i+1)%SIZE;
                }
                printf("\n");
            }
        }
        else
            break;
    }
    return 0;
}



<img width="1076" height="2025" alt="Image" src="https://github.com/user-attachments/assets/9d0b2443-e926-4afe-8dff-a05291842a79" />
