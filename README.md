# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
## 7. Implementation of Functions.
## 8. Implementation of passing parameters.
# DATE : 22-05-2026
# Ex.No:16
  Implement a C program to read a date in the format DD/MM/YYYY and determine whether the entered date is valid. The program should check the correctness of the day, month, and year, including leap year calculations for February.

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

void validateDate() {
    int day, month, year;
    
    printf("Enter date in format DD MM YYYY: ");
    scanf("%d %d %d", &day, &month, &year);
    
    if(year < 1) {
        printf("Invalid date!\n");
        return;
    }
    
    if(month < 1 || month > 12) {
        printf("Invalid date!\n");
        return;
    }
    
    if(day < 1 || day > 31) {
        printf("Invalid date!\n");
        return;
    }
    
    int maxDays = 31;
    
    if(month == 2) {
        if((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0)) {
            maxDays = 29;
        } else {
            maxDays = 28;
        }
    }
    else if(month == 4 || month == 6 || month == 9 || month == 11) {
        maxDays = 30;
    }
    
    if(day > maxDays) {
        printf("Invalid date!\n");
        return;
    }
    
    printf("Valid date!\n");
}

int main() {
    validateDate();
    return 0;
}
```
# Output:
<img width="565" height="228" alt="531330930-d57072c2-8936-4e0e-8b3b-a85e16579e0b" src="https://github.com/user-attachments/assets/095159e4-e344-4b4f-8800-1557aaff824d" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
# DATE : 22-05-2026
# Ex.No:17
  Develop a C program to read two numbers from the user and determine the maximum and minimum values. Use user-defined functions with arguments and return values—one function to find the maximum (max()) and another to find the minimum (min()).

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

int findMax(int a, int b);
int findMin(int a, int b);

int main() {
    int x, y;
    
    printf("Enter two numbers: ");
    scanf("%d %d", &x, &y);
    
    int maxValue = findMax(x, y);
    int minValue = findMin(x, y);
    
    printf("Numbers entered: %d and %d\n", x, y);
    printf("Maximum: %d\n", maxValue);
    printf("Minimum: %d\n", minValue);
    
    return 0;
}

int findMax(int a, int b) {
    return (a > b) ? a : b;
}

int findMin(int a, int b) {
    return (a < b) ? a : b;
}
```
# Output:
<img width="450" height="314" alt="531330962-40632b2b-5302-4452-8980-0563b0991682" src="https://github.com/user-attachments/assets/c249d107-1906-4277-96b1-cb785e0739f0" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
# DATE : 22-05-2026
# Ex.No:18
  Develop a C program to convert temperatures between Celsius and Fahrenheit: Convert Celsius to Fahrenheit using a function that returns the converted value. Convert Fahrenheit to Celsius using another function that returns the converted value. Display the results in the main() function.

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

float getFahrenheit(float celsius) {
    float result = (celsius * 9 / 5) + 32;
    return result;
}

float getCelsius(float fahrenheit) {
    float result = (fahrenheit - 32) * 5 / 9;
    return result;
}

int main() {
    float c, f;
    
    printf("Celsius to Fahrenheit Conversion:\n");
    printf("Enter Celsius: ");
    scanf("%f", &c);
    f = getFahrenheit(c);
    printf("Fahrenheit: %.2f\n\n", f);
    
    printf("Fahrenheit to Celsius Conversion:\n");
    printf("Enter Fahrenheit: ");
    scanf("%f", &f);
    c = getCelsius(f);
    printf("Celsius: %.2f\n", c);
    
    return 0;
}
```
# Output:
<img width="438" height="374" alt="531330982-7338a27f-ee39-4abb-8207-6a6e3ca2eb8c" src="https://github.com/user-attachments/assets/0526b24a-21ac-4304-bc93-96eee2059b5b" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

 
# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
# DATE : 22-05-2026
# Ex.No:19
  Build a C program to print the elements of a given 4×4 matrix in spiral order starting from the top-left element and moving clockwise,using a user-defined parameterized function without return spiralPrint().

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

void spiralPrint(int arr[3][3]) {
    int i;
    
    printf("Spiral order: ");
    
    printf("%d %d %d ", arr[0][0], arr[0][1], arr[0][2]);
    printf("%d %d ", arr[1][2], arr[2][2]);
    printf("%d %d ", arr[2][1], arr[2][0]);
    printf("%d\n", arr[1][0]);
}

int main() {
    int matrix[3][3];
    
    printf("Enter 9 numbers for 3x3 matrix:\n");
    for(int i = 0; i < 3; i++) {
        for(int j = 0; j < 3; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    
    printf("\nYour matrix:\n");
    for(int i = 0; i < 3; i++) {
        for(int j = 0; j < 3; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
    
    spiralPrint(matrix);
    
    return 0;
}
```
# Output:
<img width="515" height="717" alt="531331009-39da56c6-f2e3-4727-b2c6-447e76ade3f0" src="https://github.com/user-attachments/assets/e92e270d-cc99-48c6-9bd6-21fffa4391e0" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
# Ex.No:20
  Build a C program to convert a string such that the first and last characters, as well as the characters before and after each space, are converted to uppercase. Implement this using a user-defined 
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

void convertString(char str[]) {
    int length = strlen(str);
    int i;
    
    if(length > 0) {
        str[0] = toupper(str[0]);
    }
    
    if(length > 1) {
        str[length - 1] = toupper(str[length - 1]);
    }
    
    for(i = 0; i < length; i++) {
        if(str[i] == ' ') {
            if(i > 0) {
                str[i - 1] = toupper(str[i - 1]);
            }
            if(i < length - 1) {
                str[i + 1] = toupper(str[i + 1]);
            }
        }
    }
}

int main() {
    char text[100];
    
    printf("Enter a string: ");
    fgets(text, 100, stdin);
    
    text[strcspn(text, "\n")] = '\0';
    
    printf("Original string: %s\n", text);
    
    convertString(text);
    
    printf("Converted string: %s\n", text);
    
    return 0;
}
```
# Output:
<img width="480" height="258" alt="531331045-a77bccc2-99a0-4a68-8d6e-c429bd5c42d5" src="https://github.com/user-attachments/assets/3948481a-f88a-413c-a4f6-b9a581e56c82" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

