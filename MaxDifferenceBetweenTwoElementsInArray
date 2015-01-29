
/*
 * Question: Maximum difference between 2 elements in an array such that 2nd element occurs later after 1st ?
 * Question Source: http://www.careercup.com/question?id=6051351341563904
 * 
 
 * 
 * Examples: If array is [2, 3, 10, 6, 4, 8, 1] then returned value should be 8 (Diff between 10 and 2). 
 * If array is [ 7, 9, 5, 6, 3, 2 ] then returned value should be 2 (Diff between 7 and 9)
 * 
 *Solution Source: http://www.geeksforgeeks.org/maximum-difference-between-two-elements/
 *
 * Algorithm:
 * 1. MIN = arr[0]
 * 2. max_diff = arr[1] - arr[0]
 * 3. FROM i=1 to n
 * 		check for arr[i]-MIN > max_diff. If true then replace max_diff with arr[i]-MIN
 * 		also check for min element in the array. if(arr[i]<MIN) then update MIN with value of arr[i]
 * 
 */

package MaxDifferenceBetweenTwoElementsInArray;

import java.util.Scanner;

public class UsingLinearComplexityAlgorithm {
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        try{
            System.out.println("Enter the number of elements in the array");
            int n = in.nextInt();
            int[] a = new int[n];
            System.out.println("Enter the elements");
            for(int i=0;i<n;i++)
                a[i]= in.nextInt();
            
            System.out.println("The max diff in the array is: "+maxDiff(a));
            System.out.println("Using difference sum method: "+usingDifferenceSumMethod(a));
        }
        finally{
            in.close();
        }
    }
    public static int maxDiff(int[] a){
        
        
        if(a.length==0 || a==null)
            return -1;
            
        if(a.length<2)
            return 0;
        
        int MIN = a[0];
        int maxDiff = a[1]-a[0];
        
        for(int i=1;i<a.length;i++){
            
            if((a[i]-MIN) > maxDiff)
                maxDiff = a[i]-MIN;
            
            if(a[i]<MIN)
                MIN = a[i];
        }
        return maxDiff;
    }
    /*
    Analysis: Time Complexity = O(n)
              Space Complexity = O(1)
    */
 public static int usingDifferenceSumMethod(int[] a){ 
	 // Algorithm Source: http://www.geeksforgeeks.org/maximum-difference-between-two-elements/
        
        if(a.length==0 || a==null)
            return -1;
            
        if(a.length<2)
            return 0;
        
        int currentDiff = a[1] - a[0];
        int prevDiffSum = currentDiff;
        int maxDiff = prevDiffSum;
        
        
        for(int i=2;i<a.length;i++){
            
            currentDiff = a[i] - a[i-1];
            
            if(prevDiffSum > 0)
                prevDiffSum = prevDiffSum + currentDiff;
            else
                prevDiffSum = currentDiff;
                
                
            if(prevDiffSum>maxDiff)
                maxDiff = prevDiffSum;
        
        }
        
        return maxDiff;
    }
    /*
    Analysis:
    Time Complexity = O(n)
    Space Complexity = O(1)
    */
}
