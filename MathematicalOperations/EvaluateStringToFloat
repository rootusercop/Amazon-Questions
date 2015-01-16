/*
Question: Write atof in Java, which converts a string representation of a float (like "342.18E-10") 
to an actual float without using any built-in parsing functions.

For Example: Meaning of  4.21E10 meaning ?
Ans: 4.21 x10^10 (Answer Source: https://answers.yahoo.com/question/index?qid=20100915180740AALkWaT)


Source: http://www.careercup.com/question?id=4901629824335872	
*/

package EvaluateMathematicalExpression;

public class EvaluateStringToFloat {
	String str;
	float result;
	
	public EvaluateStringToFloat(String s) throws Exception{
		this.str = s.trim();
		result = solve(str);
	}
	
	public float solve(String str) throws Exception{
		int indexOfE = str.indexOf('E');
		if(indexOfE == -1)
			indexOfE= str.indexOf('e');
		if(indexOfE == -1){
			return withoutE(str);
		}else{
			return (float) (withoutE(str.substring(0, indexOfE))*
					Math.pow(10, withoutE(str.substring(indexOfE+1))));
		}
	}
	

	private float withoutE(String s) throws Exception{
		if(s.charAt(0) == '-'){
			return -withoutE(s.substring(1));
		}
		int indexOfPeriod = s.indexOf('.');
		if(indexOfPeriod == -1){
			return makeInt(s);
		}else{
			float beforePeriod = makeInt(s.substring(0,indexOfPeriod));
			float afterPeriod = makeInt(s.substring(indexOfPeriod+1));
			float temp = afterPeriod;
			int countDigit = 0;
			while(temp > 10){
				countDigit ++;
				temp /=10;
			}
			countDigit++;
			
			return (float)(beforePeriod + Math.pow(10, -countDigit)*afterPeriod);
		}
		
	}
	

	private float makeInt(String s) throws Exception{
		if(s.length() == 0)
			return 0;
		float res = 0f;
		for (int i = 0; i < s.length(); i++) {
			// for example 234 = ((2*10)+3)*10+4;
			res = res*10 + (s.charAt(i)-'0');     // use the ASCII table. For Example: '3'-'0' gives numeric 3
		}
		return res;
	}
	
	public static void main(String[] args) throws Exception {
		EvaluateStringToFloat a = new EvaluateStringToFloat("3.2");
		System.out.println(a.result);
		EvaluateStringToFloat b = new EvaluateStringToFloat("342.18E-10");
		System.out.println(b.result);
		// Example of float
		float f=(float) 342.18E-10;
		System.out.println(f);
	}
}
