- #C++_learn
-
- 以下為chatGPT內容，可能有誤
-
- **Step 1: Setting Up Your C++ Environment**
  collapsed:: true
	- Before writing C++ programs, you need:
	- 1.	**Compiler:** Install GCC (MinGW for Windows) or Clang.
	- 2.	**IDE/Text Editor:** Use CodeBlocks, Visual Studio Code, or CLion.
	- 3.	**Online Compiler (Optional):** Websites like [OnlineGDB](https://www.onlinegdb.com/) allow you to run C++ code without installation.
	- Would you like help setting up your environment? Let me know which OS you’re using! 🚀
- **Step 2: Writing Your First C++ Program**
  collapsed:: true
	- A simple C++ program consists of:
	- •	A **main function** (entry point of the program).
	- •	**Input/Output operations** (to interact with users).
	- •	**Statements and Semicolons** (each instruction ends with ;).
	- **Your First C++ Program**
	- Copy and run this code in your C++ compiler:
	- ```
	  #include <iostream>  // Header file for input/output
	  - int main() {
	    std::cout << "Hello, World!" << std::endl;  // Print message
	    return 0;  // End program
	  }
	  ```
	- **Explanation:**
	- 1.	# include <iostream> → Includes the Input/Output library.
	- 2.	int main() → Every C++ program must have a main function.
	- 3.	std::cout << "Hello, World!" → Prints text to the screen.
	- 4.	return 0; → Indicates that the program ran successfully.
- **Step 3: Understanding Input & Output**
  collapsed:: true
	- Now, let’s take user input:
	- ```
	  #include <iostream>
	  - int main() {
	    int age;  // Declare a variable
	    std::cout << "Enter your age: ";
	    std::cin >> age;  // Take user input
	    std::cout << "You are " << age << " years old!" << std::endl;
	    return 0;
	  }
	  ```
	- **Explanation:**
	- •	std::cin >> age; → Takes input from the user.
	- •	std::cout << → Prints output on the screen.
	- **Your Task:**
	- 1️⃣ Run both programs in your compiler.
	- 2️⃣ Try changing the text and input values.
	- Let me know if you have any questions before we move on to variables and data types! 🚀
- **Step 4: Variables and Data Types**
  collapsed:: true
	- **1. What Are Variables?**
	- A **variable** is a container that stores data. In C++, each variable has a **type**, which defines what kind of data it can hold.
	- **2. Common Data Types in C++**
	- || **Data Type**||**Description**||**Example**||
	  || int || Stores integers || int age = 25;||
	  ||float||Stores decimals||float price = 10.5;||
	  ||double||Stores large decimals| | double pi = 3.14159;| |
	  | | char| |Stores single letter| | char grade = 'A';| |
	  | | bool| |Stores true/false| | bool isStudent = true;| |
	  | | string| | Stores text (words)| | std::string name = "Alice";| |
	  🔹 string requires # include <string>.
	- **3. Writing a Program with Variables**
	- Try this code:
	- ```
	  #include <iostream>
	  #include <string>  // Include string library
	    int main() {
	    int age = 20; 
	    float height = 5.9;
	    char grade = 'A';
	    bool isStudent = true;
	    std::string name = "Alice";
	    std::cout << "Name: " << name << std::endl;
	    std::cout << "Age: " << age << std::endl;
	    std::cout << "Height: " << height << " feet" << std::endl;
	    std::cout << "Grade: " << grade << std::endl;
	    std::cout << "Student: " << isStudent << std::endl;
	    return 0;
	  }
	  ```
	- **4. Your Task:**
	- 1️⃣ Run this program.
	- 2️⃣ Change variable values and observe the output.
	- 3️⃣ Try adding a new variable (e.g., double salary = 50000.75;).
	- Let me know if you have any doubts! If you’re ready, we’ll move to **arithmetic operations** next. 🚀
- **Step 5: Arithmetic Operations in C++**
  collapsed:: true
	- **1. Arithmetic Operators**
	- C++ supports basic arithmetic operations, just like a calculator.
		- 💡 **Note:** If both numbers are integers, division (/) gives an **integer result** (e.g., 5/2 = 2). To get a decimal result, use float or double.
	- **2. Writing a Program with Arithmetic Operations**
		- Try this program:
		  
		  ```
		  #include <iostream>
		  
		  int main() {
		    int a = 10, b = 5;
		  
		    std::cout << "Addition: " << (a + b) << std::endl;
		    std::cout << "Subtraction: " << (a - b) << std::endl;
		    std::cout << "Multiplication: " << (a * b) << std::endl;
		    std::cout << "Division: " << (a / b) << std::endl;
		    std::cout << "Modulus: " << (a % b) << std::endl;
		  
		    return 0;
		  }
		  ```
	- **3. Taking User Input for Operations**
	- Modify the program to take input from the user:
	  ```
	  #include <iostream>
	  int main() {
	    int num1, num2;
	    std::cout << "Enter first number: ";
	    std::cin >> num1;
	    std::cout << "Enter second number: ";
	    std::cin >> num2;
	    std::cout << "Sum: " << (num1 + num2) << std::endl;
	    std::cout << "Difference: " << (num1 - num2) << std::endl;
	    std::cout << "Product: " << (num1 * num2) << std::endl;
	    std::cout << "Quotient: " << (num1 / num2) << std::endl;
	    std::cout << "Remainder: " << (num1 % num2) << std::endl;
	    return 0;
	  }
	  ```
	- **4. Your Task:**
	- 1️⃣ Run both programs.
	- 2️⃣ Try different inputs (e.g., 7 / 2).
	- 3️⃣ Modify it to work with float values (Hint: Change int to float).
	- Once you’re comfortable, let me know, and we’ll move to **operators and expressions** next! 🚀
- **Step 6: Operators and Expressions in C++**
  collapsed:: true
	- **1. Types of Operators**
	- C++ provides several types of operators:
	- | |**Type**| | **Operators**| | **Example**||
	  | | **Arithmetic**| | +, -, *, /, %| | a + b| |
	  | | **Assignment**| | =, +=, -=, *=, /=, %=| | a += 5 (same as a = a + 5)| |
	  | | **Comparison**| | ==, !=, >, <, >=, <=| | a > b| |
	  | | **Logical**| | && (AND), (OR)| |  | |
	  | | **Increment/Decrement**| | ++, --| | a++, b--| |
	  | | **Bitwise**| | &, (OR)| | , ^, ~, <<, >>`| |
	- **2. Assignment Operators**
	- These operators **modify a variable** in a compact way.
	- ```
	  #include <iostream>
	  int main() {
	    int x = 10;
	    x += 5;  // Same as x = x + 5;
	    std::cout << "Value of x: " << x << std::endl;
	    
	    return 0;
	  }
	  ```
	- ✅ **Try modifying x with -=, *=, /=, and %= and see what happens!**
	- **3. Comparison Operators**
	- These **compare two values** and return true or false.
	- ```
	  #include <iostream>
	  int main() {
	    int a = 10, b = 5;
	    std::cout << (a == b) << std::endl;  // 0 (false)
	    std::cout << (a != b) << std::endl;  // 1 (true)
	    std::cout << (a > b) << std::endl;   // 1 (true)
	    std::cout << (a < b) << std::endl;   // 0 (false)
	    return 0;
	  }
	  ```
	- ✅ **Try changing a and b values and test different comparisons!**
	- **4. Logical Operators**
	- Used to check multiple conditions at once.
	- | | **Operator**| | **Meaning**| | **Example**||
	  | | && (AND)| | Both conditions must be true| | (a > 5 && b < 10)| |
	  | | (OR)| |  | |  A(OR)B| |
	  | | ! (NOT)| | Reverses true to false and vice versa| | !(a == b)| |
	- ```
	  #include <iostream>
	  int main() {
	    int age;
	    std::cout << "Enter your age: ";
	    std::cin >> age;
	    if (age >= 18 && age <= 60) {
	        std::cout << "You are an adult." << std::endl;
	    } else {
	        std::cout << "You are either too young or a senior citizen." << std::endl;
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try different ages and see how the program behaves!**
	- **5. Your Task**
	- 1️⃣ Run the programs above and modify them.
	- 2️⃣ Try using &&, ||, and ! with different conditions.
	- 3️⃣ Write a program that checks if a number is positive and even.
	- Next, we will learn **Conditional Statements (if-else, switch)** to make your programs smarter! 🚀
- **Step 7: Conditional Statements in C++**
  collapsed:: true
	- Conditional statements **control the flow of execution** by checking conditions and executing different blocks of code.
	- **1. if-else Statement**
	- The if statement checks a condition and executes the code inside the block {} only if the condition is true.
	- ```
	  #include <iostream>
	  int main() {
	    int age;
	    std::cout << "Enter your age: ";
	    std::cin >> age;
	    if (age >= 18) {
	        std::cout << "You are eligible to vote!" << std::endl;
	    } else {
	        std::cout << "You are not eligible to vote." << std::endl;
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try different values for age and see how the program behaves!**
	- **2. if-else if-else Ladder**
	- Used when we have multiple conditions.
	- ```
	  #include <iostream>
	  int main() {
	    int num;
	    std::cout << "Enter a number: ";
	    std::cin >> num;
	    if (num > 0) {
	        std::cout << "The number is positive." << std::endl;
	    } else if (num < 0) {
	        std::cout << "The number is negative." << std::endl;
	    } else {
	        std::cout << "The number is zero." << std::endl;
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try entering positive, negative, and zero values!**
	- **3. Nested if Statements**
	- You can also place if inside another if.
	- ```
	  #include <iostream>
	  int main() {
	    int number;
	    std::cout << "Enter a number: ";
	    std::cin >> number;
	    if (number > 0) {
	        if (number % 2 == 0) {
	            std::cout << "The number is positive and even." << std::endl;
	        } else {
	            std::cout << "The number is positive and odd." << std::endl;
	        }
	    } else {
	        std::cout << "The number is not positive." << std::endl;
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try different numbers and see the results!**
	- **4. Switch Case Statement**
	- Used when we have multiple fixed values to check.
	- ```
	  #include <iostream>
	  int main() {
	    int day;
	    std::cout << "Enter a number (1-7) for the day of the week: ";
	    std::cin >> day;
	    switch (day) {
	        case 1: std::cout << "Sunday"; break;
	        case 2: std::cout << "Monday"; break;
	        case 3: std::cout << "Tuesday"; break;
	        case 4: std::cout << "Wednesday"; break;
	        case 5: std::cout << "Thursday"; break;
	        case 6: std::cout << "Friday"; break;
	        case 7: std::cout << "Saturday"; break;
	        default: std::cout << "Invalid input! Please enter a number between 1 and 7.";
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try entering numbers between 1-7 and check the output!**
	- **5. Your Task**
	- 1️⃣ Run all the programs and modify them.
	- 2️⃣ Try writing a program that checks whether a number is **positive, negative, or zero**, and whether it’s **even or odd**.
	- 3️⃣ Use a **switch case** to print a **month name** based on a given number (1-12).
	- Next, we’ll learn **Loops (for, while, do-while)** to repeat actions in your program! 🚀 Let me know if you’re ready!
- **Step 8: Loops in C++**
  collapsed:: true
	- Loops are used to execute a block of code repeatedly based on a condition.
	- **1. Types of Loops in C++**
	- | | **Loop Type** |  | **Usage** |  |
	  | ---- |
	  |  | **for loop** |  | Used when you know how many times to repeat. |  |
	  |  | **while loop** |  | Used when you don’t know the exact repetitions beforehand. |  |
	  |  | **do-while loop** |  | Similar to while, but runs at least once. |  |
	- **2. for Loop**
	- Used when the number of repetitions is **known**.
	- **Syntax:**
	- ```
	  for (initialization; condition; update) {
	      // Code to repeat
	  }
	  ```
	- **Example: Print numbers from 1 to 5**
	  
	  ```
	  #include <iostream>
	  
	  int main() {
	      for (int i = 1; i <= 5; i++) {
	          std::cout << "Number: " << i << std::endl;
	      }
	      return 0;
	  }
	  ```
	  
	  ✅ **Try changing i <= 5 to i <= 10 and see the output!**
	- **3. while Loop**
	  
	  Used when the number of repetitions **is not known in advance**.
	  
	  **Syntax:**
	  
	  ```
	  while (condition) {
	      // Code to repeat
	  }
	  ```
	  
	  **Example: Print numbers from 1 to 5 using while loop**
	  
	  ```
	  #include <iostream>
	  
	  int main() {
	      int i = 1;
	      while (i <= 5) {
	          std::cout << "Number: " << i << std::endl;
	          i++; // Increment i
	      }
	      return 0;
	  }
	  ```
	  
	  ✅ **Try changing the condition to i <= 10 and see what happens!**
	- **4. do-while Loop**
	  
	  Similar to while, but **guarantees at least one execution**, even if the condition is false.
	  
	  **Syntax:**
	  
	  ```
	  do {
	      // Code to repeat
	  } while (condition);
	  ```
	  
	  **Example: Take input until a positive number is entered**
	  
	  ```
	  #include <iostream>
	  
	  int main() {
	      int num;
	      do {
	          std::cout << "Enter a positive number: ";
	          std::cin >> num;
	      } while (num <= 0); // Loop repeats if the number is <= 0
	  
	      std::cout << "You entered: " << num << std::endl;
	      return 0;
	  }
	  ```
	  
	  ✅ **Try entering negative numbers first and then a positive number!**
	- **5. Nested Loops**
	  
	  Loops inside another loop are called **nested loops**.
	  
	  **Example: Print a 3×3 grid**
	  
	  ```
	  #include <iostream>
	  
	  int main() {
	      for (int i = 1; i <= 3; i++) { // Outer loop
	          for (int j = 1; j <= 3; j++) { // Inner loop
	              std::cout << i << "," << j << "  ";
	          }
	          std::cout << std::endl; // Move to the next line
	      }
	      return 0;
	  }
	  ```
	  
	  ✅ **Try changing 3 to 5 to make a larger grid!**
	- **6. Your Task**
	  
	  1️⃣ Run and modify the above programs.
	  
	  2️⃣ Write a **for loop** that prints even numbers from 1 to 20.
	  
	  3️⃣ Modify the **while loop** to print numbers in reverse (10 to 1).
	  
	  4️⃣ Use a **nested loop** to print a pattern like:
	  
	  ```
	  *
	  **
	  ***
	  ****
	  *****
	  ```
	  
	  Once you’re done, let me know! Next, we’ll learn **functions** to organize your code better! 🚀
- **Step 9: Functions in C++**
  collapsed:: true
	- A **function** is a block of code that performs a specific task. It helps in:
	- ✅ Avoiding code repetition
	- ✅ Making code more readable
	- ✅ Making debugging easier
	- **1. Types of Functions in C++**
	- | | **Type**| | **Description**||
	  | | **Built-in Functions**| | Provided by C++ (e.g., sqrt(), pow())| |
	  | | **User-defined Functions**| | Created by the programmer| |
	- **2. Function Syntax**
	- ```
	  returnType functionName(parameters) {
	    // Function body (code)
	    return value; // (if needed)
	  }
	  ```
	- **3. Creating and Using a Function**
	- Let’s create a simple function to **add two numbers**.
	- **Example: Function without parameters**
	- ```
	  #include <iostream>
	  void greet() {  // Function definition
	    std::cout << "Hello, Welcome to C++ Functions!" << std::endl;
	  }
	  int main() {
	    greet();  // Function call
	    return 0;
	  }
	  ```
	- ✅ **Try modifying the function to display your name!**
	- **4. Function with Parameters**
	- We can pass values to functions as **parameters**.
	- **Example: Function to add two numbers**
	- ```
	  #include <iostream>
	  void addNumbers(int a, int b) { // Function with parameters
	    int sum = a + b;
	    std::cout << "Sum: " << sum << std::endl;
	  }
	  int main() {
	    addNumbers(5, 10); // Function call with arguments
	    return 0;
	  }
	  ```
	- ✅ **Try calling the function with different numbers!**
	- **5. Function with Return Value**
	- A function can return a value using return.
	- **Example: Function that returns sum**
	- ```
	  #include <iostream>
	  int add(int x, int y) {
	    return x + y; // Returning sum
	  }
	  int main() {
	    int result = add(8, 12);
	    std::cout << "Sum: " << result << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try storing the result in another variable and printing it!**
	- **6. Function Overloading**
	- You can define multiple functions **with the same name** but different parameters.
	- **Example: Function to add integers and doubles**
	- ```
	  #include <iostream>
	  int add(int a, int b) { return a + b; }        // Integer version
	  double add(double a, double b) { return a + b; } // Double version
	  int main() {
	    std::cout << "Sum (int): " << add(5, 10) << std::endl;
	    std::cout << "Sum (double): " << add(3.5, 2.5) << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try adding more versions of the function!**
	- **7. Your Task**
	- 1️⃣ Write a function to **multiply two numbers** and return the result.
	- 2️⃣ Modify the function to accept **float** values.
	- 3️⃣ Write a function that **checks if a number is even or odd**.
	- Next, we’ll learn about **Arrays and Strings** to store and manipulate multiple values! 🚀 Let me know when you’re ready!
- **Step 10: Arrays and Strings in C++**
  collapsed:: true
	- **1. What is an Array?**
	- An **array** is a collection of multiple values of the **same data type**, stored in contiguous memory locations.
	- **Example of an Array:**
	- ```
	  int numbers[5] = {10, 20, 30, 40, 50};
	  ```
	- Here, numbers is an array that stores **5 integers**.
	- **2. Declaring and Accessing Arrays**
	- **Syntax:**
	- ```
	  dataType arrayName[size];
	  ```
	- **Example:**
	- ```
	  #include <iostream>
	  int main() {
	    int arr[3] = {5, 10, 15};
	    std::cout << "First Element: " << arr[0] << std::endl;
	    std::cout << "Second Element: " << arr[1] << std::endl;
	    std::cout << "Third Element: " << arr[2] << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try changing the values and adding more elements!**
	- **3. Looping Through an Array**
	- Using a for loop, we can **iterate through an array**.
	- ```
	  #include <iostream>
	  int main() {
	    int numbers[5] = {1, 2, 3, 4, 5};
	    for (int i = 0; i < 5; i++) {  // Loop through array
	        std::cout << "Element at index " << i << ": " << numbers[i] << std::endl;
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try modifying the array and loop range!**
	- **4. Taking User Input in Arrays**
	- ```
	  #include <iostream>
	  int main() {
	    int arr[5];
	    std::cout << "Enter 5 numbers: ";
	    for (int i = 0; i < 5; i++) {
	        std::cin >> arr[i];  // Taking input
	    }
	    std::cout << "You entered: ";
	    for (int i = 0; i < 5; i++) {
	        std::cout << arr[i] << " ";  // Printing values
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try entering different numbers and increasing the array size!**
	- **5. Strings in C++**
	- A **string** is a sequence of characters stored in memory.
	- **Ways to Declare a String**
	- ```
	  char name[] = "John";     // Using character array
	  std::string name = "John"; // Using C++ string class
	  ```
	- **6. Taking String Input**
	- **Example:**
	- ```
	  #include <iostream>
	  #include <string>  // Include string library
	  int main() {
	    std::string name;
	    
	    std::cout << "Enter your name: ";
	    std::cin >> name;  // Takes input until space
	    std::cout << "Hello, " << name << "!" << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try entering your full name—what happens?**
	- **7. Using getline() to Read Full Strings**
	- ```
	  #include <iostream>
	  #include <string>
	  int main() {
	    std::string fullName;
	    std::cout << "Enter your full name: ";
	    std::getline(std::cin, fullName);  // Reads full input
	    std::cout << "Hello, " << fullName << "!" << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try entering your full name and see the difference!**
	- **8. Your Task**
	- 1️⃣ Declare an **integer array of size 10**, take input, and print all values.
	- 2️⃣ Write a program to **find the largest number in an array**.
	- 3️⃣ Take a **string input** and print it in **reverse order**.
	- Next, we’ll learn **Pointers and Memory Management** to understand how data is stored in memory! 🚀 Let me know when you’re ready!
- **Step 11: Pointers and Memory Management in C++**
  collapsed:: true
	- A **pointer** is a variable that stores the **memory address** of another variable.
	- **1. Declaring and Using Pointers**
	- **Syntax:**
	- ```
	  dataType *pointerName;
	  ```
	- **Example:**
	- ```
	  #include <iostream>
	  int main() {
	    int num = 10;
	    int *ptr = &num;  // Pointer stores the address of num
	    std::cout << "Value of num: " << num << std::endl;
	    std::cout << "Address of num: " << &num << std::endl;
	    std::cout << "Pointer ptr stores: " << ptr << std::endl;
	    std::cout << "Value at pointer ptr: " << *ptr << std::endl;  // Dereferencing
	    return 0;
	  }
	  ```
	- ✅ **Try modifying num and see how the pointer behaves!**
	- **2. Pointer Arithmetic**
	- Pointers allow us to perform arithmetic operations like **increment, decrement, addition, and subtraction**.
	- ```
	  #include <iostream>
	  int main() {
	    int *ptr = new int;  // Allocating memory
	    *ptr = 42;  // Storing a value
	    std::cout << "Dynamically allocated value: " << *ptr << std::endl;
	    delete ptr;  // Freeing memory
	    return 0;
	  }
	  ```
	- ✅ **Try looping through the entire array using a pointer!**
	- **3. Dynamic Memory Allocation (new and delete)**
	- In C++, memory can be allocated at runtime using new, and must be freed using delete.
	- **Example: Allocating Memory for an Integer**
	- ```
	  #include <iostream>
	  int main() {
	    int *ptr = new int;  // Allocating memory
	    *ptr = 42;  // Storing a value
	    std::cout << "Dynamically allocated value: " << *ptr << std::endl;
	    delete ptr;  // Freeing memory
	    return 0;
	  }
	  ```
	- ✅ **Try allocating and freeing memory for different data types!**
	- **4. Dynamic Arrays**
	- We can allocate arrays dynamically.
	- **Example: Dynamic Array Allocation**
	- ```
	  #include <iostream>
	  int main() {
	    int size;
	    std::cout << "Enter the number of elements: ";
	    std::cin >> size;
	    int *arr = new int[size];  // Allocating array dynamically
	    std::cout << "Enter " << size << " numbers: ";
	    for (int i = 0; i < size; i++) {
	        std::cin >> arr[i];
	    }
	    std::cout << "You entered: ";
	    for (int i = 0; i < size; i++) {
	        std::cout << arr[i] << " ";
	    }
	    delete[] arr;  // Freeing memory
	    return 0;
	  }
	  ```
	- ✅ **Try allocating a larger array dynamically!**
	- **5. Your Task**
	- 1️⃣ Declare an **integer pointer**, assign it an address, and print its value.
	- 2️⃣ Create a **pointer that stores an array’s address** and print all elements using pointer arithmetic.
	- 3️⃣ Allocate **dynamic memory** for an array, take input, and print the sum of all elements.
	  Next, we’ll learn about **Structures and Classes (Object-Oriented Programming - OOP)** to write more complex programs! 🚀 Let me know when you’re ready!
- **Step 12: Structures and Classes in C++ (OOP Basics)**
  collapsed:: true
	- **1. What is a Structure (struct)?**
	- A **structure (struct)** is a user-defined data type that groups related variables together.
	- **Example: Defining and Using a Structure**
	- ```
	  #include <iostream>
	  struct Person {
	    std::string name;
	    int age;
	  };
	  int main() {
	    Person p1;  // Creating a structure variable
	    p1.name = "John";
	    p1.age = 25;
	    std::cout << "Name: " << p1.name << std::endl;
	    std::cout << "Age: " << p1.age << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try adding more attributes (like height, weight) to the structure!**
	- **2. What is a Class?**
	- A **class** is similar to a structure but also allows **functions (methods)** inside it.
	- **Example: Defining and Using a Class**
	- ```
	  #include <iostream>
	  class Person {
	  public:
	    std::string name;
	    int age;
	    void introduce() {
	        std::cout << "Hi, my name is " << name << " and I am " << age << " years old." << std::endl;
	    }
	  };
	  int main() {
	    Person p1;
	    p1.name = "Alice";
	    p1.age = 30;
	    p1.introduce();  // Calling a function inside the class
	    return 0;
	  }
	  ```
	- ✅ **Try creating multiple objects (p2, p3) and calling introduce()!**
	- **3. Constructors (Special Functions)**
	- A **constructor** is a function inside a class that gets called **automatically** when an object is created.
	- **Example: Using a Constructor**
	- ```
	  #include <iostream>
	  class Person {
	  public:
	    std::string name;
	    int age;
	    // Constructor
	    Person(std::string n, int a) {
	        name = n;
	        age = a;
	    }
	    void introduce() {
	        std::cout << "Hi, my name is " << name << " and I am " << age << " years old." << std::endl;
	    }
	  };
	  int main() {
	    Person p1("Bob", 40);  // Constructor is automatically called
	    p1.introduce();
	    return 0;
	  }
	  ```
	- ✅ **Try creating multiple objects using the constructor!**
	- **4. Private vs Public Members**
	- In a class:
	- •	**public** members can be accessed anywhere.
	- •	**private** members can be accessed only inside the class.
	- **Example: Private Variables & Getters/Setters**
	- ```
	  #include <iostream>
	  class BankAccount {
	  private:
	    double balance;
	    public:
	    BankAccount(double b) { balance = b; }
	    void deposit(double amount) {
	        balance += amount;
	    }
	    double getBalance() {
	        return balance;
	    }
	  };
	  int main() {
	    BankAccount account(1000);
	    account.deposit(500);
	    std::cout << "Current Balance: " << account.getBalance() << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try adding a withdraw() function that decreases the balance!**
	- **5. Your Task**
	- 1️⃣ Create a **Car class** with attributes like brand, model, and year.
	- 2️⃣ Add a function that **displays car details**.
	- 3️⃣ Add a **constructor** to initialize car attributes automatically.
	- Next, we’ll learn about **Inheritance and Polymorphism (Advanced OOP Concepts)**! 🚀 Let me know when you’re ready!
- **Step 13: Inheritance and Polymorphism in C++ (Advanced OOP Concepts)**
  collapsed:: true
	- **1. What is Inheritance?**
	- Inheritance allows a **child class (derived class)** to **inherit properties and methods** from a **parent class (base class)**.
	- **Example: Base and Derived Class**
	- ```
	  #include <iostream>
	  // Base class
	  class Animal {
	  public:
	    void makeSound() {
	        std::cout << "Animal makes a sound" << std::endl;
	    }
	  };
	  // Derived class
	  class Dog : public Animal {
	  public:
	    void bark() {
	        std::cout << "Dog barks" << std::endl;
	    }
	  };
	  int main() {
	    Dog myDog;
	    myDog.makeSound();  // Inherited from Animal class
	    myDog.bark();       // Dog-specific function 
	    return 0;
	  }
	  ```
	- ✅ **Try creating another class Cat that also inherits from Animal!**
	- **2. Types of Inheritance**
	- | | **Type**| | **Description**||
	  | | **Single Inheritance**| | One class inherits from another.| |
	  | | **Multiple Inheritance**| | A class inherits from multiple classes.| |
	  | | **Multilevel Inheritance**| | A class inherits from a derived class.| |
	  | | **Hierarchical Inheritance**| | Multiple classes inherit from a single base class.| |
	- **Example: Multilevel Inheritance**
	- ```
	  #include <iostream>
	  // Base class
	  class Animal {
	  public:
	    void makeSound() {
	        std::cout << "Animal makes a sound" << std::endl;
	    }
	  };
	  // Derived class
	  class Dog : public Animal {
	  public:
	    void bark() {
	        std::cout << "Dog barks" << std::endl;
	    }
	  };
	  int main() {
	    Dog myDog;
	    myDog.makeSound();  // Inherited from Animal class
	    myDog.bark();       // Dog-specific function- return 0;
	  }
	  ```
	- ✅ **Try creating a Car class with Vehicle as the base class!**
	- **3. Polymorphism (Function Overriding)**
	- Polymorphism allows a derived class to **modify (override)** a function from its base class.
	- **Example: Function Overriding**
	- ```
	  #include <iostream>
	  class Animal {
	  public:
	    virtual void makeSound() {  // Virtual function
	        std::cout << "Animal makes a sound" << std::endl;
	    }
	  };
	  class Dog : public Animal {
	  public:
	    void makeSound() override {  // Overriding function
	        std::cout << "Dog barks" << std::endl;
	    }
	  };
	  int main() {
	    Animal* a;  // Pointer to base class
	    Dog d;
	    a = &d;
	    a->makeSound();  // Calls Dog’s overridden function
	    return 0;
	  }
	  ```
	- ✅ **Try adding another class (e.g., Cat) that overrides makeSound()!**
	- **4. Abstract Classes and Pure Virtual Functions**
	- An **abstract class** is a class that has at least one **pure virtual function** (a function that must be overridden in derived classes).
	- **Example: Abstract Class**
	- ```
	  #include <iostream>
	  class Shape {
	  public:
	    virtual void draw() = 0;  // Pure virtual function
	  };
	  class Circle : public Shape {
	  public:
	    void draw() override {
	        std::cout << "Drawing a Circle" << std::endl;
	    }
	  };
	  int main() {
	    Circle c;
	    c.draw();  // Calls overridden function
	    return 0;
	  }
	  ```
	- ✅ **Try creating a Rectangle class that also inherits from Shape!**
	- **5. Your Task**
	- 1️⃣ Create a **Vehicle class** with an attribute speed and a function showSpeed().
	- 2️⃣ Create a **Car class** that **inherits from Vehicle** and adds an attribute brand.
	- 3️⃣ Use **function overriding** to modify showSpeed() in the Car class.
	- Next, we’ll learn about **File Handling in C++ (Reading/Writing to Files)**! 🚀 Let me know when you’re ready!
- **Step 14: File Handling in C++**
  collapsed:: true
	- **1. What is File Handling?**
	- File handling allows C++ programs to **store and retrieve data** from external files (like .txt, .csv, etc.).
	- C++ uses the **fstream** library for file operations.
	- **2. Including the File Handling Library**
	- ```
	  #include <iostream>
	  #include <fstream>  // Required for file handling
	  ```
	- **3. Writing to a File**
	- We use **ofstream (output file stream)** to write data to a file.
	- **Example: Writing to a File**
	- ```
	  #include <iostream>
	  #include <fstream>  // File handling library
	  int main() {
	    std::ofstream myFile("example.txt");  // Open a file in write mode
	    if (myFile.is_open()) {
	        myFile << "Hello, this is a test file.\n";
	        myFile << "C++ File Handling is easy!\n";
	        myFile.close();  // Always close the file
	        std::cout << "Data written to file successfully!" << std::endl;
	    } else {
	        std::cout << "Error opening file!" << std::endl;
	    }
	    return 0;
	  }
	  ```
	- ✅ **Check your project folder for example.txt!**
	- **4. Reading from a File**
	- We use **ifstream (input file stream)** to read data from a file.
	- **Example: Reading from a File**
	- ```
	  #include <iostream>
	  #include <fstream>
	  int main() {
	    std::ifstream myFile("example.txt");  // Open file in read mode
	    std::string line;
	    if (myFile.is_open()) {
	        while (getline(myFile, line)) {  // Read file line by line
	            std::cout << line << std::endl;
	        }
	        myFile.close();  // Close the file
	    } else {
	        std::cout << "Error opening file!" << std::endl;
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try modifying example.txt and running the program again!**
	- **5. Appending to a File**
	- We use **ios::app mode** to append data to an existing file.
	- **Example: Appending to a File**
	- ```
	  #include <iostream>
	  #include <fstream>
	  int main() {
	    std::ofstream myFile("example.txt", std::ios::app);  // Open in append mode
	    if (myFile.is_open()) {
	        myFile << "This is a new line added to the file.\n";
	        myFile.close();
	        std::cout << "Data appended successfully!" << std::endl;
	    } else {
	        std::cout << "Error opening file!" << std::endl;
	    }
	    return 0;
	  }
	  ```
	- ✅ **Check if the new line was added to example.txt!**
	- **6. Your Task**
	- 1️⃣ **Write a program** that asks the user for their name and age, then **writes** it to user_data.txt.
	- 2️⃣ Modify the program to **read and display** the saved data.
	- 3️⃣ **Append new user data** without overwriting the file.
	- Next, we’ll learn about **Exception Handling (Handling Errors in C++)**! 🚀 Let me know when you’re ready!
- **Step 15: Exception Handling in C++**
  collapsed:: true
	- **1. What is Exception Handling?**
	- Exception handling allows a program to **detect and handle runtime errors** instead of crashing unexpectedly.
	- In C++, we use **try**, **catch**, and **throw** to handle exceptions.
	- **2. Basic Try-Catch Block**
	- ```
	  #include <iostream>
	  int main() {
	    try {
	        int x = 10, y = 0;
	        if (y == 0)
	            throw "Division by zero error!";  // Throwing an exception
	            
	        std::cout << x / y << std::endl;
	    }
	    catch (const char* msg) {  // Catching the exception
	        std::cout << "Error: " << msg << std::endl;
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try changing y to a nonzero value and observe what happens!**
	- **3. Handling Multiple Exceptions**
	- We can catch different types of exceptions using multiple catch blocks.
	- ```
	  #include <iostream>
	  int main() {
	    try {
	        int num;
	        std::cout << "Enter a positive number: ";
	        std::cin >> num;
	    if (num < 0)
	            throw std::runtime_error("Negative numbers are not allowed!");
	        if (num == 0)
	            throw 0;  // Throwing an integer exception
	    std::cout << "You entered: " << num << std::endl;
	    }
	    catch (std::runtime_error &e) {  // Catching a runtime error
	        std::cout << "Error: " << e.what() << std::endl;
	    }
	    catch (int err) {  // Catching an integer exception
	        std::cout << "Error: Zero is not a valid input!" << std::endl;
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try entering negative numbers and zero to see how the exceptions work!**
	- **4. Exception Handling with Functions**
	- We can throw exceptions from functions and handle them in main().
	- ```
	  #include <iostream>
	  void divide(int a, int b) {
	    if (b == 0)
	        throw std::runtime_error("Cannot divide by zero!");  // Throw exception
	    std::cout << "Result: " << a / b << std::endl;
	  }
	  int main() {
	    try {
	        divide(10, 0);  // This will cause an exception
	    }
	    catch (std::runtime_error &e) {
	        std::cout << "Exception caught: " << e.what() << std::endl;
	    }
	    return 0;
	  }
	  ```
	- ✅ **Modify the function to handle other math errors like division by a negative number!**
	- **5. Your Task**
	- 1️⃣ Write a function that **asks the user for an age** and throws an exception if the age is **negative**.
	- 2️⃣ Modify the function to **catch and handle** the error in main().
	- 3️⃣ Implement exception handling for **file handling errors** (e.g., if a file does not exist).
	- Next, we’ll learn about **STL (Standard Template Library)**, which provides powerful data structures like **vectors, maps, and sets**! 🚀 Let me know when you’re ready!
- **Step 16: Standard Template Library (STL) in C++**
  collapsed:: true
	- The **STL (Standard Template Library)** provides **predefined classes and functions** to handle **data structures and algorithms** efficiently. It consists of:
	- •	**Containers** (like vector, map, set)
	- •	**Algorithms** (like sort(), find(), reverse())
	- •	**Iterators** (to access container elements)
	- **1. Vectors (Dynamic Arrays)**
	- Vectors are **resizable arrays** that can grow or shrink automatically.
	- **Example: Using vector**
	- ```
	  #include <iostream>
	  #include <vector>
	  int main() {
	    std::vector<int> numbers = {10, 20, 30};
	    numbers.push_back(40);  // Add an element
	    numbers.push_back(50);
	    std::cout << "Vector elements: ";
	    for (int num : numbers) {
	        std::cout << num << " ";
	    }
	    std::cout << "\nSize: " << numbers.size() << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try removing an element using numbers.pop_back()!**
	- **2. Pairs (Grouping Two Values)**
	- Pairs allow you to store **two related values** together.
	- **Example: Using pair**
	- ```
	  #include <iostream>
	  #include <utility>  // Required for pair
	  int main() {
	    std::pair<std::string, int> person("Alice", 25);
	    std::cout << "Name: " << person.first << ", Age: " << person.second << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try changing the data types in the pair (e.g., float, char)!**
	- **3. Maps (Key-Value Pairs)**
	- Maps store **key-value pairs** and allow **fast lookups**.
	- **Example: Using map**
	- ```
	  #include <iostream>
	  #include <map>
	  int main() {
	    std::map<std::string, int> ageMap;
	    
	    ageMap["Alice"] = 25;
	    ageMap["Bob"] = 30;
	    std::cout << "Alice's age: " << ageMap["Alice"] << std::endl;
	    // Iterating through the map
	    for (auto &pair : ageMap) {
	        std::cout << pair.first << " is " << pair.second << " years old." << std::endl;
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try adding more key-value pairs and checking if a key exists using ageMap.count("Alice")!**
	- **4. Sets (Unique Elements)**
	- Sets store **unique** values in **sorted order**.
	- **Example: Using set**
	- ```
	  #include <iostream>
	  #include <set>
	  int main() {
	    std::set<int> mySet = {5, 2, 8, 5, 10};
	    mySet.insert(3);  // Add an element
	    mySet.insert(8);  // Duplicate values are ignored
	    std::cout << "Set elements: ";
	    for (int num : mySet) {
	        std::cout << num << " ";
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try using mySet.erase(2) to remove an element!**
	- **5. Algorithms in STL**
	- The **STL also provides algorithms** like sorting, searching, and reversing.
	- **Example: Using sort()**
	- ```
	  #include <iostream>
	  #include <vector>
	  #include <algorithm>  // Required for sort()
	  int main() {
	    std::vector<int> nums = {4, 2, 8, 1, 5};
	    std::sort(nums.begin(), nums.end());  // Sorting the vector
	    std::cout << "Sorted numbers: ";
	    for (int num : nums) {
	        std::cout << num << " ";
	    }
	    return 0;
	  }
	  ```
	- ✅ **Try using reverse(nums.begin(), nums.end()) to reverse the vector!**
	- **6. Your Task**
	- 1️⃣ Create a **vector** that stores students’ names and displays them.
	- 2️⃣ Create a **map** to store student names with their marks.
	- 3️⃣ Use **sort()** to sort students based on their marks.
	- Next, we’ll learn about **Multithreading (Running Multiple Tasks at the Same Time)!** 🚀 Let me know when you’re ready!
- **Step 17: Multithreading in C++**
  collapsed:: true
	- **1. What is Multithreading?**
	- Multithreading allows a program to **run multiple tasks simultaneously** by using multiple threads.
	- In C++, we use the **<thread> library** to create and manage threads.
	- **2. Including the Thread Library**
	- ```
	  #include <iostream>
	  #include <thread>  // Required for multithreading
	  ```
	- **3. Creating and Running Threads**
	- We use the **std::thread** class to create a new thread.
	- **Example: Running a Thread**
	- ```
	  #include <iostream>
	  #include <thread>
	  void printMessage() {
	    std::cout << "Hello from a separate thread!" << std::endl;
	  }
	  int main() {
	    std::thread t1(printMessage);  // Create and start a thread
	    t1.join();  // Wait for the thread to finish
	    std::cout << "Hello from main thread!" << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try removing t1.join(); and observe what happens!**
	- **4. Passing Arguments to a Thread**
	- Threads can take arguments when calling a function.
	- **Example: Passing Arguments to a Thread**
	- ```
	  #include <iostream>
	  #include <thread>
	  void printNumbers(int n) {
	    for (int i = 1; i <= n; i++) {
	        std::cout << i << " ";
	    }
	    std::cout << std::endl;
	  }
	  int main() {
	    std::thread t1(printNumbers, 5);  // Pass argument to thread
	    t1.join();
	    return 0;
	  }
	  ```
	- ✅ **Try changing 5 to a larger number!**
	- **5. Using Lambda Functions in Threads**
	- We can use **lambda functions** instead of defining separate functions.
	- **Example: Lambda Function with Thread**
	- ```
	  #include <iostream>
	  #include <thread>
	  int main() {
	    std::thread t([]() {
	        std::cout << "Thread using lambda!" << std::endl;
	    });
	    t.join();
	    return 0;
	  }
	  ```
	- ✅ **Try modifying the lambda to print numbers!**
	- **6. Running Multiple Threads**
	- We can create **multiple threads** to run different tasks at the same time.
	- **Example: Multiple Threads**
	- ```
	  #include <iostream>
	  #include <thread>
	  void task1() {
	    std::cout << "Task 1 running...\n";
	  }
	  void task2() {
	    std::cout << "Task 2 running...\n";
	  }
	  int main() {
	    std::thread t1(task1);
	    std::thread t2(task2);
	    t1.join();  // Wait for t1 to finish
	    t2.join();  // Wait for t2 to finish
	    return 0;
	  }
	  ```
	- ✅ **Try adding a third thread!**
	- **7. Detaching a Thread**
	- A thread can be **detached** to run independently.
	- **Example: Detached Thread**
	- ```
	  #include <iostream>
	  #include <thread>
	  #include <chrono>
	  void backgroundTask() {
	    std::this_thread::sleep_for(std::chrono::seconds(2));
	    std::cout << "Background task completed!" << std::endl;
	  }
	  int main() {
	    std::thread t(backgroundTask);
	    t.detach();  // Thread runs independently
	    std::cout << "Main function continues..." << std::endl;
	    
	    std::this_thread::sleep_for(std::chrono::seconds(3));  // Wait for detached thread to finish
	    return 0;
	  }
	  ```
	- ✅ **Try removing std::this_thread::sleep_for(3s); and see what happens!**
	- **8. Your Task**
	- 1️⃣ Create a thread that prints numbers from 1 to 10.
	- 2️⃣ Create **two** threads that run **at the same time** and print different messages.
	- 3️⃣ Modify the program to **detach** one of the threads.
	- Next, we’ll learn about **Memory Management (Smart Pointers in C++)!** 🚀 Let me know when you’re ready!
- **Step 18: Memory Management & Smart Pointers in C++**
  collapsed:: true
	- **1. Why Memory Management?**
	- •	**Dynamic memory** is allocated using new and deallocated using delete.
	- •	Forgetting to use delete causes **memory leaks** (wasted memory).
	- •	**Smart pointers** (unique_ptr, shared_ptr, weak_ptr) automatically manage memory.
	- **2. Dynamic Memory Allocation**
	- C++ allows us to allocate memory at runtime using **new**.
	- **Example: Using new and delete**
	- ```
	  #include <iostream>
	  int main() {
	    int* ptr = new int(10);  // Allocate memory for an integer
	    std::cout << "Value: " << *ptr << std::endl;
	    delete ptr;  // Free allocated memory
	    return 0;
	  }
	  ```
	- ✅ **Try allocating memory for an array using new[] and deallocate it using delete[].**
	- **3. Unique Pointer (unique_ptr)**
	- •	**unique_ptr** ensures that only one pointer owns the memory.
	- •	Memory is automatically **deleted when the pointer goes out of scope**.
	- **Example: Using unique_ptr**
	- ```
	  #include <iostream>
	  #include <memory>  // Required for smart pointers
	  int main() {
	    std::unique_ptr<int> ptr = std::make_unique<int>(100);
	    std::cout << "Unique Pointer Value: " << *ptr << std::endl;
	    // No need to use delete, memory is freed automatically!
	    return 0;
	  }
	  ```
	- ✅ **Try assigning ptr to another unique_ptr and observe the error!**
	- **4. Shared Pointer (shared_ptr)**
	- •	**shared_ptr** allows multiple pointers to share ownership of an object.
	- •	Memory is **freed when the last shared_ptr is destroyed**.
	- **Example: Using shared_ptr**
	- ```
	  #include <iostream>
	  #include <memory>
	  int main() {
	    std::shared_ptr<int> sp1 = std::make_shared<int>(200);
	    std::shared_ptr<int> sp2 = sp1;  // Multiple pointers share ownership
	    std::cout << "Shared Pointer Value: " << *sp1 << std::endl;
	    std::cout << "Reference Count: " << sp1.use_count() << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try creating more shared pointers and check use_count().**
	- **5. Weak Pointer (weak_ptr)**
	- •	**weak_ptr** does not own memory but can access it.
	- •	Used to **avoid circular dependencies** in shared_ptr.
	- **Example: Using weak_ptr**
	- ```
	  #include <iostream>
	  #include <memory>
	  int main() {
	    std::shared_ptr<int> sp = std::make_shared<int>(300);
	    std::weak_ptr<int> wp = sp;  // Does not increase reference count
	    std::cout << "Weak Pointer Expired: " << wp.expired() << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try resetting the shared_ptr and check if weak_ptr is expired.**
	- **6. Your Task**
	- 1️⃣ Create a unique_ptr to store an integer and print its value.
	- 2️⃣ Create a shared_ptr and share it between **two functions**.
	- 3️⃣ Use a weak_ptr and check if the object still exists before accessing it.
	- Next, we’ll learn about **Templates in C++ (Generic Programming)!** 🚀 Let me know when you’re ready!
- **Step 19: Templates in C++ (Generic Programming)**
  collapsed:: true
	- **1. What Are Templates?**
	- •	Templates allow us to write **generic** functions and classes.
	- •	Instead of writing separate functions for int, double, and char, we write **one template function**.
	- **2. Function Templates**
	- A function template allows **one function** to work with **any data type**.
	- **Example: Function Template**
	- ```
	  #include <iostream>
	  // Template function
	  template <typename T>
	  T add(T a, T b) {
	    return a + b;
	  }
	  int main() {
	    std::cout << "Sum of integers: " << add(10, 20) << std::endl;
	    std::cout << "Sum of doubles: " << add(5.5, 2.3) << std::endl;
	    
	    return 0;
	  }
	  ```
	- ✅ **Try calling add() with different data types!**
	- **3. Class Templates**
	- A class template allows **one class** to handle multiple data types.
	- **Example: Class Template**
	- ```
	  #include <iostream>
	  // Template class
	  template <typename T>
	  class Box {
	  private:
	    T value;
	  public:
	    Box(T v) : value(v) {}  // Constructor
	  void display() {
	        std::cout << "Value: " << value << std::endl;
	    }
	  };
	  int main() {
	    Box<int> intBox(100);
	    Box<double> doubleBox(45.67);
	    intBox.display();
	    doubleBox.display();
	    return 0;
	  }
	  ```
	- ✅ **Try creating an object of Box<std::string>!**
	- **4. Multiple Template Parameters**
	- We can have **multiple template parameters**.
	- **Example: Multiple Type Parameters**
	- ```
	  #include <iostream>
	  template <typename T1, typename T2>
	  class Pair {
	  private:
	    T1 first;
	    T2 second;
	  public:
	    Pair(T1 a, T2 b) : first(a), second(b) {}
	  void show() {
	        std::cout << "First: " << first << ", Second: " << second << std::endl;
	    }
	  };
	  int main() {
	    Pair<int, double> p1(10, 5.5);
	    Pair<std::string, char> p2("Hello", 'A');
	    p1.show();
	    p2.show();
	    return 0;
	  }
	  ```
	- ✅ **Try swapping the types (e.g., Pair<double, int>)!**
	- **5. Template Specialization**
	- Sometimes, we need a **special case** for a specific data type.
	- **Example: Template Specialization**
	- ```
	  #include <iostream>
	  template <typename T>
	  class Printer {
	  public:
	    void show(T value) {
	        std::cout << "Value: " << value << std::endl;
	    }
	  };
	  // Specialization for `char`
	  template <>
	  class Printer<char> {
	  public:
	    void show(char value) {
	        std::cout << "Character: " << value << std::endl;
	    }
	  };
	  int main() {
	    Printer<int> intPrinter;
	    Printer<char> charPrinter;
	    intPrinter.show(100);
	    charPrinter.show('A');
	    return 0;
	  }
	  ```
	- ✅ **Try adding specialization for std::string!**
	- **6. Your Task**
	- 1️⃣ Create a **function template** for finding the maximum of two values.
	- 2️⃣ Create a **class template** for a Stack that can store elements of any type.
	- 3️⃣ Implement **template specialization** for std::string to handle text differently.
	- Next, we’ll learn about **Advanced C++ Concepts like Move Semantics and Lambda Expressions!** 🚀 Let me know when you’re ready!
- **Step 20: Move Semantics & Lambda Expressions in C++**
  collapsed:: true
	- **1. Move Semantics (Efficient Resource Transfer)**
	- By default, C++ uses **copy semantics**, meaning when an object is assigned or passed to a function, it is **copied**. However, copying large objects is **slow**.
	- Move semantics **transfers ownership** instead of copying, making operations much faster. It is done using **rvalue references (&&) and std::move()**.
	- **2. Copy vs. Move Constructor**
	- Let’s see how copy and move constructors work.
	- **Example: Copy Constructor (Inefficient)**
	- ```
	  #include <iostream>
	  #include <vector>
	  class Data {
	  public:
	    std::vector<int> values;
	    Data(std::vector<int> v) : values(v) {}  // Copy constructor
	    void show() {
	        std::cout << "Size: " << values.size() << std::endl;
	    }
	  };
	  int main() {
	    std::vector<int> vec = {1, 2, 3, 4, 5};
	    Data d1(vec);  // Copying data (expensive)
	    d1.show();
	    return 0;
	  }
	  ```
	- ✅ **This is inefficient because it copies vec.**
	- **Example: Move Constructor (Efficient)**
	- We use std::move() to **transfer ownership** instead of copying.
	- ```
	  #include <iostream>
	  #include <vector>
	  class Data {
	  public:
	    std::vector<int> values;
	    // Move Constructor
	    Data(std::vector<int>&& v) : values(std::move(v)) {}
	    void show() {
	        std::cout << "Size: " << values.size() << std::endl;
	    }
	  };
	  int main() {
	    std::vector<int> vec = {1, 2, 3, 4, 5};
	    Data d1(std::move(vec));  // Moves data (efficient)
	    d1.show();
	    std::cout << "Original vector size: " << vec.size() << std::endl;  // Now empty
	    return 0;
	  }
	  ```
	- ✅ **Try printing vec.size() after std::move(vec). It should be 0 because ownership was transferred!**
	- **3. Lambda Expressions (Short Anonymous Functions)**
	- Lambda expressions provide **inline functions** without needing a separate function declaration.
	- **Basic Syntax**
	- ```
	  [ capture ] (parameters) -> return_type { function_body }
	  ```
	- **4. Example: Simple Lambda**
	- ```
	  #include <iostream>
	  int main() {
	    auto greet = []() { std::cout << "Hello, Lambda!" << std::endl; };
	    greet();  // Call the lambda function
	    return 0;
	  }
	  ```
	- ✅ **Try modifying the lambda to print your name!**
	- **5. Lambda with Parameters**
	- ```
	  #include <iostream>
	  int main() {
	    auto add = [](int a, int b) { return a + b; };
	    
	    std::cout << "Sum: " << add(10, 20) << std::endl;
	    return 0;
	  }
	  ```
	- ✅ **Try adding a third parameter!**
	- **6. Capturing Variables in Lambda**
	- Lambdas can **capture** variables from the surrounding scope.
	- **Example: Capturing by Value [=]**
	- ```
	  #include <iostream>
	  int main() {
	    int x = 10;
	    
	    auto printX = [=]() { std::cout << "Value of x: " << x << std::endl; };
	    
	    printX();  // Uses x from outer scope
	    return 0;
	  }
	  ```
	- ✅ **Try changing [=] to [x]. It will capture only x instead of all variables.**
	- **Example: Capturing by Reference [&]**
	- ```
	  #include <iostream>
	  int main() {
	    int x = 10;
	    
	    auto modifyX = [&]() { x += 5; };  // Captures x by reference
	    modifyX();
	    std::cout << "Modified x: " << x << std::endl;  // x is changed
	    return 0;
	  }
	  ```
	- ✅ **Try capturing multiple variables [&x, &y].**
	- **7. Lambda with std::sort()**
	- Lambdas are often used with STL functions like std::sort().
	- ```
	  #include <iostream>
	  #include <vector>
	  #include <algorithm>
	  int main() {
	    std::vector<int> nums = {5, 3, 8, 1, 2};
	    std::sort(nums.begin(), nums.end(), [](int a, int b) { return a > b; });
	    for (int n : nums) {
	        std::cout << n << " ";
	    }
	    return 0;
	  }
	  ```
	- ✅ **This sorts the vector in descending order using a lambda!**
	- **8. Your Task**
	- 1️⃣ Create a class with a **move constructor** and demonstrate std::move().
	- 2️⃣ Write a **lambda function** that takes two numbers and returns their product.
	- 3️⃣ Modify std::sort() to sort a list of names **by length** using a lambda.
	- **Next Steps: Mastering File Handling in C++!**
	- Let me know when you’re ready! 🚀