#include<stdio.h>
#include <stdlib.h>
int r,c;
void traverse(int mat[r][c],int row,int col)
{
    if(row>=0 && row<r && col>=0 && col<c)
    {
        if(mat[row][col]==0)
        {
            return;
        }
        mat[row][col]=0;
        traverse(mat,row,col-1);
        traverse(mat,row,col+1);
        traverse(mat,row-1,col);
        traverse(mat,row+1,col);
        traverse(mat,row-1,col-1);
        traverse(mat,row-1,col+1);
        traverse(mat,row+1,col-1);
        traverse(mat,row+1,col+1);
    }
}
int main()
{
 scanf("%d %d",&r,&c);
 int mat[r][c];
 for(int row=0;row<r;row++){
    for(int col=0;col<c;col++){
        scanf("%d ",&mat[row][col]);
    }
 }
 int count=0;
 for(int row=0;row<r;row++)
 {
    for(int col=0;col<c;col++)
    {
        if(mat[row][col]==1)
        {
            count++;
            traverse(mat,row,col);
        }
    }
 }
 printf("%d*",count);
}
