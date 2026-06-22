# DSA-Questions
Here I upload all DSA Question solved by me .

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