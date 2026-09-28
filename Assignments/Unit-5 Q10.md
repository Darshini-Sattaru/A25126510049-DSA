#include <stdio.h>
#define MAX 20
#define INF 9999

int cost[MAX][MAX];
int dist[MAX];
int visited[MAX];
int n;

/* returns the unvisited vertex with the smallest distance */
int minVertex()
{
    int i, min=INF, index=-1;

    for (i=0; i<n; i++)
    {
        if (visited[i]==0 && dist[i]<min)
        {
            min=dist[i];
            index=i;
        }
    }
    return index;
}

void dijkstra(int src)
{
    int i, count, u, v;

    for (i=0; i<n; i++)
    {
        dist[i]=INF;
        visited[i]=0;
    }
    dist[src]=0;

    for (count=0; count<n-1; count++)
    {
        u=minVertex();
        if (u==-1)      /* remaining vertices are unreachable */
            break;

        visited[u]=1;

        for (v=0; v<n; v++)
        {
            /* cost 0 means no road between u and v */
            if (visited[v]==0 && cost[u][v]!=0 &&
                dist[u]+cost[u][v]<dist[v])
            {
                dist[v]=dist[u]+cost[u][v];
            }
        }
    }
}

int main()
{
    int i, j, src;

    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter weighted adjacency matrix (0 = no road):\n");
    for (i=0; i<n; i++)
        for (j=0; j<n; j++)
            scanf("%d", &cost[i][j]);

    printf("Enter source vertex (0 to %d): ", n-1);
    scanf("%d", &src);

    if (src<0 || src>=n)
    {
        printf("Invalid source vertex!\n");
        return 0;
    }

    dijkstra(src);

    printf("\nShortest distance from vertex %d:\n", src);
    printf("Vertex\tDistance\n");
    for (i=0; i<n; i++)
    {
        if (dist[i]==INF)
            printf("%d\t%s\n", i, "Not reachable");
        else
            printf("%d\t%d\n", i, dist[i]);
    }

    return 0;
}
