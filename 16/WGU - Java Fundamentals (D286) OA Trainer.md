### GPT名称：WGU - Java Fundamentals (D286) OA Trainer
[访问链接](https://chat.openai.com/g/g-fvwkSGadU)
## 简介：选择一个难度
![头像](../imgs/g-fvwkSGadU.png)
```text

1. **QUESTION: Print Letter**
   Instructions: Write a program that outputs the pattern shown below ending with a newline. Each line of the pattern contains 5 characters including whitespace.
   OUTPUT:  
        H   H   H   H   HHHHH   H   H   H   H   
   SOLUTION: public class LabProgram { public static void main(String[] args) { System.out.println("H   H"); System.out.println("H   H"); System.out.println("HHHHH"); System.out.println("H   H"); System.out.println("H   H"); } }   
   WALKTHROUGH: Just pay attention to how many characters are required on each line and use System.println();

2. **QUESTION: Multiplication**
   Instructions: For this lab you will use unit testing to check a null setting using assertions. Use the commented template code provided to do the following: Write a program that collects two integer inputs and assigns them to the variables starting_num and multiplier. Multiply starting_num by multiplier and output the result. Repeat this process two more times each time multiplying the previous result by multiplier. The three product outputs should be separated by a whitespace character ending with a newline.
   INPUT: [Starting Number]: 2 [Multiplier]: 5
   OUTPUT: 10 50 250   
   SOLUTION: import java.util.Scanner; public class LabProgram{ public static void main(String[] args){ Scanner scnr = new Scanner(System.in); int startingNum = scnr.nextInt(); int multiplier = scnr.nextInt(); int result = startingNum; String output = ""; for (int i = 0; i < 3; i++){ result *= multiplier; if (i <= 1){ output += result + " "; } else { output += result; } } System.out.println(output); } }   
   WALKTHROUGH: We need input from the user so we need to import java.util.Scanner Create Class public class LabProgram{ Create main method public static void main (String[] args){ Create Scanner object Scanner scnr = new Scanner(System.in); Create variables (4 of them starting number multiplier result output) int starting_num = scnr.NextInt(); int multiplier = scnr.NextInt(); int result = starting_num String output = ""; Create for loop for (i=0; i<[However many iterations the question calls for]; i++){ result *= multiplier; if(i <=1){ output += result + " "; else{ output += result; Print values System.out.println(output);

3. **QUESTION: Wedding Tables**
   Instructions: Write a program that calculates the number of full tables for a wedding event based on the number of expected guests. Each full table will seat 10 wedding guests. Collect one integer input and assign it to the variable guests. Using integer division calculate the total number of tables that will be filled. The variable tableSize has been declared and initialized and the variables guests and tablesFilled have been declared in the template code. Output the number of tables filled ending with a newline. Ensure your program output matches the example formatting below and works for a variety of input values.
   INPUT: 340
   OUTPUT: Tables filled: 34
   INPUT: 349
   OUTPUT: Tables filled: 34
   SOLUTION: import java.util.Scanner; public class LabProgram { public static void main(String[] args) { Scanner scnr = new Scanner(System.in); int tableSize=10; int guests = Integer.valueOf(scnr.nextLine()); int tablesFilled = guests / tableSize; System.out.println("Tables filled: " + tablesFilled); } }   
   WALKTHROUGH: This program will be taking in input so we need to import java.util.Scanner; Create Class public class LabProgram{ Create Method public static void main(String[] args){ Create Scanner tableSize guests and tables filled variables Scanner scnr = New Scanner(System.in); int tables = 10; int guests = Integer.ValueOf(scnr.NextLine); int tablesFilled = guests/tableSize; Output number of tables filled System.out.println("Tables filled: " + tablesFilled);

4. **QUESITON: Name/Salary**
   Instructions: Write a program that takes a full name age and salary as inputs on separate lines. Output a formatted message containing the inputs ending with a newline. Ensure your program output matches the example formatting below and works for a variety of input values.
   INPUT: Pat Ford 35 60000
   OUTPUT: Pat Ford is 35 and makes $60000.
   SOLUTION: import java.util.Scanner; public class LabProgram { public static void main(String[] args) { Scanner scnr = new Scanner(System.in); String name = scnr.nextLine(); String age = scnr.nextLine(); String salary = scnr.nextLine(); System.out.println(name + " is " + age + " and makes $" + salary + "."); } }   
   WALKTHROUGH: Import Necessary Tools To take input from the user import the Scanner class. import java.util.Scanner; Define Your Class Start your Java program by defining its class. public class LabProgram{ Main Method Entry Point Java programs begin their execution in the main method. public static void main(String[] args){ Initialize the Scanner Object Set up the Scanner to read user input. Scanner scnx = new Scanner(System.in); Collect User Input Get the three inputs in sequence: full name age and salary. 5.1. Full Name (String type): String name = scnx.nextLine(); 5.2. Age (Treat as String for simplicity): String age = scnx.nextLine(); 5.3. Salary (Treat as String for simplicity): String salary = scnx.nextLine(); Output the Formatted Message Use concatenation to format the output message. System.out.println(name + "is " + age + "and makes $ " + salary + ".");

5. **QUESTION: Divisible by 3**
   Instructions: A number is divisible by 3 if the sum of its digits is divisible by 3. For example, 153 is divisible by 3 because 1 + 5 + 3 = 9 and 9 is divisible by 3. Write a program that collects three integer inputs representing the place values of a three-digit number. Determines whether the sum of the digits is divisible by 3. If any integer entered is a negative value output Invalid input! Output a formatted message identifying if the three-digit number is divisible by 3 ending with a newline. Ensure your program output matches the example formatting below and works for a variety of input values.
   INPUT: 1 5 3 
   OUTPUT: 153 is divisible by 3! 
   INPUT: 1 0 4 
   OUTPUT: 104 is not divisible by 3! 
   INPUT: 1 -5 3 
   OUTPUT: Invalid input! 
   SOLUTION: import java.util.Scanner; public class LabProgram { public static void main(String[] args) { Scanner scnr = new Scanner(System.in); String one = scnr.nextLine(); String two = scnr.nextLine(); String three = scnr.nextLine(); String sum = one + two + three; if (Integer.valueOf(one) < 0 || Integer.valueOf(two) < 0 || Integer.valueOf(three) < 0){ System.out.println("Invalid input!"); return; } int total = Integer.valueOf(sum); if (total % 3 == 0){ System.out.println(sum + " is divisible by 3!"); } else { System.out.println(sum + " is not divisible by 3!"); } } }   
   WALKTHROUGH: Import Necessary Tools Start by importing the Scanner class to take input from the user. import java.util.Scanner; Define Your Class Define the class in which the program operates. public class LabProgram{ Main Method Entry Point Execution starts in the main method. public static void main(String[] args) { Initialize the Scanner Object Create a Scanner object to read the user's input. Scanner scnr = new Scanner(System.in); Collect User Input Obtain the three integer inputs representing the place values. Hundreds Place: String one = scnr.nextLine(); Tens Place: String two = scnr.nextLine(); Units Place: String three = scnr.nextLine(); Combine the three strings to create the three-digit number. String sum = one + two + three; Check for Invalid Inputs If any of the input numbers are negative it's an invalid input. if (Integer.valueOf(one) < 0 || Integer.valueOf(two) < 0 || Integer.valueOf(three) < 0){ System.out.println("Invalid input!"); return; Determine Divisibility Convert the combined string to an integer. int total = Integer.valueOf(sum); Use the modulo operator to check if the number is divisible by 3. If Divisible: if (total % 3 == 0) { System.out.println(sum + " is divisible by 3!"); If Not Divisible: else { System.out.println(sum + " is not divisible by 3!");

6. **QUESTION: Name**
   Instructions: Write a program that collects a full name as one string input. Format and output the name as shown below: lastInitial. firstName middleInitial. If no middle name was provided format and output the name as shown below: lastInitial. firstName
   INPUT: Pat Silly Doe 
   OUTPUT: D. Pat S. 
   INPUT: Julia Clark 
   OUTPUT: C. Julia 
   SOLUTION: public static void main(String[] args) { Scanner scnr = new Scanner(System.in); String full_name = scnr.nextLine(); String[] parts = full_name.split(" "); String first_name = parts[0]; String last_name = parts[parts.length - 1]; String final_name = last_name.substring(01) + ". " + first_name; if (parts.length >2){ String middle = parts[1].substring(01); final_name += " " + middle + "."; } System.out.println(final_name); } 
   WALKTHROUGH: Initialize the Scanner Object Start by importing the Scanner class to read the user's input. Scanner scnr = new Scanner(System.in); Collect User Input Obtain the full name as a single string input. String full_name = scnr.nextLine(); Split the Name Split the full name into individual name parts (first, middle, last). String[] parts = full_name.split(" "); Assign the first name and last name based on the split string array. String first_name = parts[0]; String last_name = parts[parts.length - 1]; Format Initial Output Start by formatting the name using the first name and the last initial. String final_name = last_name.substring(01) + ". " + first_name; Check for Middle Name If there are more than 2 parts to the name, a middle name exists. Extract its initial and add it to the output. if (parts.length > 2) { String middle = parts[1].substring(01); final_name += " " + middle + "."; Display the Formatted Name Finally print the formatted name based on the input provided. System.out.println(final_name);

7. **QUESTION: Smallest and Sum**
   Instructions: Write a program that collects any number of non-negative integer inputs and calculates the sum of the values. A negative integer should end the input collection and is not part of the sum. Output the smallest non-negative value and the sum of the non-negative input values ending with a newline. Ensure your program output matches the example formatting below and works for a variety of input values.
   INPUT: 15 20 0 3 -1 
   OUTPUT: Smallest: 0 Sum: 38 
   SOLUTION: import java.util.Scanner; public class LabProgram { public static void main(String[] args) { Scanner scnr = new Scanner(System.in); int smallest = Integer.MAX_VALUE; int sum = 0; while (true){ int num = scnr.nextInt(); if (num < 0){ break; } sum += num; if (num < smallest){ smallest = num; } } System.out.println("Smallest: " + smallest); System.out.println("Sum: " + sum); } }   
   WALKTHROUGH: Import Necessary Tools Begin by importing the Scanner class to read the user's input. import java.util.Scanner; Define Your Class Define the class in which your program will operate. public class LabProgram { Main Method Entry Point Every Java program begins execution from the main method. public static void main(String[] args) { Initialize the Scanner Object Instantiate a Scanner object to capture the user's input. Scanner scnr = new Scanner(System.in); Initialize Variables smallest variable will keep track of the minimum input value so initialize it with the highest possible integer value for comparison. int smallest = Integer.MAX_VALUE; sum will keep track of the total sum of the inputs. int sum = 0; Start Input Collection Loop Use an infinite while loop to continuously capture user input until a negative number is entered. while (true) { Collect User Input Inside the loop obtain each number from the user. int num = scnr.nextInt(); Check for Negative Input If the user enters a negative number, break out of the loop. if (num < 0) { break; Calculate Sum Add the current number to the sum. sum += num; Update Smallest Value Compare the current number with smallest. If it's lesser, update smallest. if (num < smallest) { smallest = num; Display Results Once the loop ends (i.e., after getting a negative input) display the smallest value and the sum. System.out.println("Smallest: " + smallest); System.out.println("Sum: " + sum);

8. **QUESTION: Arrays**
   Instructions: Write a program that creates an array to hold three values of type double. The program should collect the three double values as input and store them in the array. Then calculate the average value of the array. Output the array values and calculated average value ending with a newline. Ensure your program output matches the example formatting below and works for a variety of input values.
   INPUT: 10.0 10.5 11.0
   OUTPUT: Array items: 10.0 10.5 11.0 Average: 10.5 
   SOLUTION: import java.util.Scanner; public class LabProgram { public static void main(String[] args) { Scanner scnr = new Scanner(System.in); double[] values = new double[3]; for (int i = 0; i < 3; i++) { values[i] = scnr.nextDouble(); } double sum = 0.0; for (double value : values) { sum += value; } double average = sum / 3.0; System.out.print("Array items: "); for (int i = 0; i < 3; i++) { System.out.print(values[i]); if (i < 2) { System.out.print(" "); } } System.out.println();
```