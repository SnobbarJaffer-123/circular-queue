//# circular-queue
#include<stdio.h>
 #define MAX 5
 int front = -1;
 int rear = -1; 
int item = 0;
 int myqueue[MAX];
 int size();
 void addToQueue();
 void DisplayQueue(); 
void removeFromQueue();
 int main() 
{ printf("Implementation of Circular Queuee\n");
 int choice, num, i;
 unsigned long int fact;
 while(1)
 { printf("1. Get Size of Queue \n");
 printf("2. Add to Queue\n");
 printf("3. Remove from Queue\n");
 printf("4. Print Queue\n");
 printf("5. Exit\n");
 printf("Enter your choice : ");
 scanf("%d",&choice); 
switch(choice)
 { case 1: printf("Size of Queue is: %d \n\n\n",size());
 break;
 case 2: addToQueue();
 break;
 case 3: removeFromQueue(); 
break; 
case 4: DisplayQueue();
 break;
 case 5: printf("\n\n\t\t Wrong Choice !\n\n\n");
 exit(0); // terminates the complete program execution
 } }
 printf("\nCircular Queue implemenete !\n\n\n");
 return 0; 
} 
int size() 
{ 
int size = (MAX-front + rear) % MAX;
 return size; 
} 
void addToQueue() 
{
 if(((rear + 1) % MAX) == front) 
{
 printf("My Queue is Full\n\n");
 } 
else if( front== -1 && rear == -1)
 { printf("Enter the Item:");
 scanf("%d", &item);
 front = rear = 0;
 myqueue[rear] = item;
 }
 else
 {
 // Create a Space for element to be inserted 
rear = (rear + 1) % MAX;
 // Scan the element
 printf("Enter the Item:");
 scanf("%d", &item);
 // Add to the Queue
 myqueue[rear] = item;
 }
 } 
void DisplayQueue() 
{
 printf("\n Current front Index is %d and rear is %d ", front, rear);
 printf("\nMy Current Queue is ");
 int i = front; 
while(i!= rear )
 {
 printf("%d ", myqueue[i]);
 i = (i+1) % MAX; 
} 
printf("%d ", myqueue[rear]);
 printf("\n \n"); 
} 
void removeFromQueue()
 {
 if(front == -1 || rear == -1)
 { printf("\nMy Queue is currently empty\n"); 
} else if(front == rear)
 {
 printf("\nWe removed %d element \n", myqueue[front] ); 
front = rear = -1;
 } 
else { 
printf("\nWe removed %d element \n", myqueue[front] );
 front = (front + 1) % MAX; 
} 
}
