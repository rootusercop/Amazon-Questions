package FindLargestAreaRectangleInHistogram;

import java.util.Scanner;
import java.util.Stack;

public class UsingStackToStoreIndices {
public static void main(String[] args) {
	Scanner in = new Scanner(System.in);
	try{
		System.out.println("Enter the height of each index in the histogram");
		System.out.println("Enter the size of the array");
		int n = in.nextInt();
		int[] hist = new int[n];
		System.out.println("Enter the height of the histogram rectangles");
		for(int i=0;i<hist.length;i++)
			hist[i]=in.nextInt();
		System.out.println("The maximum area rectangle in the histogram is: "+largestRectangleArea(hist));
	}
	finally{
		in.close();
	}
}

public static int largestRectangleArea(int[] height) {
    if ( height==null||height.length==0){
        return 0;
    }
    
    Stack<Integer> stack=new Stack<Integer>();
    
    int max=0;
    int i=0;
    
    while(i<height.length){
        
        
        if (stack.isEmpty()||height[i]>=height[stack.peek()]){
            stack.push(i);
            i++;
        }
        else{
            
            int h=height[stack.pop()];
            int wid=stack.isEmpty()?i:i-stack.peek()-1;
            max=Math.max(h*wid, max);
        }
        
    }
    
    while (!stack.isEmpty()){
        int h=height[stack.pop()];
        int wid=stack.isEmpty()?i:i-stack.peek()-1;
        max=Math.max(h*wid, max);
    }
    
    return max;
}
}
