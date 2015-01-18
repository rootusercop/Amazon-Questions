
/*
 * Question: Inplace reverse a sentence 

You given a sentence of english words and spaces between them. 
Nothing crazy: 
1) no double spaces 
2) no empty words 
3) no spaces at the ends of a sentence


void inplace_reverse(char* arr, int length) {
    // your solution
}
Example: 
input "I wish you a merry Christmas" 
output "Christmas merry a you wish I" 

Constrains: O(1) additional memory



Source: http://www.careercup.com/question?id=5717567253512192

Algorithm: 1. Reverse the words in the sentence
		   2. Reverse the sentence
		   
Example: 
Input: I wish you a merry Christmas
step 1 . I hisw uoy a yrrem samtsirhC 
step 2 . Christmas merry a you wish I

*/



package reverseWordsInSentenseInConstantMemory;

import java.util.Scanner;

public class UsingReverseWordsFunction {
public static void main(String[] args) {
	Scanner in = new Scanner(System.in);
	try{
		System.out.println("Enter the sentence whose words needs to be reversed");
		char[] s = in.nextLine().toCharArray();
		s=reverseSentence(s);
		System.out.println(String.valueOf(s));
		
	}finally{
		in.close();
	}
}
/*  Preconditions of the input string given in the question:
1) no double spaces 
2) no empty words 
3) no spaces at the ends of a sentence
*/
public static void reverseWord(char[] s,int start, int end){
	for(;start<end;start++,end--){
		// Swap start and end characters In Place
	    s[start] = (char)(s[start]^s[end]);
	    s[end] = (char)(s[start]^s[end]);
	    s[start] = (char)(s[start]^s[end]);
	}
}
public static char[] reverseSentence(char[] s){
	int start = 0;
	int end = 0;
	for(int i=0;i<s.length;i++){

		if(s[i]==' '){  // either when we get empty space
			end=i-1;
			reverseWord(s, start, end);
			start=i+1;
		}
		if(i==(s.length-1)){  // If we reach the end of the string
			end=i;
			reverseWord(s, start, end);
		}
	}
	reverseWord(s, 0, s.length-1);
	return s;
	}
}
/*
 * Analysis:
 *       Time Complexity = O(n) where n = length of the string
 *       Space Complexity = O(1)
 */
