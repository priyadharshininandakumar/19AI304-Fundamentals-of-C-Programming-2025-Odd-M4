# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
## 7. Implementation of Functions.
## 8. Implementation of passing parameters.
# Ex.No:16
  Implement a C program to read a date in the format DD/MM/YYYY and determine whether the entered date is valid. The program should check the correctness of the day, month, and year, including leap year calculations for February.
# Date : 26/02/2026
# Aim:
 To implement a C program that validates a user-entered date using a function without parameters and without return value, ensuring the correctness of day, month, year, and leap year conditions.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
### Call the function `validateDate()`.
### Inside `validateDate()` function:
### Step 4: 
  Declare variables `dd`, `mm`, and `yy`.
### Step 5: 
  Ask the user to enter a date in `DD/MM/YYYY` format.
### Step 6: 
  Read the date values using `scanf`.
### Step 7: 
  Check if the year is between **1900 and 9999**.
 - If the year is invalid, display **"Year is not valid"** and stop further checks.
### Step 8: 
  Check if the month is between **1 and 12**.
- If the month is invalid, display **"Month is not valid"** and stop further checks.
### Step 9: 
  If the month has **31 days**, check if the day is between **1 and 31**.
### Step 10: 
  If the month has **30 days**, check if the day is between **1 and 30**.
### Step 11: 
  If the month is **February**:
  - Check if the day is between **1 and 28**, or if the day is **29**, verify if it's a **leap year**.
### Step 12: 
  If any valid condition is satisfied, display **"Date is valid."**
### Step 13: 
  Otherwise, display **"Date is invalid."**
### Step 14: 
  Stop
# Program:
```
#include <stdio.h>
int isLeapYear(int year) {
    if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0))
        return 1;
    return 0;
}
int main() {
    int day, month, year;
    int valid = 1;
    printf("Enter date (DD/MM/YYYY): ");
    scanf("%d/%d/%d", &day, &month, &year);
    if (year < 1) {
        valid = 0;
    }
    if (month < 1 || month > 12) {
        valid = 0;
    }
    if (valid) {
        if (month == 2) {
            if (isLeapYear(year)) {
                if (day < 1 || day > 29)
                    valid = 0;
            } else {
                if (day < 1 || day > 28)
                    valid = 0;
            }
        }
        else if (month == 4 || month == 6 || month == 9 || month == 11) {
            if (day < 1 || day > 30)
                valid = 0;
        }
        else {
            if (day < 1 || day > 31)
                valid = 0;
        }
    }
    if (valid)
        printf("The entered date is VALID.\n");
    else
        printf("The entered date is INVALID.\n");
    return 0;
}
```
# Output:
<img width="961" height="443" alt="Screenshot 2026-03-25 084610" src="https://github.com/user-attachments/assets/61454eea-f62f-427e-bd6f-dcc9989e6430" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
# Ex.No:17
  Develop a C program to read two numbers from the user and determine the maximum and minimum values. Use user-defined functions with arguments and return values—one function to find the maximum (max()) and another to find the minimum (min()).
# Date : 26/02/2026
# Aim:
 To develop a C program that uses functions with parameters and return values to compute and display the maximum and minimum of two user-entered numbers.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare variables `num1`, `num2`, `maximum`, and `minimum`.
### Step 4: 
  Ask the user to enter two numbers.
### Step 5: 
  Read the numbers using `scanf`.
### Step 6: 
  Call the function `max(num1, num2)`.
### Step 7: 
  Inside function `max(num1, num2)`:
- **Step 7.1:** Receive two integer arguments.  
- **Step 7.2:** Compare the two numbers.  
- **Step 7.3:** If `num1 > num2`, return `num1`.  
- **Step 7.4:** Otherwise, return `num2`.
### Step 8: 
  Store the returned value in `maximum`.
### Step 9: 
  Call the function `min(num1, num2)`.
### Step 10: 
  Inside function `min(num1, num2)`:
- **Step 10.1:** Receive two integer arguments.  
- **Step 10.2:** Compare the two numbers.  
- **Step 10.3:** If `num1 > num2`, return `num2`.  
- **Step 10.4:** Otherwise, return `num1`.
### Step 11: 
  Store the returned value in `minimum`.
### Step 12: 
  Display the returned maximum and minimum values.
### Step 13: 
  Stop
# Program:
```
#include <stdio.h>

// Function to find maximum
int max(int a, int b) {
    if (a > b)
        return a;
    else
        return b;
}

// Function to find minimum
int min(int a, int b) {
    if (a < b)
        return a;
    else
        return b;
}

int main() {
    int num1, num2, maximum, minimum;

    // Input two numbers
    printf("Enter two numbers: ");
    scanf("%d %d", &num1, &num2);

    // Function calls
    maximum = max(num1, num2);
    minimum = min(num1, num2);

    // Display results
    printf("Maximum value: %d\n", maximum);
    printf("Minimum value: %d\n", minimum);

    return 0;
}
```
# Output:
<img width="777" height="405" alt="Screenshot 2026-03-25 084801" src="https://github.com/user-attachments/assets/33072246-e568-4145-b647-2b4c86d61a0c" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
# Ex.No:18
  Develop a C program to convert temperatures between Celsius and Fahrenheit: Convert Celsius to Fahrenheit using a function that returns the converted value. Convert Fahrenheit to Celsius using another function that returns the converted value. Display the results in the main() function.
# Date : 26/02/2026
# Aim:
 To develop a C program that converts temperatures between Celsius and Fahrenheit using functions with return values.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.  
### Step 3:
 Declare function prototypes:
 - `float celtof();`  
 - `float ftocel();`
### Step 4: 
  Enter the `main()` function.
### Step 5:
  Call the `celtof()` function to convert Celsius to Fahrenheit.
### Step 6: 
  Inside `celtof()` function:
 - Declare float variables `C` and `F`.  
 - Display the message: **"Enter the temperature in Celsius"**.  
 - Read the value of `C` from the user.  
 - Calculate Fahrenheit using the formula: `F = (C * 9 / 5) + 32`.  
 - Return `F` to `main()`.
### Step 7: 
  Print the returned Fahrenheit value in `main()`.
### Step 8: 
  Call the `ftocel()` function to convert Fahrenheit to Celsius.
### Step 9: 
  Inside `ftocel()` function:
 - Declare float variables `f` and `celsius`.  
 - Display the message: **"Enter the temperature in Fahrenheit"**.  
 - Read the value of `f` from the user.  
 - Calculate Celsius using the formula: `celsius = (f - 32) * 5 / 9`.  
 - Return `celsius` to `main()`.
### Step 10: 
 Print the returned Celsius value in `main()`.
### Step 11: 
 Stop
# Program:
```
#include <stdio.h>
float celsiusToFahrenheit(float c) {
    return (c * 9.0 / 5.0) + 32.0;
}
float fahrenheitToCelsius(float f) {
    return (f - 32.0) * 5.0 / 9.0;
}
int main() {
    float celsius, fahrenheit;
    printf("Enter temperature in Celsius: ");
    scanf("%f", &celsius);
    printf("Enter temperature in Fahrenheit: ");
    scanf("%f", &fahrenheit);
    float f_result = celsiusToFahrenheit(celsius);
    float c_result = fahrenheitToCelsius(fahrenheit);
    printf("\nCelsius to Fahrenheit: %.2f C = %.2f F\n", celsius, f_result);
    printf("Fahrenheit to Celsius: %.2f F = %.2f C\n", fahrenheit, c_result);
    return 0;
}
```
# Output:
<img width="742" height="354" alt="Screenshot 2026-03-25 085249" src="https://github.com/user-attachments/assets/03b9aaba-41f5-4377-9bd1-ea1dd344f206" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

 
# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
# Ex.No:19
  Build a C program to print the elements of a given 4×4 matrix in spiral order starting from the top-left element and moving clockwise,using a user-defined parameterized function without return spiralPrint().
# Date : 26/02/2026
# Aim:
 To build a C program to display the elements of a 2D array in spiral form, traversing the outer elements first and then moving inward in a clockwise direction, using a user-defined parameterized function without return spiralPrint().
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.  
### Step 3: 
  Define constants `R` and `C` for the number of rows and columns in the matrix.
### Step 4: 
  Declare a function `spiralPrint(int m, int n, int a[R][C])` to print the matrix in spiral order.
### Step 5: 
  Inside `spiralPrint()` function:
 - Initialize variables:  
   - `k = 0` → starting row index  
   - `l = 0` → starting column index  
   - `m` → ending row index  
   - `n` → ending column index  
 - Repeat the following while `k < m` and `l < n`:
   - a. **Print the top row from left to right**:  
     - Loop from column `l` to `n-1` and print `a[k][i]`.  
     - Increment `k`.       
   - b. **Print the last column from top to bottom**:  
     - Loop from row `k` to `m-1` and print `a[i][n-1]`.  
     - Decrement `n`.       
   - c. **If `k < m`, print the bottom row from right to left**:  
     - Loop from column `n-1` to `l` and print `a[m-1][i]`.  
     - Decrement `m`.       
   - d. **If `l < n`, print the first column from bottom to top**:  
     - Loop from row `m-1` to `k` and print `a[i][l]`.  
     - Increment `l`.
### Step 6: 
  In the `main()` function:
- Declare and initialize a 4×4 matrix `a`.  
- Call `spiralPrint(R, C, a)` to print the elements in spiral order.
### Step 7: 
  Stop
# Program:
```
#include <stdio.h>
void spiralPrint(int matrix[4][4], int rows, int cols) {
	int i,j;
    int top = 0, bottom = rows - 1;
    int left = 0, right = cols - 1;
    printf("Spiral Order: ");
    while (top <= bottom && left <= right) {
        for (i = left; i <= right; i++) {
            printf("%d ", matrix[top][i]);
        }
        top++;
        for (i = top; i <= bottom; i++) {
            printf("%d ", matrix[i][right]);
        }
        right--;
        if (top <= bottom) {
            for (i = right; i >= left; i--) {
                printf("%d ", matrix[bottom][i]);
            }
            bottom--;
        }
        if (left <= right) {
            for (i = bottom; i >= top; i--) {
                printf("%d ", matrix[i][left]);
            }
            left++;
        }
    }
    printf("\n");
}
int main() {
	int i,j;
    int matrix[4][4];
    printf("Enter elements of 4x4 matrix:\n");
    for (i = 0; i < 4; i++) {
        for (j = 0; j < 4; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    spiralPrint(matrix, 4, 4);

    return 0;
}
```
# Output:
<img width="850" height="475" alt="Screenshot 2026-03-25 090224" src="https://github.com/user-attachments/assets/9d13e17e-5a39-415b-824b-f3b59dbb9e0c" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
# Ex.No:20
  Build a C program to convert a string such that the first and last characters, as well as the characters before and after each space, are converted to uppercase. Implement this using a user-defined parameterized function without return.
# Date : 26/02/2026
# Aim:
To build a C program to convert a string as described above, using a user-defined parameterized function without return convertFirstCLastC(char str[]).
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.  
### Step 3: 
  Declare a user-defined void function `convertFirstCLastC(char str[])` that takes the string as a parameter.
### Step 4: 
 Inside `convertFirstCLastC(char str[])` function:
 - Find the length of the string `len`.  
 - Convert the first character `str[0]` to uppercase.  
 - Loop through the string from index `1` to `len-2`:  
   - If a character is a space, capitalize the character before and after it.  
 - Convert the last character `str[len-1]` to uppercase.
### Step 5: 
 In `main()` function:
 - Declare a string `str[100]`.  
 - Read the input string from the user.  
 - Call the function `convertFirstCLastC(char str[])`.  
 - Print the modified string.
### Step 6: 
 Stop
# Program:
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>
void convert(char str[]) {
	int i;
    int len = strlen(str);
    if (len > 0 && str[0] != ' ')
        str[0] = toupper(str[0]);
    for (i = 1; i < len - 1; i++) {
        if (str[i] == ' ') {
            if (str[i - 1] != ' ')
                str[i - 1] = toupper(str[i - 1]); 
            if (str[i + 1] != ' ')
                str[i + 1] = toupper(str[i + 1]); 
        }
    }
    if (len > 1 && str[len - 1] != ' ')
        str[len - 1] = toupper(str[len - 1]);
}
int main() {
    char str[100];
    fgets(str, sizeof(str), stdin);
    int len = strlen(str);
    if (str[len - 1] == '\n') {
        str[len - 1] = '\0';
    }
    convert(str);
    printf("Modified string: %s\n", str);
    return 0;
}
```
# Output:
<img width="733" height="403" alt="Screenshot 2026-03-25 090757" src="https://github.com/user-attachments/assets/95e43ed3-1287-4eef-8156-0cd3a1990f3a" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

