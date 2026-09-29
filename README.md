⭐ Pattern 20 – Symmetric Star Pattern in C++

A C++ program that generates a symmetric star pattern using nested loops. The pattern increases the number of stars toward the center and then decreases them, while the spaces between the two star groups follow the opposite pattern.

📌 Overview

The program takes an integer n and generates a pattern with:

2 × n - 1 rows

For each row, two groups of stars are printed with a variable number of spaces between them.

For n = 4, the output is:

*      *
**    **
***  ***
********
***  ***
**    **
*      *

The program supports multiple test cases.

✨ Features
Generates a symmetric star pattern.
Uses nested for loops.
Dynamically calculates the number of stars.
Dynamically increases and decreases the space gap.
Produces 2n - 1 rows.
Supports multiple test cases.
Demonstrates conditional logic inside loops.
🛠️ Technologies Used
Technology	Purpose
C++	Programming language
iostream	Input and output
Nested Loops	Pattern generation
Conditional Statements	Controlling stars and spaces
📝 Problem Statement

Given an integer n, print a symmetric star pattern consisting of 2n - 1 rows.

The number of stars:

Increases from 1 to n.
Then decreases from n - 1 back to 1.

The number of spaces:

Starts at 2n - 2.
Decreases by 2 until the center.
Then increases by 2.
Example

For n = 4:

*      *
**    **
***  ***
********
***  ***
**    **
*      *
🧠 Approach
1. Calculate Initial Spaces

The pattern starts with:

int spaces = 2 * n - 2;

For n = 4:

spaces = 6
2. Calculate Number of Stars

Initially, the number of stars is equal to the current row:

int stars = i;

After reaching the middle row, the number of stars decreases:

if (i > n)
    stars = 2 * n - i;

This produces:

1
2
3
4
3
2
1
3. Update Spaces

Before reaching the center, spaces decrease:

if (i < n)
    spaces -= 2;

After the center, spaces increase:

else
    spaces += 2;

This creates the required symmetry.

💻 Source Code
#include <iostream>
using namespace std;

void Pattern20(int n) {
    int spaces = 2 * n - 2;

    for (int i = 1; i <= 2 * n - 1; i++) {

        int stars = i;

        if (i > n)
            stars = 2 * n - i;

        // Stars
        for (int j = 1; j <= stars; j++) {
            cout << "*";
        }

        // Spaces
        for (int j = 1; j <= spaces; j++) {
            cout << " ";
        }

        // Stars
        for (int j = 1; j <= stars; j++) {
            cout << "*";
        }

        cout << endl;

        // Update spaces
        if (i < n)
            spaces -= 2;
        else
            spaces += 2;
    }
}

int main() {
    int t;
    cin >> t;

    for (int i = 0; i < t; i++) {
        int n;
        cin >> n;
        Pattern20(n);
    }

    return 0;
}
📥 Example Input
1
4
📤 Example Output
*      *
**    **
***  ***
********
***  ***
**    **
*      *
▶️ How to Run
1. Clone the repository
git clone <repository-url>
cd <repository-folder>
2. Compile the program
g++ main.cpp -o main
3. Run the program
./main

Windows: Use main.exe instead of ./main.

📚 Learning Concepts

This program demonstrates:

Nested for loops
Pattern printing
Symmetric pattern construction
Conditional statements
Dynamic star calculation
Dynamic space calculation
Increasing and decreasing sequences
Functions in C++
Multiple test cases
Console input/output
⏱️ Complexity Analysis

For an input n:

Time Complexity: O(n²)
Auxiliary Space: O(1)

The pattern contains 2n - 1 rows, and each row requires a number of operations proportional to n.

📸 Screenshot

Add your program output screenshot to:

screenshots/output.png

Then include it in the README:

<img width="82" height="151" alt="Screenshot 2026-09-29 at 9 28 57 PM" src="https://github.com/user-attachments/assets/910f5b1f-8c0d-4481-97c9-97f9868d6a5d" />

Recommended project structure:

Pattern20/
│
├── main.cpp
├── README.md
└── screenshots/
    └── output.png
👤 Author

Rishab Raj Chourasia

C++ | Data Structures & Algorithms | Problem Solving
