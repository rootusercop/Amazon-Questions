/*
Question: Check if a number is multiple of 5 without using / and % operators
Source: http://www.geeksforgeeks.org/check-if-a-number-is-multiple-of-5-without-using-and-operators/

Algorithm: 

METHOD 1 (Repeatedly subtract 5 from n) 
Run a loop and subtract 5 from n in the loop while n is greater than 0. After the loop terminates, 
check whether n is 0. If n becomes 0 then n is multiple of 5, otherwise not.

METHOD 2 (Convert to string and check the last character) 
Convert n to a string and check the last character of the string. If the last character is ‘5’ or ‘0’ 
then n is multiple of 5, otherwise not.

Method 3 (Set last digit as 0 and use floating point trick)  // BEST ALGORITHM
A number n can be a mulpile of 5 in two cases. When last digit of n is 5 or 10. If last bit in binary equivalent
of n is set (which can be the case when last digit is 5) then we multiply by 2 using n<<=1 to make sure that if 
the number is multpile of 5 then we have the last digit as 0. Once we do that, our work is to just check if the
last digit is 0 or not, which we can do using float and integer comparison trick.
*/

package checkIfANumberIsMultipleOf5;

import java.util.Scanner;

public class UsingMinusLastCharacterAndIntFlatTrick {
public static void main(String[] args) {
	Scanner in = new Scanner(System.in);
	try{
		System.out.println("Enter a number to check whether it is divisible by 5");
		int n = in.nextInt();
		System.out.println("Using minus operator: "+usingMinusOperator(n));
		System.out.println("Using ascii table: "+usingAsciiTable(n));
		System.out.println("Using float int trick: "+usingFloatIntTrick(n)); // BEST ALGORITHM since TimeComplexity = O(1) and Space Complexity = O(1) 
	}
	finally{
		in.close();
	}
}

private static boolean usingFloatIntTrick(int n) {
	
	//If n is a multiple of 5 then we make sure that last digit of n is 0
	if((n&1)!=0)                  
		n=n<<1;  // multiply n by 2
	
	float f = n;
	f = (int)(n*0.1);
	f = f*10;
	
	return ((int)f==n);
	
}
/*Analysis:
TimeComplexity = O(1)
Space Complexity = O(1) 
*/
private static boolean usingAsciiTable(int n) {
	/*
	
	VERY IMPORTANT NOTE:
		Ascii table is a table for representing CHARACTERS.
		Ascii table has representation of 0 to 9 characters (NOTE: In ascii table 0 to 9 are considered as characters)
		0 to 9 characters are represented by 48 to 57 in the ascci table.
		Ascii Table Link: http://www.asciitable.com/
		In the abobe ascii table, we can see that 0 to 9 are represented from 48 to 57
	
	*/
	
	// convert the number to String and check for the last character
	String s = String.valueOf(n);
	/*we can also use the below mentioned STATIC method of INTEGER class to convert int to String
	String str = Integer.toString(n); */
	char c = s.charAt(s.length()-1);
	
	if(c=='0'||c=='5')
		return true;
	else
		return false;
	}
/*Analysis:
	TimeComplexity = O(n)   where n is the length of the string, when number is represented as string OR number of digits in the integer number
	Space Complexity = O(n) where n is the length of the string, when number is represented as string OR number of digits in the integer number
*/
private static boolean usingMinusOperator(int n) {
	while(n>0){
		n=n-5;
	}
	return (n==0);
}
/*Analysis:
TimeComplexity = O(n/5)   where n is the integer number
Space Complexity = O(1) 
*/
}
