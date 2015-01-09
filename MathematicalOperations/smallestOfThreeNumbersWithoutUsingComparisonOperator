
/*
Question: Smallest of three integers without comparison operators (> or <, however == is allowed)
Source: http://www.geeksforgeeks.org/smallest-of-three-integers-without-comparison-operators/
	http://www.geeksforgeeks.org/compute-the-minimum-or-maximum-max-of-two-integers-without-branching/
*/
package smallestOfThreeNumbersWithoutUsingComparisonOperator;

import java.util.Scanner;

public class UsingDifferentAlgorithms {
public static void main(String[] args) {
	Scanner in = new Scanner(System.in);
	try{
		System.out.println("Enter the three elements to check for min and max among them WITHOUT using comparison operator");
		int a = in.nextInt();
		int b=in.nextInt();
		int c = in.nextInt();
		System.out.println("Max between first two numbers: "+max(a, b));
		System.out.println("Max between last two numbers: "+max(b, c));
		System.out.println("Minumum number using REPETATIVE SUBSTRACTION algorithm: "+usingRepetativeSubstraction(a,b,c));
		System.out.println("Minumum number using BITWISE SHIFT algorithm: "+usingBitwiseShift(a,b,c));
		System.out.println("Minumum number using DIVISION algorithm: "+usingDivision(a,b,c));
	}
	finally{
		in.close();
	}
}

private static int usingDivision(int a, int b, int c) {
	/*To change this program to get the max, just change the comparison sign from '<' to '>'
	*/
	if(a/b==0){
		if(a/c==0)
			return a;
		else
			return c;
	}
	if(b/c==0){
		if(b/a==0)
			return b;
		else
			return a;
	}
	if(c/a==0){
		if(c/b==0)
			return c;
		else
			return b;
	} 
	return a;                        // otherwise all three numbers are equal. Hence return any one of the three numbers(for example: a=5,b=5,c=5 then min(a,b,c)=a OR b OR c)
} 
/*
Analysis:
	Time Complexity = O(1)
	Space Complexity = O(1)
*/

private static int usingBitwiseShift(int a, int b, int c) {
	return min(a,min(b,c));
}

private static int min(int b, int c) {
	return c+((b-c)&((b-c)>>31));
}
private static int max(int b, int c) {
	return b-((b-c)&((b-c)>>31));
}

/*
Analysis:
	Time Complexity = O(1)
	Space Complexity = O(1)
*/

private static int usingRepetativeSubstraction(int a, int b, int c) {
	int count = 0;
	while(a>0 && b>0 && c>0){
		a--;
		b--;
		c--;
		count++;
	}
	return count;
}
/*
Analysis:
	Time Complexity = O(min(a,b,c))
	Space Complexity = O(1)
*/
}
