#include<stdio.h>
#include<stdlib.h>
struct node
{
    int data;
    struct node *left,*right;
};
struct node *insert(struct node *root,int x)
{
    if(root==NULL)
    {
        root=(struct node*)malloc(sizeof(struct node));
        root->data=x;
        root->left=root->right=NULL;
    }
    else if(x<root->data)
        root->left=insert(root->left,x);
    else if(x>root->data)
        root->right=insert(root->right,x);
    return root;
}
void inorder(struct node *r)
{
    if(r!=NULL)
    {
        inorder(r->left);
        printf("%d ",r->data);
        inorder(r->right);
    }
}
struct node *del(struct node *root,int key)
{
    struct node *temp,*p,*s;
    if(root==NULL)
    {
        printf("Value not found\n");
        return NULL;
    }
    if(key<root->data)
        root->left=del(root->left,key);
    else if(key>root->data)
        root->right=del(root->right,key);
    else
    {
        if(root->left==NULL && root->right==NULL)
        {
            printf("Case 1: node with zero children (leaf node)\n");
            free(root);
            return NULL;
        }
        else if(root->left==NULL)
        {
            printf("Case 2: node with one child (right child)\n");
            temp=root->right;
            free(root);
            return temp;
        }
        else if(root->right==NULL)
        {
            printf("Case 2: node with one child (left child)\n");
            temp=root->left;
            free(root);
            return temp;
        }
        else
        {
            printf("Case 3: node with two children \n");
            p=root;
            s=root->right;
            while(s->left!=NULL)
            {
                p=s;
                s=s->left;
            }
            root->data=s->data;
            if(p==root)
                p->right=s->right;
            else
                p->left=s->right;
            free(s);
        }
    }
    return root;
}
int main()
{
    struct node *root=NULL;
    int n,x,key;
    printf("Enter number of values:");
    scanf("%d",&n);
    printf("Enter %d values:\n",n);
    for(int i=0;i<n;i++)
    {
        scanf("%d",&x);
        root=insert(root,x);
    }
    while(1)
    {
        printf("\nEnter value to delete(-1 to stop):");
        scanf("%d",&key);
        if(key==-1)
            break;
        printf("Inorder before deletion: ");
        inorder(root);
        printf("\n");
        root=del(root,key);
        printf("Inorder after deletion: ");
        inorder(root);
        printf("\n");
    }
    return 0;
}




