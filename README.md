# Student class
import java.text.DecimalFormat;
public class Student {
	   private String firstName, lastName;
	   private Address homeAddress, schoolAddress;
	   private double testOne,testTwo,testThree, average;

	   //-----------------------------------------------------------------
	   //  Constructor: Sets up this student with the specified values.
	   //-----------------------------------------------------------------
	   public Student(String first, String last, Address home,
	                  Address school, double test1, double test2, double test3)
	   {
	      firstName = first;
	      lastName = last;
	      homeAddress = home;
	      schoolAddress = school;
	      testOne=test1;
	      testTwo=test2;
	      testThree=test3;
		  average = 0;
	   }

	   public Student(String first, String last, Address home, Address school)
	   {
	      firstName = first;
	      lastName = last;
	      homeAddress = home;
	      schoolAddress = school;
	      testOne = 0;
	      testTwo = 0;
	      testThree = 0;
		  average = 0;
	   }

	   //-----------------------------------------------------------------
	   //  Returns a string description of this Student object.
	   //-----------------------------------------------------------------
	   
	   public void setTestScoreOne(double score)
	   {
			testOne = score;
	   }

	   public void setTestScoreTwo(double score)
	   {
			testTwo = score;
	   }

	   public void setTestScoreThree(double score)
	   {
			testThree = score;
	   }

	   public double getTestScore(int select)
	   {
	       switch(select)
		   {
	           case 1:
	               return testOne;
	           case 2 :
	               return testTwo;
	           case 3 :
	               return testThree;  
	           default:
	               return 0;
	   		}
	   }

	   public double average()
	   {
			
	        average = (testOne + testTwo + testThree) / 3;
	       
	       return average;
	   }

	   public double getAverage()
	   {
			return average;
	   }

	   public String getName(){
	       return firstName;
	   }

	   public String toString()
	   {
	      String result;

	      result = firstName + " " + lastName + "\n";
	      result += "Home Address:\n" + homeAddress + "\n";
	      result += "School Address:\n" + schoolAddress;
	      result += "\nTest Score: " + "Test 1 = " + getTestScore(1);
	      result += ", Test 2 = " + getTestScore(2);
	      result += ", Test 3 = " + getTestScore(3);
		  result += "\nAverage: " + getAverage();
		  
	      return result;
	   }
     
# main class
Address school = new Address("800 Lancaster Ave.", "Villanova", "PA", 19085);
        Address jHome = new Address("21 Jump Street", "Blacksburg", "VA", 24551);
        Student john = new Student("John", "Smith", jHome, school, 90,70,80);
        Address mHome = new Address("123 Main Street", "Euclid", "OH", 44132);
        Student marsha = new Student("Marsha", "Jones", mHome, school,90.3,90,70);
		
		System.out.println(john.average());
		System.out.println(john);
		System.out.println();

		marsha.setTestScoreOne(75.6);
		marsha.setTestScoreTwo(99.3);
		marsha.setTestScoreThree(84);
		System.out.println(marsha.average());
		System.out.println(marsha);	
