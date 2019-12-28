#include<stdio.h>
#include<stdlib.h>
int *array;
int top = 0;
int size=2;
int pop()
{
	if(top<=size/4)
	{
 int *array2 = (int*)malloc(sizeof(int)*size/2);
	for(int i=0;i<size;i++)
	array2[i] = array[i];//DİKKATT!!!!ilk dizinin elemanlarını ikinci diziye kopyalama işlemi
	free(array);
	array = array2;
	size = size/2;
	}
	return array[--top];
}
void push(int a)
{
	if(top>=size){
	int *array2 = (int*)malloc(sizeof(int)*size*2);
	for(int i=0;i<size;i++)
	array2[i] = array[i];//DİKKATT!!!!ilk dizinin elemanlarını ikinci diziye kopyalama işlemi
	free(array);
	array = array2;
	size = size*2;
}
     array[top++]=a;
}
void display()
{
	printf("Displaying\n ");
	for(int i=0;i<top;i++)
	{
	printf("%d\n",array[i]);
}
	printf("size:%d\n",size);

}
int main()
{
	array = (int*)malloc(sizeof(int));
	push(10); 
	push(20);
	push(30);
	push(40);
	push(50);
	display();
		printf("popped :%d\n",pop());
	printf("popped :%d\n",pop());
	printf("popped :%d\n",pop());
	printf("popped :%d\n",pop());
display();
pop();
,	
	
	
	
	
	return 0;
}
