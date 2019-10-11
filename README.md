# SLL-creation-
How can be create a single linked list in C  and insert an element at the the beginning of SLL


#include<stdio.h>
#include<stdlib.h>
struct node
{
int data;
struct node *Link;
}*head;
void createList(int n);
void insertnodeAtBeginning(int data);
void displayList();
int main()
{
int n,data;
printf("enter the total number of nodes:");
scanf("%d",&n);
createList(n);
printf("\n The list is:\n");
displayList();
printf("\n enter data to insert at beginning of the list");
scanf("%d",&data);
insertnodeAtBeginning(data);
printf("\n data inthe list\n");
displayList();
return 0;
}
void createList(int n)
{
struct node *newnode,*ptr;
int data,i;
head=(struct node*)malloc(sizeof(struct node));
if(head==NULL)
{
printf("unable to allocate memory");
}
else
{
printf("enter the data of node 1:");
scanf("%d",&data);
head->data=data;
head->Link=NULL;
ptr=head;
for(i=2;i<=n;i++)
{
newnode=(struct node*)malloc(sizeof(struct node));
if(newnode==NULL)
{
printf("unable to allocate memory");
break;
}
else
{
printf("enter the data of node %d:",i);
scanf("%d",&data);
newnode->data=data;
newnode->Link=NULL;
ptr->Link=newnode;
ptr=ptr->Link;
}
}
printf("singly linked list created successfully\n");
}
}
void insertnodeAtBeginning(int data)
{
struct node *newnode;
newnode=(struct node*)malloc(sizeof(struct node));
if(newnode==NULL)
{
printf("unable to allocate memory");
}
else
{
newnode->data=data;
newnode->Link=head;
head=newnode;
printf("data inserted successfully\n");
}
}
void displayList()
{
struct node *ptr;
if(head==NULL)
{
printf("list is empty");
}
else
{
ptr=head;
while(ptr!=NULL)
{
printf("%d----->",ptr->data);
ptr=ptr->Link;
}
}
}
