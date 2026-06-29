# DSA-Questions
Here I upload all DSA Question which is solved by me .

question - trap water
import java.util.*;
class  Demo 
{ // trap water
             public static  int  traprainwater(int height[] ){
              int n = height.length;
              //calc left max boundry
              int leftmax[] = new int[n];
              leftmax[0] = height[0];
              for(int i=1; i<n; i++){
                leftmax[i] = Math.max(height[i], leftmax[i-1]);
              }
              //calc right max boundry
              int rightmax[] = new int[ n];
              rightmax[n-1] = height[ n-1];
             for( int i=n-2; i>=0; i--){
             rightmax[i] = Math.max(height[i], rightmax[i+1]);
             }
             int trapwater= 0;
              for( int i=0; i<n; i++){
                //water level  = waterlevel - height[i]
                int waterlevel = Math.min(leftmax[i],rightmax[i]);
                trapwater += waterlevel-height[i];
              }
           return trapwater;

            }
             public  static void main(String arg[]){
               int height[] = { 2,3,4,1,2,1,5,3 };    
             System.out.println(traprainwater(height)) ;
          }
        } 



        **PRINT SPIRAL MATRIXXX**
                    import java.util.*;
            class  Matrices
              {public static void prs( int matrix[][]){
                int startrow = 0;  
                int startcol = 0; 
                int endrow = matrix.length - 1;
                int endcol = matrix[0].length-1;

                while(startrow <= endrow && startcol <= endcol  ){
                  //top boundry  
                  for( int j=startcol ; j<=endcol; j++){
                    System.out.print(matrix[startrow][j]+" ");
                  }
                  //right
                  for( int i = startrow+1; i<=endcol; i++){
                    System.out.print(matrix[i][endcol]+" ");
                  }
                   // bottom
                   for(int j=endcol-1; j>=startcol; j--){
                    if( startrow == endrow) {
                      break;
                    }
                    System.out.print(matrix[endrow][j]+" ");
                   }
                    //left
                    for( int i=endrow-1; i>= startrow+1; i--){
                      if( startcol == endcol) {
                      break;
                    }
                    System.out.print(matrix[startcol][i]+" ");
                    }
                    startcol++;
                    startrow++;
                    endcol--;
                    endrow--;
                }
                     System.out.println();
              }
            public static void main(String arg[]){
            int matrices [][] =  {{1, 2 , 3 ,4 },
                                     { 5, 6, 7 ,8, },
                                      { 9, 10, 11, 12 },
                                    { 13 , 14 , 15 , 16}};
                                    prs(matrices);
                                 }
                                  }
            