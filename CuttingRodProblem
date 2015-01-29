
/*
 * Question: What is the best price for cutting a rod of length n
 * 
 * Question and Answer Source: http://www.geeksforgeeks.org/dynamic-programming-set-13-cutting-a-rod/
 * 							   https://www.youtube.com/watch?v=U-09Gs6cbsQ&list=PL962BEE1A26238CA3&index=4
 * 
 */

package dynamicProgramming;

import java.util.Scanner;

public class CuttingRodProblem {
	 public static void main(String[] args){
		    Scanner in = new Scanner(System.in);
		    try{
		    	System.out.println("Enter the number of cuts");
		    	int n = in.nextInt();
		    	int[] prices = new int[n];
		    	System.out.println("Enter the prices of rod cuts");
		    	for(int i=0;i<n;i++){
		    		System.out.println("Enter price for "+(i+1)+" rod length");
		    		prices[i] = in.nextInt();
		    	}
		    	System.out.println("The best price for rod cut of size "+n+" using Recursion is: "+byRecursion(prices, n));
		    	System.out.println("The best price for rod cut of size "+n+" using DP is: "+byDP(prices, n));
		    }
		    finally{
		    	in.close();
		    }
	    }
	    public static int byRecursion(int[] prices, int rodLength){
	         
	         // Base Case
	         if(rodLength<=0)
	             return 0;     // if rod length is 0 then there is no best price
	         
	         // Recursive Step
	         int maxPrice = 0;
	         for (int i = 0; i<rodLength; i++)
	             maxPrice = Math.max(maxPrice, prices[i]+byRecursion(prices,rodLength-1-i));
	             
	         
	         // Returning Step
	         return maxPrice;
	           
	    }
	    /*
		    * Analysis:
		    * Time Complexity = O(2^n)  // not sure
		    * Space Complexity = O(1) used by dp array 
		    */
	    public static int byDP(int[] prices, int rodLength){
	        
	        int[] dp = new int[rodLength+1];   // +1 because 0 rodLength will have best prices of 0
	        dp[0] = 0;
	        
	        int maxPrice = -1;
	        for(int i=1;i<=rodLength;i++){  // i represents rodLength
	            for(int j=0;j<i;j++)        // price of cut from 0 to rodLength-1
	                maxPrice = Math.max(maxPrice,prices[j]+dp[i-j-1]);  // here i represents rodLength
	            dp[i] = maxPrice;
	        }
	        
	        return dp[rodLength];
	    }
	   /*
	    * Analysis:
	    * Time Complexity = O(n^2)
	    * Space Complexity = O(n) used by dp array 
	    */
}
