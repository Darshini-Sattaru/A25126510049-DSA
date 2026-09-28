#include <stdio.h>
#define MAX 20

int adj[MAX][MAX];
int visited[MAX];
int queue[MAX];
int n;

void bfs(int start)
{
    int front=0, rear=0;
    int v, i;

    visited[start]=1;
    queue[rear++]=start;

    printf("Visit order: ");
    while (front<rear)
    {
        v=queue[front++];
        printf("%d ", v);

        for (i=0; i<n; i++)
        {
            /* go only to connected vertices that are not visited yet */
            if (adj[v][i]==1 && visited[i]==0)
            {
                visited[i]=1;
                queue[rear++]=i;
            }
        }
    }
    printf("\n");
}

int main()
{
    int i, j, start, count=0;

    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter adjacency matrix (%d x %d):\n", n, n);
    for (i=0; i<n; i++)
        for (j=0; j<n; j++)
            scanf("%d", &adj[i][j]);

    printf("Enter starting vertex (0 to %d): ", n-1);
    scanf("%d", &start);

    if (start<0 || start>=n)
    {
        printf("Invalid starting vertex!\n");
        return 0;
    }

    bfs(start);

    /* check whether any vertex was left out */
    for (i=0; i<n; i++)
    {
        if (visited[i]==0)
        {
            if (count==0)
                printf("Vertices not reachable from %d: ", start);
            printf("%d ", i);
            count++;
        }
    }

    if (count==0)
        printf("Graph is connected. All vertices visited.\n");
    else
        printf("\nGraph is NOT connected (partially connected).\n");

    return 0;
}
