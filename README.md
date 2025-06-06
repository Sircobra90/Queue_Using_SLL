
 
  //W.A.P to implement Queue using LL (SLL)
  
  #include<stdio.h>
  #include<stdlib.h> //malloc() & free() are declared
 
  struct Queue //Use Singly Linked List
  {
 	int data;
 	struct Queue *next; 	
  };
 
 //changes will be in both first time and then in rear everytime 
 void insertq(struct Queue **pf,struct Queue **pr,int x);
 //changes always there in front but when last node of queue removed rear will change to null
 int removeq(struct Queue **pf,struct Queue **pr); 
 void display(struct Queue *p);
 
 int main()
 {
 	struct Queue *front,*rear;
 	front=rear=NULL; //Initially both will have NULL
 	
 	int x; //user accepted value is stored or value to be removed
 	int option;
	char choice;	
	
	do
	{
        printf("Enter the option from following 1.Insert 2.Remove 3.Display Queue \n");
		printf("Enter your option ");
		scanf("%d",&option);
		
		switch(option)
		{
					
			case 1 :
				     	printf("Enter a number to be inserted ");
		                scanf("%d",&x); //Assume as of now user wont enter 0 as a value 
		                insertq(&front,&rear,x);
				        break;
			case 2 :
				        x=removeq(&front,&rear);
	                    if(x!=0) //Major Correction** Assuming as of now user will not enter 0
	                      printf("Deleted Element is %d\n",x);
				        break;	
			case 3 :
				        display(front);
				        break;		
				     
			default :
				     printf("Invalid Choice");
		}//end of switch
		
		fflush(stdin);  //To flush the stdin (input) buffer
		printf("Do you want to continue (y/n) ");
		scanf("%c",&choice);
	}while(choice=='y'||choice=='Y');
	
	printf("Thank You");
}  //end of main()
 	
 //insertq()
 void insertq(struct Queue **pf,struct Queue **pr,int x)
 {
 	struct Queue *p; //Always points to 
 	p=(struct Queue *)malloc(sizeof(struct Queue));
 	
 	//When heap(RAM) is full(Rare Case) no new node is created
 	if(p==NULL) 
 	{
 		printf("Queue Overflow\n");
 		return;
	}
	p->data=x; //store the data in the newly created node
	p->next=NULL; //store NULL in the newly created node next section.
	
	//if else used
	if(*pf==NULL) //True for 1st Node *pf means front
       *pf=p;  //front pointer is also changed
    else //from 2nd node else part is always executed changes only in rear pointer
      (*pr)->next=p; //put address of new node in the next section of node pointed by rear
      
    *pr=p; 	//*pr means rear (value at address pointed by pr)
 } //insertq()
 
 //removeq()
 int removeq(struct Queue **pf,struct Queue **pr)
 {
 	struct Queue *temp;
 	int x;
 	
 	if(*pf==NULL) //*pf means front only (Check for no node exist in the list)
 	{
 		printf("Queue Underflow(Empty)\n");
 		return 0;
	}
	temp=*pf; //temp pointing to the front node currently pointed by front pointer
	x=temp->data; //extract the data from the front node currently pointed by front pointer
	
	if(*pf==*pr)  //when List has single node only
	{
	  *pr=NULL;  //rear will be NULL
	}	
	
    *pf=(*pf)->next; //move to the next front node  
    free(temp); //delete the node once data is removed
    
    return x;
 } //removeq()
 
 
 void display(struct Queue *p)
 {
  	int x;
 	
 	if(p==NULL)
 	{
 		printf("Queue Underflow(Empty)\n");
 		return;
	}
	printf("The Queue Elements are \n");
	
	while(p!=NULL)
	{
	  printf("%d\n",p->data);
	  p=p->next; //p will now point to the next node in the list
	}
 } //display() 
 	write a description fo github 
 	
 	
 	
 	
 	
 	
 	
 	
 	
 	
 	
 	
 	
 	
 


🚀 Queue Implementation Using Singly Linked List in C
This C program demonstrates how to implement a Queue (FIFO) data structure using a Singly Linked List (SLL). It supports dynamic memory allocation and includes basic operations such as:

Insertion (Enqueue)

Deletion (Dequeue)

Display Queue Elements

📁 Features
Dynamic Queue: Uses malloc() to allocate memory, allowing for flexible queue size.

Linked List-Based: No need for predefined array size, avoids overflow unless system memory is full.

Error Handling: Handles both queue overflow and underflow gracefully.

Interactive Console Menu: Allows users to perform multiple operations interactively.

📌 Functions
void insertq(struct Queue **front, struct Queue **rear, int x);
Inserts an element at the rear of the queue.

int removeq(struct Queue **front, struct Queue **rear);
Removes an element from the front of the queue and returns it.

void display(struct Queue *p);
Displays all elements in the queue.

🛠 Sample Run
Enter the option from following 1.Insert 2.Remove 3.Display Queue
Enter your option 1
Enter a number to be inserted 10
Do you want to continue (y/n) y
Enter your option 1
Enter a number to be inserted 20
Do you want to continue (y/n) y
Enter your option 3
The Queue Elements are
10
20
Do you want to continue (y/n) n
Thank You
📌 Usage
Compile and run with:

