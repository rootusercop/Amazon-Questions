package divideandconquer;

import java.util.ArrayList;
import java.util.Comparator;
import java.util.Iterator;
import java.util.List;
import java.util.PriorityQueue;
import java.util.Scanner;

public class KClosestPointsForGivenPoint {
public static void main(String[] args) {
	List<Point> points = new ArrayList<Point>();
	for(int i=10;i>0;i--){
		points.add(new Point(i,i));
	}
	
	Scanner in = new Scanner(System.in);
	int n=0;
	try{
		System.out.println("Enter the number of points you need to analyze");
		n=in.nextInt();
	PriorityComparator cmp = new PriorityComparator();
	PriorityQueue<Point> maxHeap = new PriorityQueue<>(n, cmp);
	int size = points.size();
	int i=0;
	for(i=0;i<Math.min(size, n);i++){
		maxHeap.add(points.get(i));
	}
	
	for(int j=i;j<size;j++){
		if(cmp.compare(maxHeap.peek(), points.get(j)) < 0){
			maxHeap.poll();
			maxHeap.add(points.get(j));
		}
	}
	
	Iterator<Point> iter = maxHeap.iterator();
	while(iter.hasNext()){
		Point.printPoint(iter.next());
	}
	
	
	}finally{
		in.close();
	}
	
}
}
class Point{
	int x_co;
	int y_co;
	
	public Point(int x_co, int y_co) {
		super();
		this.x_co = x_co;
		this.y_co = y_co;
	}
	
	public int getX_co() {
		return x_co;
	}
	public void setX_co(int x_co) {
		this.x_co = x_co;
	}
	public int getY_co() {
		return y_co;
	}
	public void setY_co(int y_co) {
		this.y_co = y_co;
	}
	
	public static double calculateDistance(Point x, Point y){
		return Math.sqrt((y.x_co-x.x_co)*(y.x_co-x.x_co) + (y.y_co-x.y_co)*(y.y_co-x.y_co));
	}
	
	public static void printPoint(Point p){
		System.out.print("x-coordinate = "+p.x_co+", y-coordinate = "+p.y_co);
		System.out.println();
	}
	
}
class PriorityComparator implements Comparator<Point>{

	@Override
	public int compare(Point p1, Point p2) {
		Double distanceFromP1 = Point.calculateDistance(p1, new Point(5,5));
		Double distanceFromP2 = Point.calculateDistance(p2, new Point(5,5));
		
		return distanceFromP2.compareTo(distanceFromP1);
	}
	
	
}

