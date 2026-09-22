#include<stdio.h>
int main()
{
    int n,i,j,key,shift=0;
    printf("Enter number of marks:");
    scanf("%d",&n);
    int a[n];
    printf("Enter marks:\n");
    for(i=0;i<n;i++)
        scanf("%d",&a[i]);

    for(i=1;i<n;i++)
    {
        key=a[i];
        j=i-1;
        while(j>=0 && a[j]>key)
        {
            a[j+1]=a[j];
            j--;
            shift++;
        }
        a[j+1]=key;
        printf("Pass %d: ",i);
        for(int k=0;k<n;k++)
            printf("%d ",a[k]);
        printf("\n");
    }
    printf("Sorted array: ");
    for(i=0;i<n;i++)
        printf("%d ",a[i]);
    printf("\nTotal shifts=%d\n",shift);
    return 0;
}


<img width="1079" height="809" alt="Image" src="https://github.com/user-attachments/assets/a70a230b-a7b2-43b6-8054-a52113f7e048" />
