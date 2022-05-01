#include <stdio.h>
#include <stdlib.h>
#define MAX 10
int top = -1;
int top1 = -1;
void push_element(int arr[])
{
    if (top <= MAX - 1)
    {
        int input;
        printf("\n enter your element -> ");
        top++;
        scanf("%d", &input);
        arr[top] = input;
    }
    else
        printf("-------------------------------------------------------overflow--------------------------------------------------------------------\n");
}
int pop_element(int arr[])
{
    if (top < 0)
    {
        printf("---------------------------------------------------underflow----------------------------------------------------------\n");
        return -1;
    }
    else
    {
        int val1 = arr[top];
        top--;
        return val1;
    }
}
void display_element(int arr[], int temp[])
{
    //                           printf("your array is ->  ");
    //                       for(int i=0;i<=top;i++)
    //                       {
    //                               printf("%d ",arr[i]);
    //                       }
    //                       printf("\n");
    //                       printf("press enter for continue the porgrame \n");
    //                       getchar();
    //                       getchar();
    //  printf("%d \n", top);
    while (top >= 0)
    {
        int val = pop_element(arr);

        top1++;
        temp[top1] = val;

        //   printf("%d ",val);
    }
    while (top1 != -1)
    {
        top++;
        arr[top] = temp[top1];
        printf("%d ", arr[top]);
        top1--;
    }
    printf("\n");
    printf("\n press enter to continue the program \n");
    getchar();
    getchar();
}
int main()
{
    int arr[MAX], temp[MAX];
    printf("============================================================================================================================\n");
    printf("select your choice that is given seduled \n");
    printf("-----------------------------------------------------------------------------------------------------------------------------------\n");
    printf("!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!\n");
    printf("---------------------------------------------------welcome in our stack programe-------------------------------------------------------------\n");
    while (1)
    {
        printf("\n============================================================================================================================================\n");
        printf("!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!\n");
        printf("\t 1.) push element in stack \n");
        printf("\t 2.) pop element from stack \n");
        printf("\t 3.) display the element of stack \n");
        printf("\t 4.)exit for the programe \n");
        printf("---------------------------------------------------------------------------------------------------------------------------------------------\n");
        printf("========================================================================================================================================================\n");
        int choice;
        scanf("%d", &choice);
        switch (choice)
        {
        case 1:
            push_element(arr);
            break;
        case 2:
            printf(" \n you pop the element %d ", pop_element(arr));
            break;

        case 3:
            display_element(arr, temp);
            break;
        case 4:
            exit(0);
        default:
            printf("\n invalid input \n");
            break;
        }
    }

    return 0;
}
