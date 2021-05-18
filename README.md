# Assignment-3-
Assignment(3)
#Multiply Two  matrix with c
##include <stdio.h>
 
const int MAX = 100;
 
// Function to print Matrix
void printMatrix(int M[][MAX], int rowSize, int colSize)
{
    for (int i = 0; i < rowSize; i++) {
        for (int j = 0; j < colSize; j++)
            printf("%d ", M[i][j]);
 
        printf("\n");
    }
}
 
// Function to multiply two matrices A[][] and B[][]
void multiplyMatrix(int row1, int col1, int A[][MAX],
                    int row2, int col2, int B[][MAX])
{
    int i, j, k;
 
    // Matrix to store the result
    int C[MAX][MAX];
 
    // Check if multiplication is Possible
    if (row2 != col1) {
        printf("Not Possible\n");
        return;
    }
 
    // Multiply the two
    for (i = 0; i < row1; i++) {
        for (j = 0; j < col2; j++) {
            C[i][j] = 0;
            for (k = 0; k < row2; k++)
                C[i][j] += A[i][k] * B[k][j];
        }
    }
 
    // Print the result
    printf("\nResultant Matrix: \n");
    printMatrix(C, row1, col2);
}
 
// Driven Program
int main()
{
    int row1, col1, row2, col2, i, j;
    int A[MAX][MAX], B[MAX][MAX];
 
    // Read size of Matrix A from user
    printf("Enter the number of rows of First Matrix: ");
    scanf("%d", &row1);
    printf("%d", row1);
    printf("\nEnter the number of columns of First Matrix: ");
    scanf("%d", &col1);
    printf("%d", col1);
 
    // Read the elements of Matrix A from user
    printf("\nEnter the elements of First Matrix: ");
    for (i = 0; i < row1; i++) {
        for (j = 0; j < col1; j++) {
            printf("\nA[%d][%d]: ", i, j);
            scanf("%d", &A[i][j]);
            printf("%d", A[i][j]);
        }
    }
 
    // Read size of Matrix B from user
    printf("\nEnter the number of rows of Second Matrix: ");
    scanf("%d", &row2);
    printf("%d", row2);
    printf("\nEnter the number of columns of Second Matrix: ");
    scanf("%d", &col2);
    printf("%d", col2);
 
    // Read the elements of Matrix B from user
    printf("\nEnter the elements of First Matrix: ");
    for (i = 0; i < row2; i++) {
        for (j = 0; j < col2; j++) {
            printf("\nB[%d][%d]: ", i, j);
            scanf("%d", &B[i][j]);
            printf("%d", B[i][j]);
        }
    }
 
    // Print the Matrix A
    printf("\n\nFirst Matrix: \n");
    printMatrix(A, row1, col1);
 
    // Print the Matrix B
    printf("\nSecond Matrix: \n");
    printMatrix(B, row2, col2);
 
    // Find the product of the 2 matrices
    multiplyMatrix(row1, col1, A, row2, col2, B);
 
    return 0;
}

![A1](https://user-images.githubusercontent.com/82906996/118716696-6acc3280-b825-11eb-84d9-feec5ddefcc4.png)

![A2](https://user-images.githubusercontent.com/82906996/118716761-7cadd580-b825-11eb-8edc-514b2adb1544.png)

-----------------------------------------------------------------------------------------------
#Multiply matrix with Java
import java.io.*;
import java.util.*;
 
class GFG{
     
static int MAX = 100;
 
// Function to print Matrix
static void printMatrix(int M[][], int rowSize,
                        int colSize)
{
    for(int i = 0; i < rowSize; i++)
    {
        for(int j = 0; j < colSize; j++)
            System.out.print(M[i][j] + " ");
 
        System.out.println();
    }
}
 
// Function to multiply two matrices A[][] and B[][]
static void multiplyMatrix(int row1, int col1,
                           int A[][], int row2,
                           int col2, int B[][])
{
    int i, j, k;
 
    // Matrix to store the result
    int C[][] = new int[MAX][MAX];
 
    // Check if multiplication is Possible
    if (row2 != col1)
    {
        System.out.println("Not Possible");
        return;
    }
 
    // Multiply the two
    for(i = 0; i < row1; i++)
    {
        for(j = 0; j < col2; j++)
        {
            C[i][j] = 0;
            for(k = 0; k < row2; k++)
                C[i][j] += A[i][k] * B[k][j];
        }
    }
 
    // Print the result
      System.out.println();
    System.out.println("Resultant Matrix: ");
    printMatrix(C, row1, col2);
}
 
// Driver code
public static void main(String[] args)
{
    Scanner read = new Scanner(System.in);
    int row1, col1, row2, col2, i, j;
    int A[][] = new int[MAX][MAX];
    int B[][] = new int[MAX][MAX];
 
    // Read size of Matrix A from user
    System.out.print("Enter the number of " +
                     "rows of First Matrix: ");
    row1 = read.nextInt();
    System.out.println(row1);
    System.out.print("Enter the number of " +
                     "columns of First Matrix: ");
    col1 = read.nextInt();
    System.out.println(col1);
 
    // Read the elements of Matrix A from user
    System.out.println("Enter the elements " +
                       "of First Matrix: ");
    for(i = 0; i < row1; i++)
    {
        for(j = 0; j < col1; j++)
        {
            System.out.print("A[" + i + "][" +
                                    j + "]: ");
            A[i][j] = read.nextInt();
            System.out.println(A[i][j]);
        }
    }
 
    // Read size of Matrix B from user
    System.out.print("Enter the number of " +
                     "rows of Second Matrix: ");
    row2 = read.nextInt();
    System.out.println(row2);
    System.out.print("Enter the number of " +
                     "columns of Second Matrix: ");
    col2 = read.nextInt();
    System.out.println(col2);
 
    // Read the elements of Matrix B from user
    System.out.println("Enter the elements " +
                       "of First Matrix: ");
    for(i = 0; i < row2; i++)
    {
        for(j = 0; j < col2; j++)
        {
            System.out.print("A[" + i + "][" +
                                    j + "]: ");
            B[i][j] = read.nextInt();
            System.out.println(B[i][j]);
        }
    }
 
    // Print the Matrix A
    System.out.println();
    System.out.println("First Matrix: ");
    printMatrix(A, row1, col1);
     
    // Print the Matrix B
      System.out.println();
    System.out.println("Second Matrix: ");
    printMatrix(B, row2, col2);
 
    // Find the product of the 2 matrices
    multiplyMatrix(row1, col1, A, row2, col2, B);
}
}

![WhatsApp Image 2021-05-18 at 10 01 43 PM1](https://user-images.githubusercontent.com/82906996/118717335-3c028c00-b826-11eb-9499-1b75aa6b7be5.jpg)



