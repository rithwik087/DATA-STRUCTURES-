# DATA-STRUCTURES-
# LINKED LISTS 
#include<stdio.h>
#include<stdlib.h>

int data;
typedef struct node{
    int data;
    struct node *next;
} Node;

Node *initaliselinkedlist();
Node *createnode(int data);
Node *insertbegin(Node *head,int data);
void printlinkedlist(Node *head);
Node *insertend(Node *head,int data);
Node *deletenode(Node *head,int pos);
Node *insertatpos(Node *head,int data,int position);
int findlength(Node *head);
int getnth(Node *head,int position);
int countoccurenceof(Node *head,int data);
Node *returnprevnode(Node *head,Node *present);
Node *returnnextnode(Node *head,Node *present);
void reverselinkedlist(Node *head);
void reverselinkedlistrec(Node *head);
void bubblesort(Node*head);
Node *splitgivenlist(Node *head);
Node *appendList(Node *head1,Node *head2);
Node *sortedmerge(Node *a,Node *b);
Node *alternatemerge(Node *p,Node **q);
void print_nth_last_element(Node *head,int n);



int main()
{  
    int ch=-1;
    Node *present;
    int position;
   
    Node *head=NULL;
   
    push(&head,10);
    push(&head,15);
    push(&head,20);
    push(&head,25);
    push(&head,30);
    push(&head,35);
    push(&head,40);
    push(&head,45);
    push(&head,50);
    push(&head,20);
   
    Node *head1=NULL;
    Node *head2=NULL;
   
    push(&head1,100);
    push(&head1,200);
    push(&head1,300);
   
    push(&head2,500);
    push(&head2,600);
    push(&head2,700);
    push(&head2,800);
   
   
   
    printf("\n 0:print linked list");
    printf("\n 1:insert at begining");
    printf("\n 2:insert at the end");
    printf("\n 3:to delete a node");
    printf("\n 4:insert at a position");
    printf("\n 5:to find a length of the linked list");
    printf("\n 6:to get nth node of the linked list");
    printf("\n 7:to count the occurence of a node in linked list");
    printf("\n 8:to return to previous node of present node in the  linked list");
    printf("\n 9:to return to next node of present node in the linked list");
    printf("\n 10:to reverse a linked list");
    printf("\n 11:to reverse a linked list recursively");
    printf("\n 12:to sort the linked list using bubble sort");
    printf("\n 13:to split the given linked list");
    printf("\n 14:to append a list to another list");
    printf("\n 15:to merge two given lists in a sorted manner");
    printf("\n 16:to merge two given lists in alternate manner");
    printf("\n 17:to print nth last element");
    printf("\n 99:No choice selected");
   
   
    while(ch!=99)
    {
        printf("enter your choice");
        scanf("%d" ,&ch);
        switch(ch)
        {
        case 0:
        printlinkedlist(head);
        break;
       
        case 1:
        printf("the given linked list\n");
        printlinkedlist(head);
        printf("enter the data need to be inserted at begining\n");
        scanf("%d",&data);
        head=insertbegin(head,data);
        printf("the modified linked list is\n");
        printlinkedlist(head);
        break;
       
        case 2:
        printf("the given linked list\n");
        printlinkedlist(head);
        printf("enter the data need to be inserted at end\n");
        scanf("%d",&data);
        head=insertend(head,data);
        printf("the modified linked list\n");
        printlinkedlist(head);
        break;
       
        case 3:
        printf("the given linked list\n");
        printlinkedlist(head);
        printf("enter the position or data needs to be deleted as a node\n");
        scanf("%d",&position);
        head=deletenode(head,position);
        printf("the modified linked list\n");
        printlinkedlist(head);
        break;
       
        case 4:
        printf("the given linked list\n");
        printlinkedlist(head);
        printf("enter the position or data after which new charecter as to be inserted\n");
        scanf("%d",&position);
        printf("enter the data need to be inserted\n");
        scanf("%d",&data);
        head=insertatpos(head,data,position);
        printf("the modified linked list\n");
        printlinkedlist(head);
        break;
       
        case 5:
        printf("the given linked list\n");
        printlinkedlist(head);
       
        int k=findlength(head);
        printf("the length of the linked list is %d",k);
        break;
       
        case 6:
        printf("the given linked list\n");
        printlinkedlist(head);
        printf("enter the data or the position to be got as a node\n");
        scanf("%d",&data);
       
       
        int data=getnth(head,position);
        printf("hence the data got out is %d ",data);
        break;
       
        case 7:
        printf("the given linked list\n");
        printlinkedlist(head);
        printf("enter the data or position that need to be count of occurence\n");
        scanf("%d",&data);
        int c=countoccurenceof(head,data);
        printf("the count occured is %d",c);
        break;
       
        case 8:
        printf("the given linked list\n");
        printlinkedlist(head);
        printf("enter the data or position of which previous node has to be returned\n");
        scanf("%d",&data);
    present = createnode(data);
//        present =  &data;
        Node *previous_node=returnprevnode(head,present);
        printf("the node returned is %d",previous_node->data);
        break;
       
        case 9:
        printf("the given linked list\n");
        printlinkedlist(head);
        printf("enter the data or position of which next node has to be returned\n");
        scanf("%d",&data);
        present= createnode(data);
        Node *next_node=returnnextnode(head,present);
        printf("the node returned is %d",next_node->data);
        break;
       
        case 10:
        printf("the given linked list\n");
        printlinkedlist(head);
        reverselinkedlist(head);
        printf("the modified linked list\n");
        printlinkedlist(head);
        break;
       
        case 11:
        printf("the given linked list\n");
        printlinkedlist(head);
        reverselinkedlistrec(head);
        printf("the modified linked list\n");
        printlinkedlist(head);
        break;
       
       
        case 12:
        printf("the given linked list\n");
        printlinkedlist(head);
        bubblesort(head);
        printf("the modified linked list\n");
        printlinkedlist(head);
        break;
       
       
        case 13:
        printf("the given linked list\n");
        printlinkedlist(head);
        head=splitgivenlist(head);
        printf("the modified linked list\n");
        printlinkedlist(head);
        break;
       
        case 14:
        printf("the first linked list is \n");
        printlinkedlist(head1);
        printf("the second linked list is \n");
        printlinkedlist(head2);
        head1=appendList(head1,head2);
        printf("the linked list after appending\n");
        printlinkedlist(head1);
        break;
       
        case 15:
        printf("the first linked list is \n");
        printlinkedlist(head1);
        printf("the second linked list is \n");
        printlinkedlist(head2);
        head = sortedmerge(head1,head2);
        printf("the linked list after merging is\n");
        printlinkedlist(head);
        break;
       
        case 16:
        printf("the first linked list is \n");
        printlinkedlist(head1);
        printf("the second linked list is \n");
        printlinkedlist(head2);
        head=alternatemerge(head1,&head2);
        printf("the linked list after merging alternatively is\n");
        printlinkedlist(head);
        break;
       
        case 17:
        printf("the given linked list\n");
        printlinkedlist(head);
        int n=findlength(head);
        print_nth_last_element(head,n);
        break;
       
        default:
        printf("wrong choice or choose again\n");
        }
    }    
}        
       

Node * createnode(int data)
{

    Node *p;
    p=(Node*)malloc(sizeof(Node));
    p->data=data;
    p->next=NULL;
    return(p);
}

Node * insertbegin(Node * head,int data)
{
    Node *p;
    p =createnode(data);
   
    if(head=NULL)
    head=p;
    else
    {
        p->next=head;
        head=p;
    }
    return(head);
}
   
Node *insertend(Node *head,int data)
{
    Node *p,*current;
    p=createnode(data);
    current=head;
    if(current=NULL)
    {
        current=p;
    }
    else
    {
        while(current->next!=NULL)
        {
            current=current->next;
        }
        current->next=p;
        p->next=NULL;
    }
    return(head);
}

Node *deletenode(Node *head,int position)
{
    Node *temp=head,*prev;
    if(temp!=NULL && temp->data==position)
    {
    head=temp->next;
    free(temp);
    return(head);
    }
    else
    {
        while(temp!=NULL && temp->data!=position)
        {
            prev=temp;
            temp=temp->next;
        }
        if(temp!=NULL) return;
        prev->next=temp->next;
        free(temp);
        return(head);
       
    }
   
   
}

Node *insertatpos(Node *head,int data,int position)
{
    Node *p;
    p=createnode(data);
    Node *temp=head,*prev;
    while(temp->data!=position)
    {
        temp=temp->next;
    }
    p->next=temp->next;
    temp->next=p;
   
    return(head);
}

int findlength(Node *head)
{
    int count;
    count=0;
    Node *temp=head;
    if(head=NULL)
    return(count);
    else
    {
    while(temp!=NULL)
    {
        temp=temp->next;
        count++;
    }
    return(count);
    }
}

int getnth(Node *head, int position)
{
    Node *temp=head;
   
    if(head=NULL)
    {
        return;
    }
    else
    {
        while(temp->data!=position)
        {
            temp=temp->next;
        }
    }
    return(temp->data);
}

int countoccurenceof(Node *head,int data)
{
    int count;
    count=0;
    Node *temp=head;
    if(temp=NULL)
    {
       return;
    }
    else
    {
        while(temp->next!=NULL)
        {
            if(temp->data=data)
            count++;
            temp=temp->next;
        }
    }
    return(count);
}

Node *returnprevnode(Node *head,Node *present)
{
    Node *temp=head,*prev;
    if(head=NULL)
    {
        return;
    }
    else
    {
        while(temp->data!=present->data)
        {
            if(temp->next=NULL)
            return;
            else
            {
                prev=temp;
                temp=temp->next;
            }    
        }
    }
    return(prev);
}

Node *returnnextnode(Node *head,Node *present)
{
    Node *temp=head,*q;
    if(head=NULL)
    {
        return;
    }
    else
    {
        while(temp->data!=present->data)
        {
            if(temp->next=NULL)
            {
              return;
            }
            else
            {
                temp=temp->next;
            }
        }
    q=temp->next;    
    return q;    
       
    }
}
   
void reverselinkedlist(Node *head)    
{
    Node *prev=NULL;
    Node *curr=head;
    Node *next=NULL;

    if(head=NULL)
    return;
    else
    {
       while(curr!=NULL)
       {
           next=curr->next;
           curr->next=prev;
           prev=curr;
           curr=next;
       }
    head=prev;  
    }
}
   
   
void reverselinkedlistrec(Node *head)
{
    Node *p;
    if(p->next == NULL)
    {
 
        head = p;
        return;
    }
 
    reverselinkedlist(p->next);
 
    struct node* rev = p->next;
    rev->next = p;
    p->next = NULL;
}
   
void bubblesort(Node *head)  
{
    void swap(Node *a,Node *b)
    {
          int temp = a->data;
    a->data = b->data;
    b->data = temp;

    }
    int swapped, i;
    Node *ptr1;
    Node *lptr = NULL;
 

    if (head == NULL)
        return;
 
    do
    {
        swapped = 0;
        ptr1 = head;
 
        while (ptr1->next != lptr)
        {
            if (ptr1->data > ptr1->next->data)
            {  
                swap(ptr1, ptr1->next);
                swapped = 1;
            }
            ptr1 = ptr1->next;
        }
        lptr = ptr1;
    }
    while (swapped);
}


Node *splitgivenlist(Node *head)
{
    int num;
    num=0;
    Node *temp=head,*prev;
    int count;
    count=0;
    if(head=NULL)
    {
        return;
    }
    else
    {
        while(temp!=NULL)
        {
            temp=temp->next;
            count++;
        }
    }
    while(num<=count/2)
    {
        temp=head;
        prev=temp;
        temp=temp->next;
        num++;
    }
    temp=prev->next;
    prev->next=NULL;
    return(head);
}
   
Node* appendList(Node *head1, Node *head2)
{
Node *p;
p=head1;

while(p->next!=NULL)
{
p=p->next;
}
p->next=head2;
return(head1);
}

Node *sortedmerge(Node *a,Node *b)
{
  Node* result = NULL;
 
 
  if (a == NULL)  
     return(b);
  else if (b==NULL)  
     return(a);
 
 
  if (a->data <= b->data)  
  {
     result = a;
     result->next = sortedmerge(a->next, b);
  }
  else
  {
     result = b;
     result->next = sortedmerge(a, b->next);
  }
  return(result);
}

Node *alternatemerge(Node *p, Node **q)
{
     Node *p_curr = p, *q_curr = *q;
     Node *p_next, *q_next;
  Node * temp;
   
     while (p_curr != NULL && q_curr != NULL)
     {
         
         p_next = p_curr->next;
         q_next = q_curr->next;
 
   
         q_curr->next = p_next;  
         p_curr->next = q_curr;  
 
         
         p_curr = p_next;
         q_curr = q_next;
    }
 
    *q = q_curr;
    temp = appendList(p,*q);
    return(temp);
   
}

void print_nth_last_element(Node *head,int n)
{
    Node * p;
Node * current;
int i;
p=head;
current=head;
if(head->next==NULL && n==0){
printf("%c",head->data);

}
else if(head->next==NULL && n!=0){
printf("Error");
}
else{
for(i=0;i<n;i++){
p=p->next;
}
while(p->next!=NULL){
p=p->next;
current=current->next;
}
}
printf("%c",current->data);
}


void printlinkedlist(Node *head)
{
    Node *temp = head;
    printf("\n");
    while (temp!=NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

void push(Node **head,int data)
{
    Node* new_node = (Node*)malloc(sizeof(Node));
    new_node->data = data;
    new_node->next = (*head);
    (*head) = new_node;
}




