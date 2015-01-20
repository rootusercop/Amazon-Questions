/*
 * Question:  Multiply all fields except it's own position. 
input [2,3,1,4] 
output [12,8,24,6] 

RESTRICTIONS: 
1. no use of division 
2. complexity in O(n)

Source: http://www.careercup.com/question?id=5179916190482432
 * 
 * ALGORITHM: 1. Create 2 arrays, forward and backward of the same length
 *            2. Store 1 as first element of forward and 1 as last element of backward
 *            3. Run loop (n-1) times
 *            			calculate FORWARD multiplication of array elements till the current position starting from index 1 to (input.length-1)
 *            			calculate BACKWARD multiplication of array elements till the current position starting from (input.length-2)  to 0
 *            4. Run loop from 0 to n-1
 *            			output[i] = forward[i]*backward[i]
 *            
 * Explanation of Algorithm:
 * arr = 2, 3, 1, 4

// maintain two arrays which can be done in O(n)

Put arr1[0]=1;
    arr2[arr2.length-1]=1;

arr1 = 1, 2,  6,  6  (arrays multiply each number with previous and current starting from 1 to (n-1))
arr2 = 12, 4, 4 , 1  (arrays multiplied from end starting from (n-2) to 0)

Then to find number at index 'i' you would just do:

output[i]=arr1[i]*arr2[i]    (arrays multiplied starting from 0 to (n-1))
 */

package MultiplyAllOtherElementsExceptItself;

import java.util.Arrays;
import java.util.Scanner;

public class IterativeSolutionWithLinearTimeComplexity {
public static void main(String[] args) {
	Scanner in = new Scanner(System.in);
	try{
	System.out.println("Enter the number of elements in the array");
	int n = in.nextInt();
	System.out.println("Enter the elements of the array");
	int[] a= new int[n];
	for(int i=0;i<n;i++)
		a[i]=in.nextInt();
	System.out.println("Solution using three arrays is: "+multiplyUsingTwoArrays(a));
	System.out.println("Solution using single array is: "+multiplyUsingSingleArray(a));
	}
	finally{
		in.close();
	}
	
	}


private static String multiplyUsingTwoArrays(int[] input) {
	int[] forward = new int[input.length];
	int[] backward = new int[input.length];
	
	// store the initial elements 
	forward[0]=1;                           // first element of forward is 1
	backward[input.length-1]=1;             // last element of backward is 1
	
	// Use loop to calculate forward multiplication
	for(int i=1;i<forward.length;i++)                        
		forward[i] = forward[i-1]*input[i-1];
	
	// Use loop to calculate backward multiplication
	for(int i=(backward.length-2);i>=0;i--)
		backward[i]=backward[i+1]*input[i+1];
	
	
	
	// store the result in output array
	int[] output = new int[input.length];
	for(int i=0;i<output.length;i++)
		output[i]=forward[i]*backward[i];
	
	// return the result
	return Arrays.toString(output);
		
}
/*
Analysis:
	Time Complexity,
			3n since we pass n elements thrice, asymptotically it is = O(n)
			where n = number of elements in the input array
	Space Complexity,
			3n since forward, backward and output array is used = O(3n)
*/


private static String multiplyUsingSingleArray(int[] input) {
	int[] aux = new int[input.length];
	
	// take a variable to store the product
	int product = 1;
	
	// calculate forward multiplication
	for(int i=0;i<aux.length;i++){
		aux[i]=product;
		// update the product by multiplying with input array in FORWARD DIRECTION
		product *= input[i];
	}
	
	// update the product to reuse it again
	product = 1;
	
	// calculate backward multiplication
	for(int i=aux.length-1;i>=0;i--){
		aux[i] *= product;                   // VERY IMP STEP
		// update product
		product *= input[i];                 // VERY IMP STEP
	}
	
	// return the result
	return Arrays.toString(aux);
	
}

/*
Analysis:
	Time Complexity,
			2n since we pass n elements twice, asymptotically it is = O(n)
			where n = number of elements in the input array
	Space Complexity,
			n since only one array is used called auxiliary array. Hence O(n)
*/


}
