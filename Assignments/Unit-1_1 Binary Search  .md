#include<stdio.h>
int main()
{
    int n,key,low,high,mid,count=0,pos=-1;
    printf("Enter number of employees:");
    scanf("%d",&n);
    int arr[n];
    printf("Enter %d ids in ascending order:\n",n);
    for(int i=0;i<n;i++)
        scanf("%d",&arr[i]);
    printf("Enter id to search:");
    scanf("%d",&key);
    low=0;
    high=n-1;
    while(low<=high)
    {
        mid=(low+high)/2;
        count++;
        if(arr[mid]==key)
        {
            pos=mid;
            break;
        }
        else if(arr[mid]<key)
            low=mid+1;
        else
            high=mid-1;
    }
    if(pos!=-1)
        printf("Found at position %d\n",pos+1);
    else
        printf("Not found\n");
    printf("Comparisons=%d\n",count);
    return 0;
}




<img width="4320" height="2260" alt="Image" src="https://github.com/user-attachments/assets/e80efcf2-9220-4b83-928c-7280d309ab72" />
<img width="4320" height="2304" alt="Image" src="https://github.com/user-attachments/assets/7133d6d6-8898-44e6-a103-aa0bdc2c5164" />
<img width="1080" height="600" alt="Image" src="https://github.com/user-attachments/assets/e445bcb6-d373-4e42-9036-542c8153e755" />
