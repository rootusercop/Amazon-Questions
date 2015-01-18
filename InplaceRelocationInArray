
/*

Question: WAP to modify the array such that arr[I] = arr[arr[I]]. 
DO THIS IN PLACE i.e. with out using additional memory. 

example : if a = {2,3,1,0} 
o/p = a = {1,0,3,2} 

NOTE : THE ARRAY CONTAINS 0 TO N-1 INTEGERS.

Source: http://www.careercup.com/question?id=4909367207919616


 * ALGORITHM: 
 * 
 * What we are doing is effectively magnifying the final result so that the current 
 * value doesn't matter anymore. When we multiply the arr[arr[i]] by size and add the current value to it,
 * you get a new value. This new value can use division to get the final result or modulo to obtain the 
 * current value. When he does the division, the current value(remainder) just falls off and you get the 
 * final value.


For General Understanding, understand this:
(x + y*z)/z = y    provided x and y is less than z. (IN SHORT USE / TO DROP THE CURRENT VALUE GET THE OTHER VALUE)
(x + y*z)%z = x    provided x and y is less than z. (IN SHORT USE % TO GET THE CURRENT VALUE)
This is the concept used here.
Example:
(3 + 4*5)/5 = 4
(3 + 4*5)%5 = 3

arr[i] = arr[i] + arr[arr[i]]*size
so arr[i]/size = arr[arr[i]]

In the code you see the author has used % below; this is done just to make sure arr[i] and arr[arr[i]] is less than size as explained earlier.
arr[i] += (arr[arr[i]]%size)*size;

 */



package InplaceRelocation;

import java.util.Scanner;

public class RelocateArray {
public static void main(String[] args) {
	Scanner in = new Scanner(System.in);
	try{
	System.out.println("Enter the elements of the array");
	int n = in.nextInt();
	int[] a = new int[n];
	for(int i=0;i<n;i++)
		a[i]=in.nextInt();
	System.out.println("After inplace Relocation: ");
	inplaceRelocation(a);
	}finally{
		in.close();
	}
}

private static void inplaceRelocation(int[] arr) {
	// extreme case
	if(arr==null || arr.length==0)
		return;
	
	int size = arr.length;
	/* 
	 * PLEASE REMEMBER, VERY IMP: We need two loops, we cannot solve this problem using this algorithm 
	 * using single loop
	 * 
	 */
	for(int i=0;i<size;i++) {
		/*
		 * This loop does x = (x + y*z)
		 */
		arr[i] %=size;                             // %size is just to handle the case where arr[i] > size                    
		arr[i] += (arr[arr[i]]%size)*size;         // %size is just to handle the case where arr[arr[i]] > size 
	}
	for(int i=0;i<size;i++) {
		/*
		 * This loop does x = x/z
		 */
		arr[i] /= size;
		System.out.println(arr[i]);
	}
	/*
	 * The two for loops just do the following:
	 * x = (x + y*z)/z = y                i.e. WE USE / TO DROP THE CURRENT VALUE GET THE OTHER VALUE   
	 * Here,x = arr[i]
	 *      y = arr[arr[i]]
	 *      z = size
	 *      
	 *  NOTE: (arr[i]%size) AND (arr[arr[i]]%size) are only used to handle the case where arr[i] > size 
	 *        and arr[arr[i]] > size
	 */
	}
}
/*
 * Analysis:
 *  Time Complexity = O(n) where n = number of elements in the array
 *  Space Complexity = O(1)
*/
