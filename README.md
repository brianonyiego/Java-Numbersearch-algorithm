# Java-Numbersearch-algorithm
# NumberSearch Program

## Overview

The `NumberSearch` program is a simple Java application that demonstrates a binary search algorithm to find a specified number within a given range (0 to 8). The program includes indentation to visually represent the recursion depth of the search process.

## Features

- Binary search implementation to locate a number within a specified range.
- Recursively narrows down the search range until the number is found or the range cannot be further divided.
- Visual indentation to show recursion levels.

## How it Works

1. **Input**: The user is prompted to enter a number between 0 and 8.
2. **Binary Search**:
   - The program calculates the middle value (`midVal`) of the current range.
   - It prints `midVal` with the current indentation.
   - If `number` equals `midVal`, the program prints `a` and exits.
   - If `number` is less than `midVal`, the program prints `b` and recursively searches the lower half of the range.
   - If `number` is greater than `midVal`, the program prints `c` and recursively searches the upper half of the range.
3. **Output**: Each recursion step prints the mid value and corresponding letter (`a`, `b`, or `c`), and the program finally prints `d` at each step of recursion unwinding.

## Code Description

### Main Class: `NumberSearch`

#### Methods

- `public static void findNumber(int number, int lowVal, int highVal, String indentAmt)`
  - **Parameters**:
    - `number`: The target number to find.
    - `lowVal`: The lower bound of the current search range.
    - `highVal`: The upper bound of the current search range.
    - `indentAmt`: A string representing the current indentation level for visualizing recursion.
  - **Logic**:
    - Calculates the middle value of the current range.
    - Compares `number` with `midVal` and decides whether to search in the lower or upper half of the range, or if the number has been found.
    - Prints the appropriate character (`a`, `b`, or `c`) and the value of `midVal`.
    - Recursively calls itself with the updated range and increased indentation if necessary.
    - Prints `d` when the recursion unwinds.

```java
public class NumberSearch {
    public static void findNumber(int number, int lowVal, int highVal, String indentAmt) {
        int midVal;

        midVal = (highVal + lowVal) / 2;
        System.out.print(indentAmt);
        System.out.print(midVal);

        if (number == midVal) {
            System.out.println(" a");
        }
        else {
            if (number < midVal) {
                System.out.println(" b");
                findNumber(number, lowVal, midVal, indentAmt + " ");
            }
            else {
                System.out.println(" c");
                findNumber(number, midVal + 1, highVal, indentAmt + " ");
            }
        }

        System.out.println(indentAmt + "d");
    }
}
```

- `public static void main(String[] args)`
  - **Logic**:
    - Reads an integer input from the user.
    - Calls `findNumber` with the user input, initial range (0 to 8), and an empty string for indentation.

```java
public static void main(String[] args) {
    Scanner scnr = new Scanner(System.in);
    int number;

    number = scnr.nextInt();
    findNumber(number, 0, 8, "");
}
```

### Example Execution

For a given number `number` (e.g., `number = 3`):

1. User inputs the number `3`.
2. The initial call is `findNumber(3, 0, 8, "")`.
3. The program prints the steps of the search, showing the mid values and whether it is searching in the lower or upper half.

## How to Run

1. Ensure you have Java installed on your machine.
2. Copy the code into a file named `NumberSearch.java`.
3. Compile the program using the command:
   ```bash
   javac NumberSearch.java
   ```
4. Run the program using the command:
   ```bash
   java NumberSearch
   ```
5. Enter a number between 0 and 8 when prompted.

## Sample Output

If the user inputs `3`, the program might output:

```
4 b
 2 c
  3 a
  3 d
 2 d
4 d
```

This output indicates the steps taken by the binary search to find the number `3`, showing the recursive calls and the process of narrowing down the search range.

## License

This code is provided for educational purposes and is free to use and modify.

---
