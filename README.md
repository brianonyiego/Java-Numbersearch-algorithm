# Java-Numbersearch-algorithm
NumberSearch Program
Overview
The NumberSearch program is a simple Java application that demonstrates a binary search algorithm to find a specified number within a given range (0 to 8). The program includes indentation to visually represent the recursion depth of the search process.

Features
Binary search implementation to locate a number within a specified range.
Recursively narrows down the search range until the number is found or the range cannot be further divided.
Visual indentation to show recursion levels.
How it Works
Input: The user is prompted to enter a number between 0 and 8.
Binary Search:
The program calculates the middle value (midVal) of the current range.
It prints midVal with the current indentation.
If number equals midVal, the program prints a and exits.
If number is less than midVal, the program prints b and recursively searches the lower half of the range.
If number is greater than midVal, the program prints c and recursively searches the upper half of the range.
Output: Each recursion step prints the mid value and corresponding letter (a, b, or c), and the program finally prints d at each step of recursion unwinding.
Code Description
Main Class: NumberSearch
Methods
public static void findNumber(int number, int lowVal, int highVal, String indentAmt)

Parameters:
number: The target number to find.
lowVal: The lower bound of the current search range.
highVal: The upper bound of the current search range.
indentAmt: A string representing the current indentation level for visualizing recursion.
Logic:
Calculates the middle value of the current range.
Compares number with midVal and decides whether to search in the lower or upper half of the range, or if the number has been found.
Prints the appropriate character (a, b, or c) and the value of midVal.
Recursively calls itself with the updated range and increased indentation if necessary.
Prints d when the recursion unwinds.
public static void main(String[] args)

Logic:
Reads an integer input from the user.
Calls findNumber with the user input, initial range (0 to 8), and an empty string for indentation.
Example Execution
For a given number number (e.g., number = 3):

User inputs the number 3.
The initial call is findNumber(3, 0, 8, "").
The program prints the steps of the search, showing the mid values and whether it is searching in the lower or upper half.
How to Run
Ensure you have Java installed on your machine.
Copy the code into a file named NumberSearch.java.
Compile the program using the command:
bash
Copy code
javac NumberSearch.java
Run the program using the command:
bash
Copy code
java NumberSearch
Enter a number between 0 and 8 when prompted.
Sample Output
If the user inputs 3, the program might output:

css
Copy code
4 b
 2 c
  3 a
  3 d
 2 d
4 d
This output indicates the steps taken by the binary search to find the number 3, showing the recursive calls and the process of narrowing down the search range.

License
This code is provided for educational purposes and is free to use and modify.
