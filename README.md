# stack-in-c

#include<stdio.h>
#include<process.h>
#include<stdlib.h>
#include<conio.h>

#define MAX 5
int  top=-1,stack[MAX];
void PUSH()  //PUSH OPERATION
{
	int val;
	if(top==MAX-1)
	{
		printf("\nStack is full! You cannot perform PUSH operatiion.");
	}
	else
	{
		printf("\nEnter element  :");
		scanf("%d",&val);
		top=top+1;
		stack[top]=val;
	}
}
void POP()   //POP OPERATION
{
	if(top==-1)
	{
		printf("\nStack is empty! You cannot perform POP operation.");
	}
	else
	{
		printf("\nDeleted element is %d",stack[top]);
		top=top-1;
		
	}
}
void PEEP()  //PEEP OPERATION
{
	int i,val;
	printf("\nEnter the index value you want to find(1 to top).");
	scanf("%d",&i);
	if(top-i+1<1)
	{
		printf("\nStack is empty!");
	}
	else
	{
		val=stack[top-i+1];
		printf("\nValue at index %d is %d",i,val);
	}
}
void CHANGE()  //CHANGE OPERATION
{
	int i,val;
	printf("\nEnter index where you have to change value(1 to top) :");
	scanf("%d",&i);
	printf("\nenter new value :");
	scanf("%d",&val);
	if(stack[top]-i+1<1)
	{
		printf("\nStack is empty!");
	}
	else
	{
		stack[top-i+1]=val;
		printf("\nValue is changed.");
	}
}
void DISPLAY()  //DISPLAY OPERATION
{
	int i;
	if(top==-1)
	{
		printf("\nStack is empty! Cannot display.");
	}
	else
	{
		printf("\nStack is     :\n");
		for(i=top;i>=0;i--)
		{
			printf("%d\t",stack[i]);
		}
	}
}

int main()   //MAIN FUNCTION
{
	int op;
	
	while(1)
	{
		printf("\n***Stack Menu***");
		printf("\n\n1)PUSH  2)POP  3)DISPLAY  4)PEEP  5)CHANGE  6)EXIT");
		printf("\n\nEnter your choice(1-6)");
		scanf("%d",&op);
		
		switch(op)
		{
			case 1:
				PUSH();
				break;
			case 2:
				POP();
				break;
			case 3:
				DISPLAY();
				break;
			case 4:
				PEEP();
				break;
			case 5:
				CHANGE();
				break;
			case 6:
				exit(0);
			default:
				printf("\nWrong choice!");
		}
	}
	return 0;
}
