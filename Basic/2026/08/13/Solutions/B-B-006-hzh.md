#include<stdio.h>
int main()
{
	int n,t,i;
	int flag[1001]={0};
	int cnt=0;
	scanf("%d",&n);
	for(int i=1;i<=n;i++);
	{
		scanf("%d",&t);
		flag[t]=1;
	}
	for(int i=1;i<=1000;i++)
	{
		if(flag[i])cnt++;
	}
	printf("%d\n",cnt);
	for(i=1;i<=1000;i++)
	{
		if(flag[i])
		{
			printf("%d",i);
		}
	}
	return 0;
}
