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




<img width="1080" height="600" alt="Image" src="https://github.com/user-attachments/assets/8140cf9c-36e4-4636-a73b-1181addfea5f" />
<img width="4320" height="2304" alt="Image" src="https://github.com/user-attachments/assets/e76eabff-aadf-404c-9e58-28e5b4535403" />
<img width="4320" height="2260" alt="Image" src="https://github.com/user-attachments/assets/fd05831d-d95c-4b2e-b5fc-375e3b2cde0e" />
