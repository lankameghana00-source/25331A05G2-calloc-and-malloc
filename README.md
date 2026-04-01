#include <stdio.h>
#include <stdlib.h>
 int main() 
{
 int n, i;
 int *ptr1, *ptr2;
 printf("Enter number of elements: ");
 scanf("%d", &n);
 ptr1 = (int *)malloc(n * sizeof(int));
 if (ptr1 == NULL) {
 printf("Memory not allocated using malloc\n");
 return 0;
 }
 printf("\nMemory allocated using malloc\n");
 printf("Enter %d elements:\n", n);
 for (i = 0; i < n; i++) {
 scanf("%d", &ptr1[i]);
 }
 printf("Elements stored in malloc memory:\n");
 for (i = 0; i < n; i++) {
 printf("%d ", ptr1[i]);
 }
 ptr2 = (int *)calloc(n, sizeof(int));
 if (ptr2 == NULL) {
 printf("\nMemory not allocated using calloc\n");
 return 0;
 }
 printf("\n\nMemory allocated using calloc (initialized to zero):\n");
 for (i = 0; i < n; i++) {
 printf("%d ", ptr2[i]);
 }
 free(ptr1);
 free(ptr2);
 return 0;
}
