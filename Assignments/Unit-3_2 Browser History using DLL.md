#include<stdio.h>
#include<stdlib.h>
#include<string.h>
struct node
{
    char page[50];
    struct node *prev,*next;
};
struct node *head=NULL,*cur=NULL;
int main()
{
    int ch;
    char p[50];
    struct node *newn,*temp;
    while(1)
    {
        printf("\n1.Visit 2.Back 3.Forward 4.Delete 5.Show forward 6.Show backward 7.Exit\nEnter your choice: ");
        scanf("%d",&ch);
        if(ch==1)
        {
            printf("Enter page name:");
            scanf("%s",p);
            newn=(struct node*)malloc(sizeof(struct node));
            strcpy(newn->page,p);
            newn->next=NULL;
            newn->prev=cur;
            if(head==NULL)
                head=newn;
            else
                cur->next=newn;
            cur=newn;
        }
        else if(ch==2)
        {
            if(cur==NULL || cur->prev==NULL)
                printf("No previous page\n");
            else
                cur=cur->prev;
        }
        else if(ch==3)
        {
            if(cur==NULL || cur->next==NULL)
                printf("No next page\n");
            else
                cur=cur->next;
        }
        else if(ch==4)
        {
            printf("Enter page to delete:");
            scanf("%s",p);
            temp=head;
            while(temp!=NULL && strcmp(temp->page,p)!=0)
                temp=temp->next;
            if(temp==NULL)
                printf("Not found\n");
            else
            {
                if(temp->prev!=NULL)
                    temp->prev->next=temp->next;
                else
                    head=temp->next;
                if(temp->next!=NULL)
                    temp->next->prev=temp->prev;
                if(cur==temp)
                {
                    if(temp->prev!=NULL)
                        cur=temp->prev;
                    else
                        cur=temp->next;
                }
                free(temp);
                printf("Deleted\n");
            }
        }
        else if(ch==5)
        {
            if(head==NULL)
                printf("History empty\n");
            else
            {
                temp=head;
                while(temp!=NULL)
                {
                    printf("%s ",temp->page);
                    temp=temp->next;
                }
                printf("\n");
            }
        }
        else if(ch==6)
        {
            if(head==NULL)
                printf("History empty\n");
            else
            {
                temp=head;
                while(temp->next!=NULL)
                    temp=temp->next;
                while(temp!=NULL)
                {
                    printf("%s ",temp->page);
                    temp=temp->prev;
                }
                printf("\n");
            }
        }
        else
            break;
    }
    return 0;
}




<img width="757" height="570" alt="Image" src="https://github.com/user-attachments/assets/d749e9fd-df5a-42f3-9d63-2e25d40047e5" />
<img width="765" height="537" alt="Image" src="https://github.com/user-attachments/assets/b6291a3e-43fb-4c92-9367-2310ed71a7fc" />
<img width="763" height="570" alt="Image" src="https://github.com/user-attachments/assets/c3d3af17-343e-4aaf-a9f4-76f141bd9231" />
<img width="771" height="602" alt="Image" src="https://github.com/user-attachments/assets/83ecd9dd-ec14-490c-8892-c7d3959371a8" />
<img width="767" height="155" alt="Image" src="https://github.com/user-attachments/assets/2b96786d-2859-4ff6-b8f9-fc2828d43d16" />


