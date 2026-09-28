#include<stdio.h>
#include<stdlib.h>
struct node
{
    int roll;
    struct node *next;
};
struct node *head=NULL;
int main()
{
    int ch,r;
    struct node *temp,*prev,*newn;
    while(1)
    {
        printf("\n1.Insert begin 2.Insert end 3.Search 4.Delete 5.Display 6.Exit\nEnter your choice:");
        scanf("%d",&ch);
        if(ch==1)
        {
            printf("Enter roll:");
            scanf("%d",&r);
            newn=(struct node*)malloc(sizeof(struct node));
            newn->roll=r;
            newn->next=head;
            head=newn;
        }
        else if(ch==2)
        {
            printf("Enter roll:");
            scanf("%d",&r);
            newn=(struct node*)malloc(sizeof(struct node));
            newn->roll=r;
            newn->next=NULL;
            if(head==NULL)
                head=newn;
            else
            {
                temp=head;
                while(temp->next!=NULL)
                    temp=temp->next;
                temp->next=newn;
            }
        }
        else if(ch==3)
        {
            printf("Enter roll to search:");
            scanf("%d",&r);
            temp=head;
            int found=0;
            while(temp!=NULL)
            {
                if(temp->roll==r)
                {
                    found=1;
                    break;
                }
                temp=temp->next;
            }
            if(found)
                printf("Found\n");
            else
                printf("Not found\n");
        }
        else if(ch==4)
        {
            printf("Enter roll to delete:");
            scanf("%d",&r);
            temp=head;
            prev=NULL;
            while(temp!=NULL && temp->roll!=r)
            {
                prev=temp;
                temp=temp->next;
            }
            if(temp==NULL)
                printf("Not available\n");
            else
            {
                if(prev==NULL)
                    head=temp->next;
                else
                    prev->next=temp->next;
                free(temp);
                printf("Deleted\n");
            }
        }
        else if(ch==5)
        {
            temp=head;
            while(temp!=NULL)
            {
                printf("%d ",temp->roll);
                temp=temp->next;
            }
            printf("\n");
        }
        else
            break;
    }
    return 0;
}



