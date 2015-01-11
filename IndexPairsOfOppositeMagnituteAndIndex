/*
Question: You are given two integer arrays A and B . 

1<=i<=len(A) so i is iterator of array A 
1<=j<=len(B) so j is iterator of array B 

find all the pairs(i,j) such that : i < j and A[i]>B[j]
		
Question Source: http://www.careercup.com/question?id=6260358392053760

*/
package IndexPairsOfOppositeMagnituteAndIndex;

import java.util.Scanner;

public class UsingComparison {
public static void main(String[] args) {
	Scanner in = new Scanner(System.in);
	try{
		System.out.println("Enter the number of elements in the first array");
		int m = in.nextInt();
		int[] a= new int[m];
		System.out.println("Enter the elements of the first array");
		for(int i=0;i<m;i++)
			a[i]=in.nextInt();
		System.out.println("Enter the number of elements in the second array");
		int n = in.nextInt();
		int[] b= new int[n];
		System.out.println("Enter the elements of the second array");
		for(int i=0;i<n;i++)
			b[i]=in.nextInt();
		System.out.println("Pairs such that i<j and a[i]>b[j] are: ");
		oppPairs(a,b);
	}
	finally{
		in.close();
	}
}

private static void oppPairs(int[] a, int[] b) {
	for(int i=0;i<a.length;i++){
		for(int j=i+1;j<b.length;j++){
			if(a[i]>b[j])
				System.out.println("Pair: i="+i+", a[i]= "+a[i]+", j= "+j+", b[j]= "+b[j]);
		}
	}
}
}
/*
Analysis:
	Time Complexity = O(m*n)
	Space Complexity = (1)
	
OK, as many of us concluded it's impossible to construct algorithm for this problem with time complexity better
than O(N^2) [in worst case]. What to do when interviewer still expects O(N) solution for 
worst case [where O(N^2) pairs has to be reported]? 
1) Provide a formal proof that this is impossible in a classic computation model (turing machine)
 [providing an argument about # of pairs is enough]. 
2) Tell the interviewer that we're engineers and we are going to solve this no matter what. Show what 
constraints we can change to provide O(N) time complexity or better. 
For instance we can escape from classical sequential model and design a system (either design a new
ardware system or build a distributed systems with many processors/computers) - where we can leverage 
O(N) processors with very efficient communication between each pair of processors. In this case O(N) solution 
is possible. We can find O(N^2) pairs and report them in O(N) time into a distributed storage across our O(N) nodes. 
If I was an interviewer at Amazon I'd be happy to hear such answer.
*/
