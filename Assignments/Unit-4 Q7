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
    else
        printf("%d is duplicate, ignored\n",x);
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
void preorder(struct node *r)
{
    if(r!=NULL)
    {
        printf("%d ",r->data);
        preorder(r->left);
        preorder(r->right);
    }
}
void postorder(struct node *r)
{
    if(r!=NULL)
    {
        postorder(r->left);
        postorder(r->right);
        printf("%d ",r->data);
    }
}
int search(struct node *r,int key)
{
    while(r!=NULL)
    {
        if(key==r->data)
            return 1;
        else if(key<r->data)
            r=r->left;
        else
            r=r->right;
    }
    return 0;
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
    if(root==NULL)
    {
        printf("Tree is empty\n");
        return 0;
    }
    printf("Inorder: ");
    inorder(root);
    printf("\nPreorder: ");
    preorder(root);
    printf("\nPostorder: ");
    postorder(root);
    printf("\nEnter value to search:");
    scanf("%d",&key);
    if(search(root,key))
        printf("%d exists in the tree\n",key);
    else
        printf("%d does not exist in the tree\n",key);
    printf("Inorder is sorted: left < root < right at every node\n");
    return 0;
}




<img width="577" height="217" alt="Image" src="https://github.com/user-attachments/assets/dce4a2f3-19be-485b-8d6c-d53328271a99" />
<img width="580" height="241" alt="Image" src="https://github.com/user-attachments/assets/9ea6a097-b5d1-4283-9901-cdb7ec90ce7a" />
<img width="272" height="76" alt="Image" src="https://github.com/user-attachments/assets/901000e5-f610-4ecb-a896-33131140d8f1" />
