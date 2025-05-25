MODULE 1
---
### 1. Procedural Programming

- **Definition:** Programming paradigm based on the concept of procedure calls, where programs are structured as a sequence of instructions or procedures (functions).
- **Key Features:**
  - Emphasizes sequence, selection, and iteration.
  - Focus on functions to perform tasks.
  - Data and functions are separate.
- **Example:** Writing functions like `calculateSum()`, calling them from `main()`.

---

### 2. Overview of C

- Developed by Dennis Ritchie in early 1970s.
- A procedural programming language, widely used for system and application development.
- Features:
  - Low-level memory access using pointers.
  - Simple, efficient, portable.
  - Supports structured programming.
- Key components: Variables, data types, functions, control flow, pointers.

---

### 3. Types in C

- **Primary data types:**
  - `int` — integer values.
  - `float` — single-precision floating-point.
  - `double` — double-precision floating-point.
  - `char` — single characters.
- **Derived types:**
  - Arrays, pointers, structures, unions.
- **Qualifiers:**
  - `signed`, `unsigned`, `short`, `long`.
- **Example:**

```c
int age = 25;
float price = 10.5;
char letter = 'A';
```

---

### 4. Operators and Expressions

- **Operators:**
  - Arithmetic: `+`, `-`, `*`, `/`, `%`
  - Relational: `==`, `!=`, `<`, `>`, `<=`, `>=`
  - Logical: `&&`, `||`, `!`
  - Bitwise: `&`, `|`, `^`, `~`, `<<`, `>>`
  - Assignment: `=`, `+=`, `-=`, etc.
- **Expressions:** Combination of variables, constants, operators that produce a value.
- **Operator precedence** governs order of evaluation.
- Example:
  
```c
int sum = a + b * c; // multiplication before addition
```

---

### 5. Scope and Lifetime

- **Scope:** Region of program where an identifier is accessible.
  - **Local scope:** Inside a block or function.
  - **Global scope:** Outside all functions, throughout file.
- **Lifetime:** Duration variable exists in memory.
  - Automatic (local variables) — exist during function execution.
  - Static (with `static` keyword) — persist throughout program.
  - Dynamic (via pointers and heap)
- Example:

```c
int globalVar; // global scope

void func() {
    int localVar; // local scope
}
```

---

### 6. Constants

- Values that don’t change during program execution.
- Types:
  - **Literal constants:** numbers, characters like `10`, `'A'`.
  - **Defined constants:** `#define PI 3.14`
  - **`const` keyword:** e.g. `const int days = 7;`
  
---

### 7. Pointers

- Variables holding memory addresses.
- Enable direct memory access and dynamic memory management.
- Pointer declaration: `int *p;`
- Operators:
  - `&` (address-of), `*` (dereference)
- Example:

```c
int x = 10;
int *p = &x;  // p stores address of x
printf("%d", *p); // outputs 10
```

---

### 8. Arrays

- Collection of elements of the same type stored contiguously.
- Declaration: `int arr[10];`
- Access by index: `arr[0]`, `arr[1]`
- Arrays decay to pointers in many expressions.
- Example:

```c
int marks[3] = {80, 90, 85};
printf("%d", marks[1]); // 90
```

---

### 9. References

- C itself does **not** have references (a C++ feature).
- Closest in C: pointers used to simulate pass-by-reference.

---

### 10. Control Flow

- Statements to direct the order of execution.
- Constructs:
  - **Conditional:** `if`, `else if`, `else`, `switch`
  - **Loops:** `for`, `while`, `do-while`
  - **Jump:** `break`, `continue`, `goto`, `return`
- Example:

```c
for (int i=0; i<5; i++) {
   printf("%d\n", i);
}
```

---

### 11. Functions and Program Structure

- Modular blocks of code performing specific tasks.
- Declared with return type, name, parameters.
- Syntax:

```c
returnType functionName(parameter list) {
  // body
}
```

- `main` is program entry point.
- Can call functions, pass parameters by value (or pointer for reference-like behavior).

Example:

```c
int add(int a, int b) {
    return a + b;
}

int main() {
    int sum = add(3,4);
}
```

---

### 12. Namespaces

- **C does not support namespaces** (C++ feature).
- To avoid name conflicts, use prefixes or static functions for internal linkage.

---

### 13. Error Handling

- C has no built-in exception handling.
- Typical techniques:
  - Return error codes.
  - Use global `errno`.
  - Check function return values.
- Example: `FILE *fp = fopen("file.txt", "r"); if(fp == NULL) { perror("Error opening file"); }`

---

### 14. Input and Output (C-style)

- Provided via standard library `<stdio.h>`.
- Functions:
  - `printf` - formatted output to console.
  - `scanf` - formatted input from console.
  - `getchar`/`putchar` - single character I/O.
- Example:

```c
int age;
printf("Enter your age: ");
scanf("%d", &age);
printf("Your age is %d\n", age);
```

---

### 15. Library Functions

- **String functions (`<string.h>`):**
  - `strlen`, `strcpy`, `strcmp`, `strcat`
- **Math functions (`<math.h>`):**
  - `pow`, `sqrt`, `sin`, `cos`, `abs`
- **General utilities (`<stdlib.h>`):**
  - `malloc`, `free`, `atoi`, `exit`, `rand`, `qsort`

---

### 16. Command Line Arguments

- Parameters passed to `main` function:

```c
int main(int argc, char *argv[]) {
    // argc = argument count
    // argv = array of argument strings
}
```

- `argv[0]` is program name, `argv[1]` onward are arguments.

---

### 17. Pre-processor Directives

- Commands to pre-processor before compilation.
- Start with `#`.
- Common directives:
  - `#include` - include header files
  - `#define` - macro definitions
  - `#ifdef, #ifndef, #endif` - conditional compilation
- Example:

```c
#define PI 3.14159
#include <stdio.h>
```

---

# MODULE 2 

### **1. Single Line Comments**

- **C**:
  - Single-line comments are supported in later versions of C (`C99` onwards) using `//`.
  - Previously (before `C99`), only multi-line comments (`/* */`) were supported.
  
  ```c
  // This is a single-line comment in C (C99 or later)
  /* This is a multi-line comment in C */
  ```

- **C++**:
  - Single-line comments with `//` have always been supported (since its inception).
  - Multi-line comments (`/* */`) are also allowed.

  ```cpp
  // This is a single-line comment in C++
  /* This is a multi-line comment in C++ */
  ```

---

### **2. Local Variable Declaration within Function Scope**

- **C**:
  - All local variables must be declared at the beginning of a block (before any executable code).
  
  ```c
  void example() {
      int a = 5;  // Declaration at the start of the block
      a = a + 10;
      printf("%d", a);
  }
  ```

- **C++**:
  - Variables can be declared anywhere within a function's scope, giving greater flexibility. This allows variables to be initialized closer to their first use, improving readability and reducing errors.
  
  ```cpp
  void example() {
      int a = 5;
      a = a + 10;
      float b = 3.14;  // Declaration anywhere within the scope
      std::cout << a << " " << b;
  }
  ```

---

### **3. Function Declaration and Overloading**

- **C**:
  - Function overloading is **not supported in C**.
  - All functions must have unique names.
  - Function prototypes must match the exact parameters when called.
  
  ```c
  void printInt(int x) {
      printf("Integer: %d\n", x);
  }

  // Cannot overload functions in C
  ```

- **C++**:
  - Function overloading is supported.
  - You can declare multiple functions with the same name as long as their parameter lists differ.
  
  ```cpp
  void print(int x) {
      std::cout << "Integer: " << x << std::endl;
  }
  
  void print(double x) {
      std::cout << "Double: " << x << std::endl;
  }
  ```

---

### **4. Stronger Type Checking**

- **C**:
  - Weaker type checking.
  - Implicit conversion between incompatible data types is allowed (though sometimes this may lead to unexpected results).
  
  ```c
  int a = 10.5;  // Allowed; float is truncated to int.
  ```

- **C++**:
  - Implements stronger type checking.
  - Implicit conversions are more restricted to prevent accidental data loss.
  - Use `static_cast`, `reinterpret_cast`, or `dynamic_cast` for explicit conversions (covered in point 9).

  ```cpp
  int a = 10.5;  // Generates a warning in C++
  int b = static_cast<int>(10.5);  // Explicit casting in C++
  ```

---

### **5. Reference Variables**

- **C**:
  - Does not support references.
  - Manipulation of variables via pointers is encouraged for such scenarios.
  
  ```c
  void modify(int *ptr) {
      *ptr = 10;
  }

  int x = 5;
  modify(&x);  // Pass pointer
  ```

- **C++**:
  - Reference variables (`&`) are supported and provide a safer and more readable way to access variables by reference.

  ```cpp
  void modify(int &ref) {
      ref = 10;  // Modifies the actual variable
  }

  int x = 5;
  modify(x);  // Pass by reference
  ```

---

### **6. Parameter Passing (Value vs. Reference)**

- **C**:
  - Supports only **pass-by-value** and can use **pointers** to simulate pass-by-reference.
  
  ```c
  void modify(int *x) {  // Simulates pass-by-reference
      *x = 20;
  }
  int a = 10;
  modify(&a);
  ```

- **C++**:
  - Supports **pass-by-value**, **pass-by-reference**, and **pass-by-pointer**, making it more versatile.
  
  ```cpp
  void modify(int &x) {  // Pass by reference
      x = 20;
  }
  int a = 10;
  modify(a);
  ```

---

### **7. Passing Pointers by Value or Reference**

- **C**:
  - Pointers are passed **by value**, but you can modify the value at the address they point to.

  ```c
  void modify(int *ptr) {
      *ptr = 50;  // Modifies the value at the address
  }
  ```

- **C++**:
  - You can pass pointers **by value** or **by reference** to explicitly control whether the pointer itself should be modifiable.

  ```cpp
  void modify(int *&ptr) {  // Passing pointer by reference
      ptr = new int(50);
  }
  ```

---

### **8. define Constants vs. const**

- **C**:
  - Constants are created using `#define` preprocessor macros.
  - Does not provide type-checking for constants.
  
  ```c
  #define PI 3.14
  ```

- **C++**:
  - `const` is preferred over `#define` because it provides type checking.
  
  ```cpp
  const double PI = 3.14;
  ```

---

### **9. `new` and `delete`**

- **C**:
  - Uses `malloc()` and `free()` for dynamic memory allocation and deallocation.
  
  ```c
  int *ptr = (int *)malloc(sizeof(int) * 5);
  free(ptr);
  ```

- **C++**:
  - Introduces `new` and `delete` operators for dynamic memory management, which are type-safe and more convenient.
  
  ```cpp
  int *ptr = new int[5];
  delete[] ptr;
  ```

---

### **10. Typecasting Operators**

- **C**:
  - Uses C-style casting `(type)` which is less explicit and error-prone.
  
  ```c
  double x = 3.14;
  int y = (int)x;  // C-style cast
  ```

- **C++**:
  - Introduces specialized typecasting operators like `static_cast`, `dynamic_cast`, `const_cast`, and `reinterpret_cast`, which are more readable and safer.

  ```cpp
  double x = 3.14;
  int y = static_cast<int>(x);  // C++ type casting
  ```

---

### **11. Inline Functions vs. Macros**

- **C**:
  - Uses macros (`#define`) for code substitution, which can lead to unintended side effects due to lack of type checking.
  
  ```c
  #define SQUARE(x) (x * x)
  ```

- **C++**:
  - Introduces `inline` functions, which provide better type checking and avoid macro pitfalls.

  ```cpp
  inline int square(int x) {
      return x * x;
  }
  ```

---

### **12. Default Arguments**

- **C**:
  - Default arguments are **not supported** in function declarations.

- **C++**:
  - Supports default arguments, making function calls more flexible.
  - Example:

  ```cpp
  void print(int x = 10) {
      std::cout << x;
  }
  print();  // Prints 10
  print(20);  // Prints 20
  ```

---
```
detailed empashis on some topics 
```
---

### **6. Parameter Passing: Pass-by-Value, Pass-by-Reference, and Passing Pointers**

#### **Pass-by-Value (C & C++)**:
- The function **receives a copy** of the value passed as an argument.
- Any changes made to the parameter inside the function **do not affect the original variable** in the calling function.
- **Example** in C/C++:
  ```c
  void increment(int value) {
      value = value + 1;  // Modifies only the local copy inside the function
  }

  int main() {
      int x = 10;
      increment(x);  // Original x remains unchanged
      printf("%d", x);  // Output: 10
      return 0;
  }
  ```

#### **Pass-by-Pointer (Simulating Reference in C)**:
- A pointer to the original variable is passed to the function.
- The function can modify the original variable by dereferencing the pointer.
- **Example in C**:
  ```c
  void increment(int *value) {
      *value = *value + 1;  // Modifies the value at the address
  }
  
  int main() {
      int x = 10;
      increment(&x);  // Passes the address of x
      printf("%d", x);  // Output: 11
      return 0;
  }
  ```

#### **Pass-by-Reference (Available in C++)**:
- The function works directly on the memory location of the argument by using references (`&`).
- The original variable is modified without needing to explicitly pass its address/pointer.
- **Example in C++**:
  ```cpp
  void increment(int &value) {
      value = value + 1;  // Directly modifies the original variable
  }
  
  int main() {
      int x = 10;
      increment(x);  // Directly passes x by reference
      std::cout << x;  // Output: 11
      return 0;
  }
  ```

#### **Passing Pointers: By Value or By Reference (C++)**:
- **By Value**: A copy of the pointer is passed, so the pointer's address itself can't be modified in the function.
- **By Reference**: A reference to the pointer is passed so the function can modify the pointer itself.

- **Example of Passing Pointers by Reference**:
  ```cpp
  void modifyPointer(int *&ptr) {  // Note the `*&`
      ptr = new int(42);  // Pointer itself is modified
  }
  ```

---

### **8. `#define Constants vs. const (Constants and Type Checking)**

#### **C: Using `#define`**:
- A `#define` is a **preprocessor directive** and not a language feature. It acts like a text replacement.
- `#define` constants don’t have types, so there’s no type checking during compilation.
- **Risks**:
  - Can lead to unexpected behavior (e.g., improper evaluation of macro expressions).
- **Example** in C:
  ```c
  #define PI 3.14
  printf("%f", PI);  // Works fine
  ```

#### **C++: Using `const`**:
- **Type-Safe**: `const` ensures type checking and scoping rules.
- Constants declared with `const` are part of the type system.
- **Example** in C++:
  ```cpp
  const double PI = 3.14;  // Typed constant
  ```

#### Comparison Summary:
| Feature               | `#define`         | `const`               |
|-----------------------|-------------------|-----------------------|
| **Scope**             | Global, no scope | Scoped within blocks  |
| **Type Checking**     | None             | Enforced by compiler  |
| **Debugging Info**    | Not visible      | Clearly accessible    |

---

### **9. `new` and `delete` vs. `malloc()` and `free()`**

#### `malloc()` and `free()` (C):
- Functions used for **dynamic memory allocation** in C.
- Allocated memory must be explicitly freed to avoid memory leaks.
- **Important Notes**:
  - Does not call constructors or destructors.
  - Must manually cast return pointer to appropriate type.
  
- **Example in C**:
  ```c
  int *arr = (int *)malloc(sizeof(int) * 5);  // Allocate memory for 5 integers
  free(arr);  // Deallocate the memory
  ```

#### `new` and `delete` (C++):
- Operators for **dynamic memory management** in C++.
- Automatically calls constructors (`new`) and destructors (`delete`).
- Typecasting is not required, unlike `malloc()`.
  
- **Example in C++**:
  ```cpp
  int *arr = new int[5];  // Allocate memory for an array
  delete[] arr;  // Deallocate memory
  ```

#### Comparison:

| Feature              | `malloc()` / `free()`      | `new` / `delete`          |
|----------------------|---------------------------|---------------------------|
| **Type Safety**      | No, casting required      | Yes, inherently type-safe |
| **Constructor/Destructor** | No                  | Yes                      |
| **Syntax**           | Function-like            | Operator-like             |

---

### **10. Inline Functions vs. Macros**

#### Inline Functions (C++):
- Functions declared with the `inline` keyword.
- Inline expansion avoids function call overhead while retaining type checking and scoping.
- Preferred over macros since they are safer and easier to debug.

- **Example**:
  ```cpp
  inline int square(int x) {
      return x * x;
  }
  ```

#### Macros (C and C++):
- Simple text substitution performed during preprocessing.
- No type checking occurs, and can lead to side effects due to improper argument evaluation.

- **Example** of Macro Issue:
  ```c
  #define SQUARE(x) (x * x)
  SQUARE(1 + 2)  // Expands to (1 + 2 * 1 + 2), which evaluates incorrectly
  ```

#### Comparison:
| Feature              | Macros (`#define`)         | Inline Functions          |
|----------------------|---------------------------|---------------------------|
| **Type Checking**    | None                     | Yes                       |
| **Debugging**        | Hard to debug            | Debugging supported       |
| **Efficiency**       | Fast (but unsafe)        | Fast and safe             |

---

### **12. Default Arguments**

#### **C**:
- **Not supported in C**. Function calls must pass exactly the number of arguments specified.

#### **C++**:
- Allows you to specify default arguments for parameters in a function declaration.
- Default values are assigned if no value is passed during the function call.
  
- **Example**:
  ```cpp
  void greet(std::string name = "John") {
      std::cout << "Hello, " << name;
  }

  int main() {
      greet();  // Output: Hello, John
      greet("Alice");  // Output: Hello, Alice
      return 0;
  }
  ```

---

### **13. Typecasting Operators**

#### **C**:
- Uses **C-style casting**, which is less explicit and may lead to unsafe type conversions.
- **Example**:
  ```c
  double x = 5.5;
  int y = (int)x;  // C-style cast
  ```

#### **C++**:
- Introduces stricter and more explicit typecasting operators:
  1. **`static_cast`**: General-purpose cast (e.g., converting numeric types like `double` to `int`).
  2. **`dynamic_cast`**: Works only with polymorphic types (classes with virtual functions).
  3. **`const_cast`**: Adds or removes `const` from a variable.
  4. **`reinterpret_cast`**: Converts between unrelated pointer types.

- **Example of explicit C++ typecasting**:
  ```cpp
  double x = 5.5;
  int y = static_cast<int>(x);  // Safer, explicit cast
  ```

#### Comparison Summary:
| Feature         | C-Style Cast | C++ Typecasting |
| --------------- | ------------ | --------------- |
| **Readability** | Low          | High            |
| **Type Safety** | Limited      | Strong          |

---

# MODULE 3


### **Object-Oriented Programming (OOP) Fundamentals: Comprehensive Notes**

Object-Oriented Programming (OOP) is an advanced programming paradigm that organizes software design around **objects** rather than functions or logic. Objects hold data (attributes) and code (methods) together, promoting modularity, reusability, and scalability in software development. Below is a detailed explanation of the key OOP fundamentals mentioned:

---

### **1. Necessity for OOP**

#### **Why Do We Need OOP?**

1. **Limitations of Procedural Programming**:
   - Procedural programming (like C) organizes programs using procedures (functions).
   - It leads to challenges in managing large-scale applications due to **lack of modularity**, **tight coupling between data and procedures**, and **difficulty in maintaining code**.

2. **Advantages of OOP**:
   - **Modularity**: Complex code is divided into smaller, manageable pieces (i.e., classes and objects).
   - **Code Reusability**: Features like inheritance allow the reuse of existing code.
   - **Improved Reliability**: Encapsulation protects sensitive data and ensures controlled access.
   - **Representation of Real-World Models**: Objects in OOP closely simulate real-world entities.

#### **Applications**:
- Developing large-scale software systems: E-commerce platforms, operating systems, games.
- High demand in fields where modular design and extensibility are critical, such as software frameworks or mobile apps.

---

### **2. Data Hiding**

#### **Definition**:
- **Data Hiding** refers to restricting access to specific parts of an object's data only to authorized parts within the program, preventing unintended interference or misuse.

#### **Implementation**:
- Achieved using **access specifiers** in languages like C++.
  - **`private`** (default): Only accessible within the class.
  - **`protected`**: Accessible within the class and derived classes.
  - **`public`**: Accessible from anywhere in the program.

#### **Example in C++**:
```cpp
class Student {
private:
    int rollNo;  // Hidden from outside access
public:
    void setRollNo(int r) { rollNo = r; }
    int getRollNo() { return rollNo; }
};

int main() {
    Student s1;
    s1.setRollNo(101);  // Controlled access using public functions
    std::cout << s1.getRollNo();  // Output: 101
}
```

#### **Importance**:
- Protects sensitive data from accidental corruption or malicious modifications.
- Encourages **data security** and adherence to the principle of least privilege.

---

### **3. Data Abstraction**

#### **Definition**:
- **Data Abstraction** hides implementation details of an object and only exposes the essential features required to interact with it.

#### **Key Mechanism**:
- In OOP, abstraction is achieved using:
  - **Abstract classes** (classes containing pure virtual functions).
  - **Interfaces** (functions with no implementation).

#### **Example in C++**:
```cpp
class Shape {  // Abstract class
public:
    virtual void area() = 0;  // Pure virtual function
};

class Circle : public Shape {
private:
    double radius;
public:
    Circle(double r) { radius = r; }
    void area() override { std::cout << 3.14 * radius * radius; }
};

int main() {
    Shape* s = new Circle(5);
    s->area();  // Output: 78.5
}
```

#### **Importance**:
- Helps in **designing clean, modular code** by separating what an object does from how it does it.
- Abstract classes and interfaces simplify complex systems and make systems scalable.

---

### **4. Encapsulation**

#### **Definition**:
- **Encapsulation** is the process of wrapping an object's data and methods into a single unit (class) and controlling access to it via access specifiers.

#### **Features**:
- Encapsulation ensures:
  - Data hiding.
  - Controlled access to an object's attributes and methods through an interface (i.e., public methods).

#### **Example in C++**:
```cpp
class BankAccount {
private:
    double balance;
public:
    void deposit(double amount) { balance += amount; }
    double getBalance() { return balance; }
};

int main() {
    BankAccount account;
    account.deposit(1000);
    std::cout << account.getBalance();  // Output: 1000
}
```

#### **Importance**:
- Protects object integrity by preventing direct manipulation of attributes.
- Enables **maintainability** by controlling how changes in code affect the object.

---

### **5. Procedural Abstraction**

#### **Definition**:
- **Procedural Abstraction** refers to hiding the implementation details of specific procedures (functions) and exposing them as a simple interface.

#### **Example in C++**:
```cpp
double calculateArea(double radius) {
    return 3.14 * radius * radius;  // Procedural abstraction
}

int main() {
    double area = calculateArea(5);  // Users don't need to know the formula
    std::cout << area;  // Output: 78.5
}
```

#### **Importance**:
- Simplifies interaction with procedures/functions.
- Encourages modularity, improving readability and reducing complexity.

---

### **6. Class**

#### **Definition**:
- **Class** is a blueprint or template for creating objects. It defines the data (attributes) and behavior (methods) of the objects.
- **Classes encapsulate data and functionality**, making them the building blocks of OOP.

#### **Structure of a Class**:
```cpp
class ClassName {
private:  // Attributes hidden from outside
    int data;
public:
    void method() {  // Public method (interface)
        // Implementation
    }
};
```

#### **Example**:
```cpp
class Car {
private:
    int speed;
public:
    void setSpeed(int s) { speed = s; }
    int getSpeed() { return speed; }
};

int main() {
    Car c1;  // Create an object of class Car
    c1.setSpeed(100);
    std::cout << c1.getSpeed();  // Output: 100
}
```

#### **Importance**:
- Promotes **modularity** and organizes code into reusable components.
- Acts as the blueprint for individual **objects**.

---

### **7. Object**

#### **Definition**:
- **Object** is an instance of a class. An object represents a real-world entity by combining data and behavior defined by the class.
- **Objects have state, behavior, and identity**:
  - **State**: Data fields or attributes (e.g., speed, color).
  - **Behavior**: Methods or functions (e.g., move(), stop()).
  - **Identity**: A unique memory address differentiates one object from another.

#### **Example**:
```cpp
class Car {
private:
    int speed;
public:
    void setSpeed(int s) { speed = s; }
    int getSpeed() { return speed; }
};

int main() {
    Car car1;  // Create an object
    Car car2;  // Create another object
    car1.setSpeed(120);
    car2.setSpeed(100);
    std::cout << "Car 1 Speed: " << car1.getSpeed() << std::endl;  // Output: 120
    std::cout << "Car 2 Speed: " << car2.getSpeed() << std::endl;  // Output: 100
}
```

#### **Importance**:
- Represents specific instances with their own data.
- Enables interaction between components via method calls on objects.

---

### **Applications in OOP**

1. **Data Security**:
   - Data hiding and encapsulation protect sensitive variables from unauthorized access.

2. **Code Reusability**:
   - Classes and objects facilitate code reuse through inheritance.

3. **Scalability**:
   - Abstraction simplifies large software systems by focusing on essential operations.

4. **Real-world Modeling**:
   - Classes and objects closely simulate real-world entities, making the design intuitive.

---


```
MODULE 4
```

## Detailed Notes on C++ Extensions Providing Object-Oriented Programming (OOP) Facilities

C++ extends the C language by introducing features that support Object-Oriented Programming (OOP). These extensions enable better data abstraction, encapsulation, inheritance, and polymorphism. Below is a detailed exploration of key OOP facilities introduced by C++ beyond C.

---

### 1. Scope of Class

- **Definition:**  
  In C++, a class acts as a user-defined data type that bundles data (attributes) and functions (methods) into a single logical entity. The scope of a class means the region in the program where the class name and its members (variables and functions) are valid and accessible.

- **Scope Inside a Class:**  
  - All members defined inside the class are within the class’s scope.
  - Members can be accessed directly only from within member functions or friend functions/classes.
  - Outside the class, members are accessed through objects or pointers to objects.

- **Example:**
  ```cpp
  class Car {
      int speed;  // private by default
  public:
      void setSpeed(int s) { speed = s; }  // member function inside class scope
      int getSpeed() { return speed; }
  };
  
  int main() {
      Car c;
      c.setSpeed(100);    // Access via object 'c'
      int s = c.getSpeed();
  }
  ```

---

### 2. Scope Resolution Operator (`::`)

- **Purpose:**  
  The scope resolution operator `::` is used to define member functions outside the class definition and to access static members or global scope when overshadowed by local scope.

- **Usage:**  
  - Define a member function outside the class body.
  - Access static data members or functions.
  - Refer to global variables or functions when overshadowed by local names.

- **Example: Defining Member Functions Outside the Class**
  ```cpp
  class Person {
      int age;
  public:
      void setAge(int a);     // declaration
      int getAge();
  };

  void Person::setAge(int a) {  // definition outside class using ::
      age = a;
  }

  int Person::getAge() {
      return age;
  }
  ```

---

### 3. Member Functions of a Class

- **Definition:**  
  Functions declared inside a class that operate on the data members of that class. They define the behavior of objects.

- **Key Points:**  
  - Can be defined inside or outside the class.
  - Can access all members of the class based on access specifiers.
  - Can be `const` to ensure they do not modify the object.
  - May be inline for performance.

- **Example:**
  ```cpp
  class Rectangle {
      int width, height;
  public:
      void setDimensions(int w, int h) {
          width = w; height = h;
      }
      int area() const {  // const member function
          return width * height;
      }
  };
  ```

---

### 4. Access Specifiers: `private`, `protected`, `public`

- **Purpose:**  
  Control the accessibility of class members to enforce encapsulation and data hiding.

- **Access Levels:**
  | Specifier  | Accessibility                               |
  |------------|---------------------------------------------|
  | `private`   | Accessible only within the class itself     |
  | `protected` | Accessible within the class and derived classes (inheritance) |
  | `public`    | Accessible from anywhere the object is visible |

- **Default Access:**  
  - Members of a `class` are `private` by default.
  - Members of a `struct` are `public` by default.

- **Example:**
  ```cpp
  class BankAccount {
  private:
      double balance;  // hidden from outside
  protected:
      int accountNumber; // accessible in derived classes
  public:
      void deposit(double amount) {
          if(amount > 0) balance += amount;
      }
      double getBalance() { return balance; }
  };
  ```

---

### 5. The `this` Keyword

- **Definition:**  
  A pointer available inside all non-static member functions that points to the object for which the member function is called.

- **Use Cases:**  
  - Differentiate members from parameters or local variables when they have the same name.
  - Return the current object pointer from member functions (enabling method chaining).
  - Pass the current object to other functions.

- **Example:**
  ```cpp
  class Sample {
      int x;
  public:
      void setX(int x) {
          this->x = x;   // 'this' differentiates member 'x' from parameter 'x'
      }
      Sample* getPointer() {
          return this;  // returns pointer to current object
      }
  };
  ```

---

### 6. Constructors and Destructors

#### Constructors
- **Definition:**  
  Special member functions automatically called when an object is created to initialize the object.

- **Features:**  
  - Same name as class.
  - No return type, not even void.
  - Can be overloaded.
  - Can be parameterized or default.
  - Supports member initializer lists for initialization.

- **Example:**
  ```cpp
  class Point {
      int x, y;
  public:
      Point() { x = 0; y = 0; }  // default constructor
      Point(int xVal, int yVal) : x(xVal), y(yVal) {}  // parameterized constructor
  };
  ```

#### Destructors
- **Definition:**  
  Special member function automatically called when an object goes out of scope or is deleted, used for cleanup.

- **Features:**  
  - Same name as class preceded by `~`.
  - No parameters and no return type.
  - Only one destructor per class.
  - Executes automatically; cannot be called explicitly.

- **Example:**
  ```cpp
  class Resource {
  public:
      Resource() { /* allocate resources */ }
      ~Resource() { /* free resources */ }
  };
  ```

---

### 7. Friend Classes and Friend Functions

- **Purpose:**  
  Allow external functions or other classes to access private and protected members of a class.

- **Friend Function:**  
  - Declared with `friend` keyword inside the class.
  - Not a member of the class but has access rights.

- **Friend Class:**  
  - Another class declared as friend has access to private/protected members of the declaring class.

- **Use Case:**  
  Helpful when two or more classes/functions need close cooperation but you don’t want to make members public.

- **Example:**
  ```cpp
  class Box {
  private:
      int length;
  public:
      Box() : length(0) {}
      friend void printLength(Box b);  // friend function declaration
  };

  void printLength(Box b) {
      // can access private member length because it's a friend
      std::cout << "Length: " << b.length << std::endl;
  }
  ```

  **Friend Class Example:**
  ```cpp
  class Engine {
      friend class Car;  // Car is friend of Engine
  private:
      int horsepower;
  public:
      Engine() : horsepower(120) {}
  };

  class Car {
  public:
      void showHorsepower(Engine &e) {
          std::cout << "Horsepower: " << e.horsepower << std::endl;  // allowed due to friendship
      }
  };
  ```

---

### 8. Exception Handling

- **Purpose:**  
  Handle runtime errors or exceptional situations gracefully without crashing the program.

- **Key Keywords:**  
  - `try`: Block where exceptions may occur.
  - `throw`: Statement to throw an exception.
  - `catch`: Block to catch and handle exceptions.

- **C++ Exception Model:**  
  When an exception is thrown inside `try`, control passes to the matching `catch` block.

- **Syntax:**
  ```cpp
  try {
      // code that may throw exception
  }
  catch (ExceptionType e) {
      // handler code
  }
  ```

- **Example:**
  ```cpp
  #include <iostream>
  using namespace std;

  double divide(int a, int b) {
      if (b == 0) throw "Division by zero error!";
      return (double)a / b;
  }

  int main() {
      try {
          cout << divide(10, 2) << endl;
          cout << divide(5, 0) << endl;  // throws exception
      }
      catch (const char* msg) {
          cerr << "Error: " << msg << endl;
      }
      return 0;
  }
  ```

- **Notes:**
  - Exception handling allows separation of error-handling code from normal logic.
  - Can throw any type as exception, but standard practice is to throw objects or pointers derived from `std::exception`.
  - Supports multiple catch blocks for different exception types.

---

## Summary Table of Topics and Key Points

| Topic                     | Key Points                                                     | Example Highlight                   |
|---------------------------|----------------------------------------------------------------|-----------------------------------|
| Scope of Class            | Class members accessible within class, outside via object.    | `Car c; c.setSpeed(100);`         |
| Scope Resolution Operator | Define members outside class, access static/global scope.    | `void Person::setAge(int a) {}`   |
| Member Functions          | Members define behavior; can be inside/outside; const/mutable.| `int area() const;`                |
| Access Specifiers         | `private`, `protected`, `public` control access level.        | `private: double balance;`        |
| The `this` Keyword        | Pointer to current object inside member functions.             | `this->x = x;`                    |
| Constructors/Destructors  | Special functions for init/cleanup, automatic call.            | `Point() {}` and `~Resource() {}` |
| Friend Classes/Functions  | Grant external functions/classes access to private members.    | `friend void printLength(Box b);` |
| Exception Handling        | Try-throw-catch blocks for runtime errors with graceful exit. | `try { ... } catch (...) { ... }` |

---


---
# MODULE 5

## Enhanced Explanation of the Essentials of Object-Oriented Programming (OOP)

Object-Oriented Programming (OOP) is a widely used programming paradigm that models software design by organizing code into entities called **objects**, which are instances of **classes**. OOP helps create programs that are more modular, easier to maintain, and better able to mirror real-world entities and interactions.

---

## 1. Operator Overloading

### What is Operator Overloading?

Operators like `+`, `-`, `*`, or `<<` have predefined meanings for basic data types (like numbers). In OOP, **operator overloading** lets you define how these operators work with your own user-defined types (classes). This enables more intuitive and natural use of objects.

### Why is it Important?

Imagine you have a `Complex` number class. Without overloading, adding two complex numbers requires calling a method explicitly. With operator overloading, you can simply use the `+` operator, making code succinct and readable.

### Detailed Example:

```cpp
#include <iostream>

class Complex {
private:
    double real, imag;
public:
    Complex(double r=0, double i=0) : real(r), imag(i) {}
    
    // Overload '+' operator to add complex numbers
    Complex operator+(const Complex& obj) const {
        return Complex(real + obj.real, imag + obj.imag);
    }

    void display() const {
        std::cout << real << " + " << imag << "i\n";
    }
};

int main() {
    Complex c1(3.4, 2.1), c2(1.6, 7.8);
    Complex c3 = c1 + c2;    // operator+ invoked here
    c3.display();            // Output: 5 + 9.9i
    return 0;
}
```

- The operator `+` is redefined to add the respective real and imaginary parts.
- This approach lets objects be manipulated using natural mathematical expressions.

---

## 2. Inheritance

Inheritance is a fundamental OOP concept that **promotes code reuse** by enabling classes to acquire properties and behaviors from other classes.

### Single Inheritance

One class inherits from one base class.

**Real-World Analogy:**  
A `Dog` is a kind of `Animal`. So, `Dog` class inherits common features (eating, sleeping) from an `Animal` class.

**Example:**
```cpp
class Animal {
public:
    void eat() { std::cout << "Eating\n"; }
};

class Dog : public Animal {
public:
    void bark() { std::cout << "Barking\n"; }
};

int main() {
    Dog d;
    d.eat();  // inherited method
    d.bark();
}
```

### Multiple Inheritance

Derived class inherits from more than one base class. This allows combining functionalities.

**Example:**
```cpp
class Camera {
public:
    void click() { std::cout << "Click!\n"; }
};

class Phone {
public:
    void call() { std::cout << "Calling...\n"; }
};

class SmartPhone : public Camera, public Phone {};

int main() {
    SmartPhone sp;
    sp.click(); // from Camera
    sp.call();  // from Phone
}
```

**Caution:** Multiple inheritance can lead to complexity such as the "diamond problem," which C++ addresses with virtual inheritance.

---

## 3. Class Hierarchy

- Organizes classes from **general to specific**.
- Helps model real-world relationships.
  
### Why Important?

It provides clarity and structure, enabling polymorphic behavior.

**Example:**
```plaintext
Vehicle  (base class)
   ↑
Car  (derived class)
   ↑
ElectricCar (derived from Car)
```

### Usage Example:
```cpp
class Vehicle {
public:
    virtual void start() { std::cout << "Vehicle starting\n"; }
};

class Car : public Vehicle {
public:
    void start() override { std::cout << "Car starting\n"; }
};

class ElectricCar : public Car {
public:
    void start() override { std::cout << "Electric Car starting silently\n"; }
};

int main() {
    Vehicle* vehicles[] = { new Vehicle(), new Car(), new ElectricCar() };
    for(auto v : vehicles) v->start();

    // Output:
    // Vehicle starting
    // Car starting
    // Electric Car starting silently
}
```

---

## 4. Pointers to Objects

Pointers can reference objects dynamically, allowing flexible and efficient management of objects.

### Why use pointers to objects?

- Support **dynamic allocation** (creating objects at runtime).
- Essential for **polymorphism** (base class pointers referring to derived objects).
- Useful when working with collections of heterogeneous objects.

### Example:

```cpp
class Box {
public:
    int length;
    Box(int l) : length(l) {}
    void show() const { std::cout << "Length: " << length << "\n"; }
};

int main() {
    Box* ptr = new Box(10); // dynamic allocation
    ptr->show();
    delete ptr;  // always free dynamically allocated memory
}
```

---

## 5. Object Assignment

- **Default Assignment:** Copies each data member directly (shallow copy).
- Problems can arise if the members involve dynamically allocated resources, causing **double-free errors**.

### Deep vs. Shallow Copy

- **Shallow copy:** Copies pointer values, not the data they point to.
- **Deep copy:** Copies the actual data pointed to, creating independent copies.

### Custom Assignment Operator Example:

```cpp
class Demo {
    int* ptr;
public:
    Demo(int val) { ptr = new int(val); }
    
    // Copy constructor (deep copy)
    Demo(const Demo& d) {
        ptr = new int(*d.ptr);
    }
    
    // Assignment operator (deep copy)
    Demo& operator=(const Demo& d) {
        if(this == &d) return *this;  // self-assignment check
        
        delete ptr;          // free existing resource
        ptr = new int(*d.ptr);  // allocate and copy
        return *this;
    }
    
    ~Demo() { delete ptr; }
};
```

---

## 6. Polymorphism and Dynamic Binding

### What is Polymorphism?

Ability of a program to **handle objects of different types through the same interface**.

Types:
- **Compile-time (Static)**: function overloading, operator overloading.
- **Run-time (Dynamic)**: achieved with **virtual functions** and **inheritance**.

### Dynamic Binding

- Decisions made at runtime to call the correct function based on the actual object's type.
- Achieved using **virtual functions** in C++.

### Example Demonstrating Polymorphism:

```cpp
class Animal {
public:
    virtual void sound() { std::cout << "Animal sound\n"; }
};

class Cat : public Animal {
public:
    void sound() override { std::cout << "Meow\n"; }
};

class Dog : public Animal {
public:
    void sound() override { std::cout << "Woof\n"; }
};

void makeSound(Animal* a) {
    a->sound();  // calls the correct overridden method dynamically
}

int main() {
    Cat c;
    Dog d;
    makeSound(&c);  // Meow
    makeSound(&d);  // Woof
}
```

---

## 7. Virtual Functions

- Declared with `virtual` keyword in base class.
- Tell the compiler to look up the function in the derived class at runtime.
- Enable **run-time polymorphism**.

### Why Virtual Functions Matter?

Without virtual, the base class pointer would always call the base class method, causing incorrect behavior.

---

## 8. Function Overloading, Overriding, and Hiding

### Overloading

- Multiple functions with the **same name but different parameter types or count** within the same scope.
- Allows polymorphism at compile time.

**Example:**
```cpp
class Print {
public:
    void show(int i) { std::cout << "Int: " << i << "\n"; }
    void show(double d) { std::cout << "Double: " << d << "\n"; }
};
```

### Overriding

- Derived class provides its own implementation of a **virtual function** inherited from base.
- Function signature must be **identical**.

### Hiding

- Occurs when a derived class declares a function with the same name as one in the base class but different parameters.
- The base class version becomes hidden in the derived class's context.

**Example:**
```cpp
class Base {
public:
    void func(int) { std::cout << "Base func(int)\n"; }
};

class Derived : public Base {
public:
    void func() { std::cout << "Derived func()\n"; }
};

int main() {
    Derived d;
    // d.func(5);  // Error: Base func(int) is hidden
    d.func();       // OK: calls Derived func()
}
```

You can unhide base functions using:
```cpp
using Base::func;
```

---

## 9. Error Handling in OOP (Exception Handling)

### How is error handling integrated into OOP?

- Exceptions are objects.
- Code raising an error **throws** an exception object.
- Handlers **catch** exceptions, allowing the program to recover gracefully or report the error.
- Promotes **separation of normal logic and error handling**.

### Example

```cpp
#include <iostream>
#include <stdexcept>

class Calculator {
public:
    double divide(double a, double b) {
        if (b == 0)
            throw std::runtime_error("Division by zero error");
        return a / b;
    }
};

int main() {
    Calculator calc;
    
    try {
        std::cout << calc.divide(10, 2) << "\n";
        std::cout << calc.divide(5, 0) << "\n";  // Exception thrown here
    } catch(const std::exception& e) {
        std::cerr << "Caught exception: " << e.what() << "\n";
    }
    return 0;
}
```

---

# Final Thoughts

- **OOP helps organize software** according to real-world concepts using classes and objects.
- Concepts like **inheritance** and **polymorphism** facilitate code reuse and flexible design.
- **Operator overloading** and **function overloading** improve code readability.
- **Virtual functions and dynamic binding** allow runtime decisions, enabling true polymorphism.
- Proper understanding of **object copying, pointers, access specifiers, and exception handling** is crucial in writing robust OOP code.

---

# MODULE 6

## Detailed Explanation of Generic Programming and Templates in C++

Generic programming is a programming paradigm that enables writing code that works with any data type. Instead of writing multiple versions of the same code for different data types, **generic programming** uses templates in C++ to write flexible and reusable code components.

---

## 1. Introduction to Templates

A **template** is a blueprint or formula for creating a generic class or function. The compiler generates the actual class or function for the specific data type when you instantiate the template.

Templates are extensively used in the C++ Standard Template Library (STL) to provide generic containers and algorithms.

---

## 2. Function Templates

### What is a Function Template?

A **function template** defines a pattern for a function where the data types of parameters or return value are generic placeholders.

### Syntax:
```cpp
template <typename T>  
T functionName(T a, T b) {
    // function body using T
}
```

### Example: A function that returns the maximum of two values

```cpp
#include <iostream>
using namespace std;

template <typename T>
T maxOf(T a, T b) {
    return (a > b) ? a : b;
}

int main() {
    cout << maxOf<int>(3, 7) << endl;       // Output: 7
    cout << maxOf<double>(3.5, 2.5) << endl; // Output: 3.5
    cout << maxOf<char>('g', 'e') << endl; // Output: g

    // Type can often be deduced, so these calls are also valid:
    cout << maxOf(10, 100) << endl;      
    cout << maxOf(3.14, 2.72) << endl;

    return 0;
}
```

- Here `T` is a template parameter representing any data type.
- The compiler generates a function version for each data type used.

---

## 3. Class Templates

### What is a Class Template?

A **class template** allows you to define an entire class with one or more generic data types. This makes classes adaptable to multiple types without rewriting code.

### Syntax:
```cpp
template <typename T>
class ClassName {
    T data;
public:
    ClassName(T d);
    void display();
};
```

### Example: A simple generic `Box` class

```cpp
#include <iostream>
using namespace std;

template <typename T>
class Box {
    T content;
public:
    Box(T c) : content(c) {}
    void showContent() {
        cout << "Content: " << content << endl;
    }
};

int main() {
    Box<int> intBox(123);
    intBox.showContent();  // Output: Content: 123

    Box<string> strBox("Hello Templates");
    strBox.showContent();  // Output: Content: Hello Templates

    return 0;
}
```

- The same class works for any data type, as specified when creating the object (`int`, `string`, etc.).
- Templates promote **code reuse** and **type safety**.

---

## 4. Template Specialization

### What is Template Specialization?

Sometimes, you want special behavior for a certain data type different from the generic template. Template specialization lets you define a specific implementation for particular types.

### Why is it useful?

You can optimize or customize code for particular types without affecting the general template.

### Types of Specialization:

- **Full Specialization:** Provide an entirely different implementation for a specific type.
- **Partial Specialization:** Specialize templates based on subset of parameters (only for class templates).

---

### 4.1 Full Specialization for a Class Template

Example: Specialized template for `char*` that prints the string differently

```cpp
#include <iostream>
using namespace std;

template <typename T>
class Printer {
public:
    void print(T data) {
        cout << "Generic print: " << data << endl;
    }
};

// Full specialization for char*
template <>
class Printer<char*> {
public:
    void print(char* data) {
        cout << "String print: " << data << endl;
    }
};

int main() {
    Printer<int> intPrinter;
    intPrinter.print(100);   // Output: Generic print: 100

    Printer<char*> strPrinter;
    char text[] = "Hello, world!";
    strPrinter.print(text);  // Output: String print: Hello, world!

    return 0;
}
```

- The specialized `Printer<char*>` class has a custom `print` method.

---

### 4.2 Full Specialization for Function Template

Example: Specialized version of `maxOf` function for `const char*` for string comparison

```cpp
#include <iostream>
#include <cstring>
using namespace std;

template <typename T>
T maxOf(T a, T b) {
    return (a > b) ? a : b;
}

// Specialization for const char*
template <>
const char* maxOf<const char*>(const char* a, const char* b) {
    return (strcmp(a, b) > 0) ? a : b;
}

int main() {
    cout << maxOf(10, 20) << endl;          // Output: 20
    cout << maxOf(3.5, 2.5) << endl;        // Output: 3.5

    const char* str1 = "apple";
    const char* str2 = "banana";
    cout << maxOf(str1, str2) << endl;      // Output: banana (lexicographically larger)

    return 0;
}
```

---

### 4.3 Partial Specialization (Class Templates only)

Partial specialization applies when only some of the template parameters are specialized.

Example: Partial specialization of a pair class when both types are the same

```cpp
#include <iostream>
using namespace std;

template <typename T1, typename T2>
class Pair {
public:
    void display() {
        cout << "General Pair" << endl;
    }
};

// Partial specialization when both types are the same
template <typename T>
class Pair<T, T> {
public:
    void display() {
        cout << "Pair with same types" << endl;
    }
};

int main() {
    Pair<int, double> p1;
    p1.display();        // Output: General Pair

    Pair<int, int> p2;
    p2.display();        // Output: Pair with same types

    return 0;
}
```

---

## Summary Table

| Concept               | Description                                              | Example Highlight                                  |
|-----------------------|----------------------------------------------------------|---------------------------------------------------|
| Template              | Blueprint for generic code                              | `template <typename T>`                            |
| Function Template     | Generic function definition                             | `T maxOf(T a, T b)`                               |
| Class Template        | Generic class definition                                | `template <typename T> class Box { ... }`         |
| Full Specialization   | Specific implementation for a data type                | Specialized `Printer<char*>`                        |
| Partial Specialization| Specialization for part of the class template parameters| `template <typename T> Pair<T, T>`                 |

---

## Why Use Generic Programming?

- **Type safety:** Errors caught at compile time.
- **Code reuse:** Write once, use for any type.
- **Maintainability:** Avoids redundant code.
- **Performance:** No overhead compared to hand-written specific code, as code is generated during compilation.

---

# MODULE 7

## Detailed Explanation of Input and Output (I/O) in Programming

Input and Output (I/O) form the backbone of any practical program: they allow it to receive data from the outside world (input) and deliver results or information to the user or other systems (output). Understanding how I/O works is crucial for interacting with consoles, files, and other devices.

---

## 1. What Are Streams?

### Concept of Streams

A **stream** is an abstraction representing a flow of data. Think of it as a pipeline through which data travels between a program and some device or file.

- **Input stream:** Used to read data into the program.
- **Output stream:** Used to send data out of the program.

### Why Use Streams?

Streams hide the complexity of hardware devices or files so you can operate on data uniformly.

---

## 2. Streams in Programming

### Example from C++

C++ uses streams extensively through the standard library:

- `std::cin` — Standard input stream (usually keyboard input).
- `std::cout` — Standard output stream (usually displays on the screen).
- `std::cerr` — Standard error output stream (for error messages).

### Basic Input and Output Using Streams:

```cpp
#include <iostream>
using namespace std;

int main() {
    int age;

    cout << "Enter your age: "; // Output stream to prompt user
    cin >> age;                  // Input stream to receive integer

    cout << "You are " << age << " years old." << endl; // Output result

    return 0;
}
```

**Explanation:**

- `cout` inserts (outputs) data to the console.
- `cin` extracts (reads) data from the console.
- Both are objects of types derived from `iostream`, that handle streaming.

---

## 3. Files and File Streams

### What is a File?

A **file** is a stored collection of data on a disk or other storage device. Programs can read from or write to files, enabling data persistence beyond program execution.

### File Streams

Like console I/O streams, files use streams:

- **ifstream (input file stream):** To read data from files.
- **ofstream (output file stream):** To write data to files.
- **fstream:** Supports both reading and writing.

These classes are defined in the `<fstream>` header.

---

### Opening and Using Files Example

```cpp
#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main() {
    // Declare an output file stream and open file "output.txt"
    ofstream outFile("output.txt");

    if (!outFile) {
        cerr << "Error opening file for writing\n";
        return 1;
    }

    outFile << "Hello, file!\n";   // Write to the file

    outFile.close();               // Always close the file after use

    // Declare an input file stream and open file "output.txt"
    ifstream inFile("output.txt");

    if (!inFile) {
        cerr << "Error opening file for reading\n";
        return 1;
    }

    string line;
    while (getline(inFile, line)) {   // Read the file line by line
        cout << line << endl;         // Output the content to console
    }

    inFile.close();

    return 0;
}
```

---

### Explanation:

- `ofstream outFile("filename")` creates and opens the file for writing.
- You can use the `<<` operator to write to the file like you do with `cout`.
- `ifstream inFile("filename")` opens the file for reading.
- `getline(inFile, line)` reads a full line from the file into `line`.
- Remember to **close** file streams explicitly.

---

## 4. Library Functions for I/O

Many programming languages or libraries provide functions to simplify file and console I/O.

### C Standard I/O (stdio.h)
In C (and available in C++):

- `printf` and `scanf` for formatted console I/O.
- `fopen`, `fclose`, `fprintf`, `fscanf`, `fgets`, `fputs` for file operations.

Example in C using `printf` and `scanf`:

```c
#include <stdio.h>

int main() {
    int age;
    printf("Enter your age: ");
    scanf("%d", &age);
    printf("You are %d years old.\n", age);
    return 0;
}
```

---

## 5. Formatted Output

Formatted output means customizing how data is presented: controlling precision, width, alignment, and more.

### 5.1 Formatted Output in C++

C++ provides manipulators to format output.

Some commonly used manipulators from `<iomanip>`:

- `setw(n)` — Sets the width of the next output field.
- `setprecision(n)` — Sets decimal precision for floating-point numbers.
- `fixed` — Use fixed-point notation.
- `left` and `right` — Set alignment.

### Example of formatted output:

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    double pi = 3.14159265;

    cout << "Default precision: " << pi << endl;
    cout << fixed << setprecision(2);  // Fix to 2 decimal places
    cout << "Fixed precision: " << pi << endl;

    cout << setw(10) << 123 << endl;         // Width 10, right aligned by default
    cout << left << setw(10) << 123 << endl; // Width 10, left aligned

    return 0;
}
```

**Output:**

```
Default precision: 3.14159
Fixed precision: 3.14
       123
123       
```

---

## 6. Summary of Key Concepts

| Concept           | Description                                                                         | Example/Usage                           |
|-------------------|-------------------------------------------------------------------------------------|---------------------------------------|
| **Stream**         | Abstract flow of data for input or output                                          | `cin`, `cout` in C++                   |
| **Input Stream**   | Stream used to extract/read data into program                                      | `cin >> variable`                      |
| **Output Stream**  | Stream used to insert/write data outside the program                               | `cout << "Hello"`                      |
| **File Stream**    | Stream connected to a file on disk for reading (`ifstream`) or writing (`ofstream`) | Opening with `ifstream file("data.txt")` |
| **Library Functions** | Functions available for formatted and file I/O (C/C++ standards)                  | `printf`, `scanf`, `getline`, `open` etc. |
| **Formatted Output** | Controls how output data appears (alignment, precision, width)                    | `setw`, `setprecision`, `fixed`       |

---

## 7. Important Best Practices

- Always **check if streams/files are successfully opened** before reading or writing.
- Always **close files** after operations to save changes and free resources.
- Use **formatted output** to improve readability of program data.
- Understand difference between **text mode** and **binary mode** when opening files (mostly important for non-text files).
- For beginners, start with simple console streams (`cin`, `cout`), then move to file I/O.

---

## 8. Real-World Scenario Example

Imagine you want a program that:

- Prompts a user to enter student names and grades.
- Saves them to a text file.
- Later reads and displays the saved data nicely formatted.

This involves console input/output (`cin`, `cout`), file streams (`ifstream`, `ofstream`), and formatted output (to align columns).

---

# MODULE 8
## Detailed Explanation of Object-Oriented Design and Modeling with UML and C++ Implementation

Object-Oriented Design (OOD) and Modeling provide structured ways to capture, analyze, and design software systems before actual coding. UML (Unified Modeling Language) is the standard for visualizing and documenting object-oriented systems. Below is a detailed explanation suitable for an intermediate learner.

---

## 1. UML Concepts: Overview

**UML** is a graphical language that helps model the structure and behavior of software systems.

- **Structure diagrams** describe static aspects: classes, objects, components, etc.
- **Behavior diagrams** describe dynamic behavior: interactions, activities, state changes.

Key UML diagrams we will focus on:

- **Use Case Diagram:** Captures requirements.
- **Class Diagram:** Describes system structure (classes and relationships).
- **Activity Diagram:** Models workflows and activities.
- **Sequence Diagram:** Models object interactions over time.

---

## 2. Capturing Requirements Using Use Cases

### What is a Use Case?

A **Use Case** describes a way an actor (user or system) interacts with the system to achieve a goal. It captures functional requirements simply and clearly.

### Use Case Diagram

- **Actors:** External entities interacting with the system.
- **Use Cases:** Functions/services provided by the system.
- **Relationships:** Associating actors and use cases.

### Example: ATM System Use Case Diagram

- **Actors:** Customer, Bank Server.
- **Use Cases:** Withdraw Cash, Check Balance, Deposit Funds.

**Purpose:** Capture *what* the system should do, without yet describing *how*.

---

## 3. Designing with Class Diagrams

### What is a Class Diagram?

It shows:

- **Classes**: Blueprint of objects with attributes (data) and methods (functions).
- **Relationships:**
  - **Association:** A "uses" or "knows about" link.
  - **Aggregation:** Whole-part "has a" relationship.
  - **Composition:** Strong ownership (part cannot exist without whole).
  - **Inheritance:** "Is-a" or generalization relationship.

### Basic Notation:

```
-------------------------
|       ClassName       |
-------------------------
| - attributeName: Type |
| - ...                 |
-------------------------
| + methodName(): Type  |
| + ...                 |
-------------------------
```

- `-` private, `+` public.

### Example: ATM System Classes

- Class: `Account`
  - Attributes: accountNumber, balance
  - Methods: deposit(), withdraw(), getBalance()
- Class: `Customer`
  - Attributes: customerID, name
  - Methods: authenticate()

Relationships:

- Customer **has** Account(s) (Aggregation).
- Account **performs** withdraw, deposit, etc.

---

## 4. Activity Diagrams: Modeling Workflows

Activity Diagrams show the flow of activities or control flow in a system or process.

- Uses **activities (rounded rectangles)**, **decisions (diamonds)**, **start/end nodes**, and arrows to indicate the flow.
- Good for describing complex logic, conditions, and parallel processes.

### Example: Withdraw Cash Activity

- Start
- Authenticate customer
- Select account
- Enter amount
- Check funds
- Dispense cash
- End

---

## 5. Sequence Diagram: Interaction Over Time

Shows how objects interact via messages in a time sequence.

- Objects placed horizontally at the top.
- Vertical dashed lines represent lifespan during interaction.
- Arrows show messages/calls sent between objects.

### Example: Withdraw Cash Sequence

1. Customer calls `withdraw()` on ATM.
2. ATM calls `authenticate()` on Customer.
3. ATM calls `deductAmount()` on Account.
4. ATM dispenses cash.

---

## 6. Translating UML Designs into C++ Code

Let's demonstrate how these diagrams translate to C++ classes and methods.

---

### 6.1 Class Diagram → C++ Classes

Consider these simplified classes from the ATM example.

```cpp
#include <iostream>
#include <string>
using namespace std;

class Account {
private:
    string accountNumber;
    double balance;
public:
    Account(string accNum, double bal) : accountNumber(accNum), balance(bal) {}
    
    void deposit(double amount) {
        balance += amount;
    }
    
    bool withdraw(double amount) {
        if (amount > balance) {
            cout << "Insufficient funds\n";
            return false;
        }
        balance -= amount;
        return true;
    }
    
    double getBalance() const {
        return balance;
    }
};

class Customer {
private:
    string customerID;
    string pin;
public:
    Customer(string id, string p) : customerID(id), pin(p) {}

    bool authenticate(string enteredPin) {
        return enteredPin == pin;
    }
};
```

---

### 6.2 Activity and Sequence Diagrams → Program Flow

Suppose the ATM interacts with customer and account objects following the flow described.

```cpp
int main() {
    Customer customer("cust123", "4321");
    Account account("acc456", 500.0);

    string enteredPin;
    cout << "Enter PIN: ";
    cin >> enteredPin;

    if (!customer.authenticate(enteredPin)) {
        cout << "Authentication failed. Exiting.\n";
        return 0;
    }
    
    double amount;
    cout << "Enter amount to withdraw: ";
    cin >> amount;

    if (account.withdraw(amount)) {
        cout << "Please collect your cash.\n";
        cout << "Remaining balance: $" << account.getBalance() << endl;
    } else {
        cout << "Transaction failed.\n";
    }

    return 0;
}
```

- The control flow corresponds to the **activity diagram**.
- The method calls correspond to the **sequence diagram** messages.

---

## 7. Summary of Steps from Requirements to Code

| Phase                  | Diagram / Artifact                   | Purpose                                   | Example                             |
|------------------------|------------------------------------|-------------------------------------------|-----------------------------------|
| **Requirement Capturing** | Use Case Diagram                    | Identify actors and system use cases       | Customer withdraws cash             |
| **Structural Design**   | Class Diagram                      | Define key classes and relationships       | Customer, Account classes            |
| **Behavior Modeling**   | Activity Diagram                   | Represent workflows and logic               | Withdraw cash process               |
| **Interaction Modeling**| Sequence Diagram                   | Model object interactions over time        | Customer calls withdraw on ATM     |
| **Implementation**     | C++ Classes and Methods            | Translate design into programming constructs| Classes with data + member functions|

---

## 8. Additional Tips

- Always validate requirements with stakeholders using **Use Cases**.
- Use **Class Diagrams** to carefully design object relationships before coding.
- Model complex business logic clearly with **Activity Diagrams**.
- Use **Sequence Diagrams** to understand and verify object collaboration and message sequence.
- Begin coding by implementing classes as per the class diagram, then implement methods and main workflows respecting activity and sequence diagrams.
- Use **access specifiers** (`private`, `public`) to encapsulate class internals.
- Refine design iteratively by revisiting UML diagrams as requirements evolve.

---
