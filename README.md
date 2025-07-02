#include <stdio.h>

int main() {
    int size1,size2,j;
    
    printf("Enter max input for the first array: ");
    scanf("%d",&size1);
    int arr1[size1];
    for (int i=0;i<size1;i++){
        scanf("%d",&arr1[i]);
    }
    printf("Enter max input for the second array: ");
    scanf("%d",&size2);
    int arr2[size2];
    for (int i=0;i<size2;i++){
        scanf("%d",&arr2[i]);
    }
    
    int max_size = (sizeof(arr1)/sizeof(arr1[0])) + (sizeof(arr2)/sizeof(arr2[0]));
    int max_arr[max_size];
    for (j=0;j<size1;j++){
        max_arr[j] = arr1[j];
    }
    for (int i=0;i<size2;i++){
        max_arr[j] = arr2[i];
        j++;
    }
    
    for (int i=0;i<max_size;i++){
        for (int k=0;k<max_size;k++){
            if (max_arr[i]<max_arr[k]){
                int temp = max_arr[i];
                max_arr[i] = max_arr[k];
                max_arr[k] = temp;
            }
        }
    }
    
    
    for (int i=0;i<max_size;i++){
        printf("%d ",max_arr[i]);
    }
    return 0;
}
