
/*
 * 
 * 
 Question:  Given a string, how do we check if any anagram of it can be a palindrome?
Question Source: http://comproguide.blogspot.com/2013/11/checking-if-any-anagram-of-given-string.html

Algorithm:
For example let us consider the string "AAC". An anagram of it is "ACA" which is a palindrome.
 We have to write a method which takes a string and outputs true if we can form a palindrome 
 from any anagram of the given string. Otherwise outputs false.

We can immediately think of a solution where we can generate all anagrams of the given string
 and check if there is any palindrome exists. But this approach is very lengthy and has exponential
  time complexity (O(n!)).

The key to solve this problem efficiently is to understand how a palindrome is formed. We all know
 that a palindrome reads the same when you read from left to right or right to left. 

A palindrome can be broken into two halves. where in the first half is the reverse of second half. 
In case of odd length of strings, we have to ignore the middle character.

So for every character in the first half, there is a corresponding matching character in the second 
half. This indicates that all the characters in a string must occur even number of times except for 
one which appears in the middle of the string.

Hence if we check if there is at most one character with odd occurrences in the string we can say that
 we can form a palindrome from any anagram.
Here is the Java code which implements this algorithm. For simplicity, I assumed that the input string 
contains only lowercase English alphabets.
 */


package AnyAnagramPalindrome;


public class isAnyAnagramPalindrome{
    public static void main(String[] args){
    System.out.println("Check whether any anagram of this string is palindrome: "+checkIfAnyAnagramPalindrome("aac"));    
    }
    public static boolean checkIfAnyAnagramPalindrome(String s){
        int[] count = new int[26]; // assume that all the characters are lowercase. 'a' starts from 97 in ASCII table
        for(int i=0;i<s.length();i++){
            count[s.charAt(i)-97]++;
        }
        int oddCount=0;
        for(int i=0;i<count.length;i++){
            if(count[i]%2==1)
                oddCount++;
        }
        if(oddCount<2)  // oddCount of the characters should be ATMOST 1
            return true;
        else
            return false;
    }
}
/*
 * Analysis:
 * Time Complexity = O(n) where n = length of the string
 * Space Complexity = O(1)
 */
