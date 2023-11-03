# OS-EX.12-IMPLEMENTATION-OF-FILE-ALLOCATION-METHODS

## FILE MANAGEMENT USING SEQUENTIAL ALLOCATION

## AIM:

To implement file management using sequential list. 

## PROGRAM:

```
#include <stdio.h>
void main()
{
int f[50], i, st, len, j, c, k, count = 0;
for(i=0;i<50;i++)
f[i]=0;
printf("Files Allocated are : \n");
x: count=0;
printf("Enter starting block and length of files: ");
scanf("%d%d", &st,&len);
for(k=st;k<(st+len);k++)
if(f[k]==0)
count++;
if(len==count)
{
for(j=st;j<(st+len);j++)
if(f[j]==0)
{
f[j]=1;
printf("%d\t%d\n",j,f[j]);
}
if(j!=(st+len-1))
printf(" The file is allocated to disk\n");
}
else
printf(" The file is not allocated \n");
printf("Do you want to enter more file(Yes - 1/No - 0)");
scanf("%d", &c);
if(c==1)
goto x;
else
exit(0);
getch();
}
```

## OUTPUT:

![12 1](https://github.com/Skanthasishanth/OS-EX.12-IMPLEMENTATION-OF-FILE-ALLOCATION-METHODS/assets/118298456/7c9573f0-6a9b-450e-b875-a2f7a0e9d4f4)


## RESULT:

Thus, file management using sequential list is implemented successfully. 


## FILE MANAGEMENT USING INDEXED ALLOCATION 

## AIM:

To implement file management using Indexed list. 

## PROGRAM:

```
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>
void main()
{
int f[50], index[50],i, n, st, len, j, c, k, ind,count=0;
for(i=0;i<50;i++)
f[i]=0;
x:printf("Enter the index block: ");
scanf("%d",&ind);
if(f[ind]!=1)
{
printf("Enter no of blocks needed and no of files for the index %d on the disk : \n", ind);
scanf("%d",&n);
}
else
{
printf("%d index is already allocated \n",ind);
goto x;
}
y: count=0;
for(i=0;i<n;i++)
{
scanf("%d", &index[i]);
if(f[index[i]]==0)
count++;
}
if(count==n)
{
for(j=0;j<n;j++)
f[index[j]]=1;
printf("Allocated\n");
printf("File Indexed\n");
for(k=0;k<n;k++)
printf("%d ------- >%d : %d\n",ind,index[k],f[index[k]]);
}
else
{
printf("File in the index is already allocated \n");
printf("Enter another file indexed");
goto y;
}
printf("Do you want to enter more file(Yes - 1/No - 0)");
scanf("%d", &c);
if(c==1)
goto x;
else
exit(0);
getch();
}
```

## OUTPUT:

![12 2](https://github.com/Skanthasishanth/OS-EX.12-IMPLEMENTATION-OF-FILE-ALLOCATION-METHODS/assets/118298456/1e41583c-0ae3-4214-82ea-8cf955e8f12e)


## RESULT:

Thus, file management using Indexed list is implemented successfully. 



## FILE MANAGEMENT USING LINKED ALLOCATION

## AIM:

To implement file management using Linked list. 

## PROGRAM:

```
#include <stdio.h>
#include <conio.h>
#include <stdlib.h>
void recursivePart(int pages[]){
int st, len, k, c, j;
printf("Enter the index of the starting block and its length: ");
scanf("%d%d", &st, &len);
k = len;
if (pages[st] == 0){
for (j = st; j < (st + k); j++){
if (pages[j] == 0){
pages[j] = 1;
printf("%d ----- >%d\n", j, pages[j]);
}
else {
printf("The block %d is already allocated \n", j);
k++;
}
}
}
else
printf("The block %d is already allocated \n", st);
printf("Do you want to enter more files? \n");
printf("Enter 1 for Yes, Enter 0 for No: ");
scanf("%d", &c);
if (c==1)
recursivePart(pages);
else
exit(0);
return;
}
int main(){
int pages[50], p, a;
for (int i = 0; i < 50; i++)
pages[i] = 0;
printf("Enter the number of blocks already allocated: ");
scanf("%d", &p);
printf("Enter the blocks already allocated: ");
for (int i = 0; i < p; i++){
scanf("%d", &a);
pages[a] = 1;
}
recursivePart(pages);
getch();
return 0;
} 
```

## OUTPUT:

![12 3](https://github.com/Skanthasishanth/OS-EX.12-IMPLEMENTATION-OF-FILE-ALLOCATION-METHODS/assets/118298456/0af3c052-6d44-401d-bec7-5480290e80a2)


## RESULT:

Thus, file management using Linked list is implemented successfully. 
