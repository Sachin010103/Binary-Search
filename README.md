#include<stdio.h>

void takearray(int A[], int size){
    for (int i = 0; i <size; i++)
    {
        printf("Enter the A[%d] element : ",i+1);
        scanf("%d",&A[i]);
    }
   
}

void printarray(int A[], int lenght){
    for (int i = 0; i <lenght; i++)
    {
         printf("%d ",*(A+i));
    }
     printf("\n");
}

int binarysearch(int A[],int low,int high,int key){
    int mid=(low+high)/2; 
    if(low==high && A[low]!=key){
       return 0;
    }
    else{
    if (A[mid]==key)
    {
        return mid;
    }
    else if (A[mid]>key)
    {
        binarysearch(A,low,mid-1,key);
    }
    else if(A[mid]<key){
       binarysearch(A,mid+1,high,key);
    }
    }

}

int main(){
    int lenght,key;
    printf("Enter the length of the list : ");
    scanf("%d",&lenght);
    int A[lenght];
    takearray(A,lenght);
    printarray(A,lenght);

    printf("Enter the element to be search : ");
    scanf("%d",&key);
    
    int index=binarysearch(A,0,lenght-1,key);

   (index==0)? printf("Not found"): printf("The element %d is at index %d ",key ,index+1);
} 
