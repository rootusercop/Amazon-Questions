
/*
 * Question : Find the maximum continuous subsequence sum in an array
 * Source: http://www.geeksforgeeks.org/largest-sum-contiguous-subarray/
 * 		   https://www.youtube.com/watch?v=hXlv88ddcgw&list=PL962BEE1A26238CA3
 */

package FindMaxContinuousSumInArray;

import java.util.Scanner;

public class UsingDynamicProgramming {
	
	    public static void main(String[] args){
	        Scanner in = new Scanner(System.in);
	        try{
	            System.out.println("Enter the number of array elements");
	            int n = in.nextInt();
	            int[] a = new int[n];
	            System.out.println("Enter the array elements");
	            for(int i=0;i<n;i++)
	                a[i]=in.nextInt();
	            System.out.println("The max sym in the array is: "+maxSum(a));
	        }
	        finally{
	        in.close();
	        }
	    }
	    public static int maxSum(int[] a){
	    
	    // We will solve this problem using Dynamic Programming
	    
	    if(a.length==0 || a==null)
	        return -1;
	    
	    int[] dp = new int[a.length];
	    dp[0] = a[0];
	    
	    for(int i=1;i<a.length;i++)
	        dp[i] = Math.max(dp[i-1]+a[i],a[i]);
	    
	    
	    // iterate over all the values of dp to find the max
	    int max = 0;
	    for(int element: dp)
	         max = Math.max(max,element);
	         
	     return max;       
	    }
	    /*
	    Analysis:
	    Time Complexity = O(n)
	    Space Complexity = O(n) which is used to store the dp array
	    */
	}

