#include<stdio.h>
#include<stdlib.h>
struct sllnode
{
    int val;
    struct sllnode*next;
};
struct sllnode*createnode(int v)
{
    struct sllnode*nn;
    nn=(struct sllnode*)malloc(sizeof(struct sllnode));
    nn->val=v;
    nn->next=NULL;
    return nn;
}
struct sllode*createlist(int n)
{
    int i,v;
    struct sllnode*head=NULL,*newn,*temp;
    
    for(i=0;i<n;i++)
    {
        printf("%dth node element:",i);
        scanf("%d",&v);
        newn=createnode(v);
        if(head==NULL)
            head=newn;
        else
            temp->next=newn;
        temp=newn;
    }
    return head;
}
void printlist(struct sllnode*h)
{
    //struct sllnode*h
    while(h!=NULL)
    {
        printf("%d->",h->val);
        h=h->next;
    }
}
struct sllnode*insertatendining(struct sllnode*h,struct sllnode*t)
{
    struct sllnode*temp=h;
    while(temp->next!=NULL)
    {
        temp=temp->next;
    }
    temp->next=t;
    return h;
}
int main()
{
    int n;
    struct sllnode*h,*t;
    printf("enter n elements:");
    scanf("%d",&n);
    h=createlist(n);
    t=createnode(21);
    h=insertatendining(h,t);
    printlist(h);
}
