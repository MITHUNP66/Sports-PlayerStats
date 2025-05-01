# Sports-PlayerStats
A simple Java-based console application demonstrating the use of object-oriented programming concepts such as inheritance, encapsulation, and input validation. The program allows users to create and manage basic profiles for two types of players — Cricket and Football — capturing both shared and sport-specific details.

code:
package com.javeprograming;


import java.util.Scanner;

class player {
	private String name; 
	private int age;
	private double height;
	private String country;
	
	public player(String name,int age,double height,String country) {
		this.name=name;
		this.age=age;
		this.height=height;
		this.country=country;
	}
	public void displayinfo() {
		System.out.println("name :"+name);
		System.out.println("age :"+age);
		System.out.println("height :"+height);
		System.out.println("country :"+country);
	}
	public String getname() {
		return name;
	}
	public int getage() {
		return age;
	}
	public double getheight() {
		return height;
	}
	public String getcountry() {
		return country;
	}
}
class cricket extends player{
	int wickets,runs;
	
	public cricket(String name,int age,double height,String country,int wickets,int runs) {
		super(name,age,height,country);
		this.wickets=wickets;
		this.runs=runs;
	}
	public void displaycricketstats() {
System.out.println("no of wickets  "+ wickets);
System.out.println("no. of runs  "+runs);

	}

}
class football extends player{
	int goals;
	String position;
	
	public  football(String name,int age,double height,String country,int goals,String position) {
		super(name,age,height,country);
		this.goals=goals;
		this.position=position;
	}
	public void displayfootball() {
		System.out.println(" no. of goals :"+ goals);
		System.out.println("in position :"+ position);
	}
}
public class classplayer {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
Scanner sc=new Scanner(System.in);
System.out.println("enter the details of cricket");
System.out.println("enter the name of the player");
System.out.print("name :");
String cricketname=sc.nextLine();
System.out.println("enter the age of the player");
System.out.print("age :");
int cricketage=sc.nextInt();
System.out.println("enter the height of the player");
System.out.print("height :");
double cricketheight=sc.nextDouble();
System.out.println("enter the country of the player");
System.out.print("country :");
String cricketcountry=sc.next();
System.out.println("enter the runs of the player");
System.out.print("runs :");
int cricketruns=sc.nextInt();
System.out.println("enter the wickets of the player");
System.out.print("wickets :");
int cricketwickets=sc.nextInt();
System.out.println();
//football class;
System.out.println(" enter the football details");
System.out.println("enter the name of the player");
System.out.print("name :");
String footballname=sc.next();
System.out.println("enter the age of the player");
System.out.print("age :");
int footballage=sc.nextInt();
System.out.println("enter the height of the player");
System.out.print("height :");
double footballheight=sc.nextDouble();
System.out.println("enter the country of the player");
System.out.print("country :");
String footballcountry=sc.next();
System.out.println("enter the goals of the player");
System.out.print("goals :");
int footballgoals=sc.nextInt();
System.out.println("enter the position of the player");
System.out.print("poistions :");
String footballposition=sc.next();
System.out.println();
cricket c=new cricket(cricketname,cricketage,cricketheight,cricketcountry,cricketruns,cricketwickets);
football f=new football(footballname,footballage,footballheight,footballcountry,footballgoals,footballposition);

c.displayinfo();
c.displaycricketstats();

System.out.println();
f.displayinfo();
f.displayfootball();
System.out.println();

	}

}

