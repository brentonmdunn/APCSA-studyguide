# AP CS A 

An overview of the [Advanced Placement Computer Science A](https://apstudents.collegeboard.org/courses/ap-computer-science-a) course by the [College Board](https://www.collegeboard.org/) based on the [Fall 2020 Course Exam Description](https://apcentral.collegeboard.org/pdf/ap-computer-science-a-course-and-exam-description.pdf?course=ap-computer-science-a) in conjunction with [Runestone Academy CSAwesome](https://csawesome.runestone.academy/runestone/books/published/csawesome/index.html).

[TOC]

# Primitive Types

## 1.1 Why Programming? Why Java?

`System.out.println()` prints text then moves the cursor to a new line <u>**after**</u> the information has been displayed.

`System.out.print()` prints text but does not move the cursor to a new line.

```java
// This is a single line commment

/*
This
is 
a
block/multiline
comment.
*/
```



## 1.2 Variables and Data Types

Primitive types: `int`, `double`, and `boolean`

A variable must be declared and then initialized. Example: `int x = 2`

If variable is declared with `final`, its value cannot be changed once it is initialized. Example: `final String str = "str";`

### Naming Variables

- Cannot use any reserved keywords
- Cannot start with a number
- Cannot have spaces
- Are case sensitive 

## 1.3 Expressions and Assignment Statements

`=` is the assignment operator.

Literal: source code representation of a fixed value

Arithmetic expressions: `+`, `-`, `*`, `/`, and `%`

If operation uses two `int` values, then will evaluate to an `int`. If operation has at least 1 `double` value, it will evaluate to a `double`.

Dividing by 0 will result in an `ArithmeticException` to occur.

## 1.4 Compound Assignment Operators

Compound operators: `+=`, `−=`, `*=`, `/=`, and `%=`

Increment operator: ++

Decrement operator: --

## 1.5 Casting and Ranges of Variables

Casting is used to create a temporary value converted to a different data type. 

Casting a `double` to an `int` causes the digits after the decimal to be taken off. 

The smallest possible `int` value is `Integer.MIN_VALUE`.



# Using Objects

## 2.1 Objects: Instances of Classes

An object is an instance of a class. A class is a formal implementation of the attributes (properties) and behaviors (actions) of an object. Behaviors are written as methods.

## 2.2 Creating and Storing Objects (Instantiation)

A signature consists of the constructor name and the parameter list. Example: `public MyClass(int a, boolean b, String c)`

The list of parameters are known as formal parameters. The values that are passed in the parameters are known as actual parameters. 

Objects are created using the `new` keyword followed by a call to one of the constructors (`new Class()`). Constructors have the same name as the class. They are use to initialize the attributes in a newly created object.

The `null` keyword is used to indicate that a reference is not associated with any object.

```java
class MyClass {
    
    private int my_A;
    private int my_B;
    
    public MyClass(/* formal parameters: */ int a, int b) {
        my_A = a;
        my_B = b;
    }
}

class Main {
    public static void main(String[] args) {
        MyClass myclass1 = new MyClass(/* actual parameters: */ 14, 2);
        MyClass myclass2 = null;
    }
}
```

## 2.3 Calling a Void Method

Void methods are methods that do not have a return type. They are declared as type `void` and must be called on an object of the class that the method is defined in. Example: 

```java
public void print_A() {
    System.out.println("A");
    // no return statement needed
}
```

An object's behavior is defined by its methods. Abstraction allows a programmer to use a method even if the do not know how the method is written. They just need to know the method signature. If a method and/or constructor is called, the code within the method and/or constructor is executed. After completed, the program goes back to where it left off before the method/constructor call.

Non-static methods are called through objects of the class. A dot operator is used to call them. Using a `null` reference to call a method or access an instance variable causes a `NullPointerException` to be thrown

## 2.4 Calling a Void Method with Parameters

A method signature consists of a method name and the ordered list of parameter types. The values in the parameter list need to correspond to the order and type in the method signature. Methods are said to be overloaded when there are multiple methods with the same name but different signatures. Example:

```java
public static void myMethod() {
    System.out.println("This is the method with no parameters!");
}

public static void myMethod(int a) {
    System.out.println("This is an overloaded method! The parameter is: " + a);
}
```

### Set Methods

Set methods are methods used to set certain instance variables. Example:

```java
public void setLenth(int newLength) {
	length = newLength;
}
```

## 2.5 Calling a Non-void Method

Non-void methods return a value that is the same type as the return type in the signature. The return value must be stored in a variable or used as part of an expression. Example:

```java
public static int myIntMethod() {
    return 1 + 2;
}
```

### Get Methods

Get methods are methods used to retrieve certain instance variables. Example:

```java
public int getLength() {
    return length;
}
```

## 2.6 String Objects: Concatenation, Literals, and More

`String` objects can be created using string literals or by calling the `String` class constructor. They hold sequences of characters. Example:

```java
String strLiteral = "my string";
String strConstructor = new String("my string");
```

`String` objects are immutable--the `String` methods do not change the `String` object. Strings can be concatenated using `+` or `+=`, resulting in a new `String` object. Primitive values can be concatenated with `String` objects. The primitive is implicitly converted to a `String` object. 

Escape sequences start with a `\` and give the ability to use reserved characters in a `String`. Example: `\"`, `\\`, and `\n`.

## 2.7 String Methods

A `String` object has index values from 0 to `length-1`. Attempting to access indices outside of that range will result in an `StringIndexOutOfBoundsException`. A `String` object can be concatenated with an object reference, which implicitly calls the referenced object's `toString` method.

### String Methods and Constructors

`String(String str)`: Constructs a new `String` object that represents the same sequence of characters as `str`

`int length()`: returns the number of characters in a `String` object

`String substring(int from, int to)`: returns the substring beginning at index `from` and ending at index `to-1`

`String substring(int from)`: returns `substring(from, length())`

`int indexOf(String str)`: returns the index of the first occurrence of `str`; returns `-1` if not found

`boolean equals(String other)`: returns `true` if `this` is equal to `other`; returns `false` otherwise

`int compareTo(String other)`: returns a value if `< 0` if `this` is alphabetically ordered before `other`; returns 0 if `this` is equal to `other`; returns a value `> 0` if `this` is alphabetically ordered after `other`

Can isolate a single element by calling `substring(index, index + 1)`

Common mistake: do not use `==` to evaluate two `String` objects

## 2.8 Wrapper Classes: Integer and Double

Sometimes you may need to wrap a value if method is expecting an object. 

```java
Integer i = new Integer(2);
Double d = new double (3.5);
```

### Integer Methods and Constructors

`Integer(int value)`: constructs a new `Integer` object that represents the specified `int` value

`Integer.MIN_VALUE`: the minimum value represented by an `Int` or `Integer`

`Integer.MAX_VALUE`: the maximum value represented by an `Int` or `Integer`

`int intValue()`: returns a value of this `Integer` as an `int`

#### Underflow and Overflow

Underflow: Java will return the maximum integer value if you try to do `Integer.MIN_VALUE - 1`

Overflow: Java will return the minimum integer value if you try to do `Integer.MAX_VALUE - 1`

### Double Methods and Constructors

`Double(double value)`: constructs a new `Double` object that represents the specified `double` value

`double doubleValue()`: returns the vale of this `Double` as a `double`

### Autoboxing

Autoboxing is the automatic conversion that the Java compiler makes between primitive types and their corresponding object wrapper classes. This includes converting an `int` to and `Integer` and a `double` to  a `Double`.

The Java compiler applies autoboxing when a primitive value is:

- Passed as a parameter to a method that expects an object of the corresponding wrapper class
- Assigned to a variable of the corresponding wrapper class

```java
Integer i = 2;
Double d = 3.5;
```

### Unboxing 

Unboxing is a the automatic conversion that the Java compiler makes from the wrapper class to the primitive type. This includes converting an `Integer` to an `Int` and a `Double` to a `double`.

The Java compiler applies unboxing when a primitive value is:

- Passed as a parameter to a method that expects an value of the corresponding primitive type
- Assigned to a variable of the corresponding primitive type 

```java
Integer i = 2;		// autoboxing - wrap 2
int number = i;		// unboxing - back to primitve type
```

## 2.9 Using the Math Class

Static methods are called using the dot operator along with the class name unless they are defined by the enclosing class. The `Math` contains only static methods.

### Static Math Methods

`int abs(int x)`: returns the absolute value of an `int` value

`double abs(double x)`: returns the absolute value of the `double` value

`double pow(double base, double exponent)`: returns the value of the first parameter raised to the power of the second parameter

`double sqrt(double x)`: returns the positive square root of a `double` value

`double random()`: returns a double value greater than or equal to 0.0 and less than 1.0

### Using the random() Method

Casting `Math.random()` to an `int` (`(int) Math.random()`) will truncate any numbers after the decimal.

`(int) (Math.random() * range) + min)` where `range` is `maxNum - minNum + 1`

Random integer in the range 0 - 9 inclusive: `(int) (Math.random() * 10)`

Random integer in the range 10-15 inclusive: `(int) (Math.random() * 6) + 10`



# Boolean Expressions and If Statements

## 3.1 Boolean Expressions

Primitive values and reference values can be compared using relational operators (`==`, `!=`)

Arithmetic expressions values can be compared using relational operators (`<`, `>`, `<=`, `>=`)

An expression involving relational operators evaluates to a Boolean value.

### Using Modulo

Test if a number is positive: `(num > 0)`

Test if a number is negative: `(num  <  0)`

Test if a number is even: `(num % 2 == 0)`

Test if a number is odd: `(num % 2 != 0)` or `(num % 2 == 1)`

Test if a number is a multiple of `x`: `(num % x == 0)`

## 3.2 If Statements and Control Flow

Conditional statements interrupt the sequential execution of statements.

`if` statements affect the flow of control by executing different statements based on the value of a Boolean expression. The body of an `if` statement executes if the Boolean condition is `true`.

A one-way selection is when there is only one `if` statement. Example:

```java
if (x == 2) {
    System.out.println("x is equal to 2!");
}
```

## 3.3 If-Else Statements

A two-way selection is when there are two sets of statements--one to be executed when the Boolean condition is `true`, and another set of for when the Boolean condition is `false`. The "if" part of the statement is executed if the statement is  true and the "else" is executed if the Boolean condition is false. Example:

```java
if (x == 0) {
    System.out.println("x is equal to 0!")
} else {
    System.out.println("x is not equal to 0!")
}
```

## 3.4 Else If Statements

A multi-selection is when there are a series of conditions with different statements for each conditions. They are performed using `if-else-if` statements such that exactly one section of code is executed based on the first condition that evaluates to true. Example: 

```java
if (x == 0) {
    System.out.println("x is equal to 0!")
} else if (x == 1) {
	System.out.println("x is equal to 1!")
} else {
    System.out.println("x is not equal to 0 or 1!")
}
```

## 3.5 Compound Boolean Expressions

Nested `if` statements consist of `if` statements within `if` statements.

Logical operators `!` (note), `&&` (and), and `||` (or) are used with Boolean values and evaluate to a Boolean value.

|  `P`  |  `Q`  | `P && Q` |
| :---: | :---: | :------: |
| true  | true  |   true   |
| false | true  |  false   |
| true  | false |  false   |
| false | false |  false   |



|  `P`  |  `Q`  | `P || Q` |
| :---: | :---: | :------: |
| true  | true  |   true   |
| false | true  |   true   |
| true  | false |   true   |
| false | false |  false   |

When the result of a logical expression can be determined by evaluating only the first Boolean operand, the second is not evaluated (known as short circuiting). If two Boolean values are combined with `&&` and the first Boolean is `false`, then the second Boolean will not be checked. If two Boolean values are combined with `||` and the first Boolean value is `true`, then the second Boolean value will not be checked. Example: `if (x == 2 || x < 5)` If `x == 2` is `true`, then `x < 5` is never evaluated because the condition is already true.

## 3.6 Equivalent Boolean Expressions

De Morgan's Laws can be applied to Boolean expressions.

- Move the `NOT` inside --> `AND` becomes `OR` and `OR` becomes `AND`
  - `!(a && b)` is equivalent to `!a || !b`
  - `!(a || b)` is equivalent to `!a && !b`

- To move the `NOT`, flip the sign
  - `!(c == d)` is equivalent to `(c != d)`
  - `!(c != d)` is equivalent to `(c == d)`
  - `!( c < d)` is equivalent to `(c >= d)`
  - `!(c > d)` is equivalent to `(c <= d)`
  - `!(c <= d)` is equivalent to `(c > d)`
  - `!(c >= d)` is equivalent to `(c < d)`

Example: `!(x < 3 && y > 2)` --> `!(x < 3) || !(y > 2)` --> `x >= 3 || y <= 2`

Truth tables can be used to prove Boolean identities. Equivalent Boolean expressions will evaluate to the same value in all cases.

|  `a`  |  `b`  | `!(a && b)` | `!a || !b` |
| :---: | :---: | :---------: | :--------: |
| true  | true  |    false    |   false    |
| false | true  |    true     |    true    |
| true  | false |    true     |    true    |
| false | false |    true     |    true    |

## 3.7 Comparing Objects

Two object references are considered aliases when they both reference the same object. Object reference values can be compared using `==` and `!=` to identify aliases. 

```java
MyClass myclass1 = new MyClass();
MyClass myclass2 = new MyClass();
        
System.out.println(myclass1 == myclass2);	// false
        
MyClass myclass3 = myclass1
        
System.out.println(myclass1 == myclass3);	// true
```

A reference value can be compared with `null` using `==` or `!=` to determine  if the reference actually references an object. Often classes have their own `equals` method, which can be sued to determine whether two objects of the class are equivalent. 



# Iteration

## 4.1 `WHILE` Loops

Iteration statement change the flow of control by repeating a set of statements zero or more times until a condition is met. In loops, the Boolean expression is evaluated before each iteration of the loop body, including the first. When  he expression evaluates to `true`, the loop body is executed. This continues until the expression evaluates to `false`, whereupon the iteration ceases. 

A `while` loop executes the body of the loop as long as (or while) a Boolean condition is true. When the condition is false, we exit the loop and continue with the statements that are after the body of the `while` loop.  

A loop is an infinity loop when the Boolean expression always evaluates to `true`. If the Boolean expression evaluates to `false` initially, the loop body is not executed at all. 

Executing a return statement inside an iteration statement will halt the loop and exit the method or constructor.

Standard algorithms to know: 

- Identify if an integer is or is not evenly divisible by another integer
- Identify the individual digits in an integer
- Determine the frequency with which a specific criterion is met
- Determine a minimum or maximum value
- Compute a sum, average, or mode

Example:

```java
while (Boolean b) f{
    System.out.println("Executed!");
}
```

## 4.2 `FOR` Loops

There are three parts in a `for` loop header: the initialization, the Boolean expression, and the increment. Each is separated by a semicolon (`;`). The increment statement can also be a decrement statement. In a `for` loop, the initialization is only executed once before the first Boolean expression evaluation. The variable being initialized is referred to as a loop control variable. In each iteration of a `for` loop, the increment statement is executed after the entire loop body is executed and before the boolean expression is evaluated again. A `for` loop can be written into an equivalent `while` loop and vice versa. 

"Off by one" errors occur when the iteration statement loops one time too many or one time too few.

```java
for (int i=0; i < 10; i++) {
    System.out.println("Executed!");
}
```

## 4.3 Developing Algorithms Using Strings

Standard algorithms that utilize `String` transversals to:

- Find if one or more substrings has a particular property
- Determine the number of substrings that meet a specific criteria
- Create a new string with the characters reversed

The first character in a Java String is at index 0 and the last character is at `length() - 1`.

### While Find and Replace Loop

A while loop can be used with the `String` `indexOf` method to find certain characters in a string and process them, usually sing the substring method.

```java
String s = "example";
int i = 0;
while (s.indexOf("a") >= 0) {
    i = s.indexOf("a");
    String ithLetter = s.substring(i, i+1)
}
```

*<u>**MAY NEED TO CONTINUE**</u>*

### For Loops: Reverse String

```java
String s = "example";
String reversed = "";
String temp = "";
for (int i=0; i < s.length(); i++) {
    String ithLetter = s.substring(i, i+1);
    
}
```

<u>***MAY NEED TO CONTINUE***</u>

## 4.4 Nested Iteration

Nested iteration statement are iteration statements that appear in the body of another iteration statement. When a loop is nested inside another loop, the inner loop must complete all its iterations before the outer loop can continue. Example:

```java
for (int i=0; i < 5; i++) {
    for (int j=0; j < 5; j++) {
        System.out.println("This will print 25 times!");
    }
}
```

## 4.5 Informal Code Analysis

A statement execution count indicates the number of times a statement is executed by the program. 



# Writing Classes

## 5.1 Anatomy of a Class

The keywords `public` and `private` affect the access of classes, data, constructors, and methods. The keyword `private` restricts access to the declaring class. The keyword `public` allows access from classes outside of the declaring class. Classes are designed to be `public`. Access to attributes should be kept internal to the class, and therefore, should be designed as `private`. Constructors are designed as `public`. Access to behaviors can be internal or external to the class. Therefore, methods can be designed as either `public` or `private`.

Data encapsulation is a technique in which the implementation details of a class are kept hidden from a user. When designing a class, programmers make decisions about what data to make accessible and modifiable form an external class. Data can be either accessible or modifiable, or it can be both or neither. Instance variables are encapsulated by suing the `private` access modifier. The provided accessor or mutator methods in a class allow client code to use and modify data. 

Example:

```java
// class name declared public
public class MyClass {
    
    // instance variables declared private
    private int my_A;
    private int my_B;
    
    // constructor declared public
    public MyClass(int a, int b) {
        my_A = a;
        my_B = b;
    }
}
```

## 5.2 Constructors

An object's state refers to its attributes and their values at a given time and is defined by instance variables belonging to the object. This creates a "has-a" relationship between the object and its instance variables. Constructors are the same name as the class and are used to set the initial state of an object, which should include initial values for all instance variables. Constructor parameters are local variables to the constructor and provide data to initialize instance variables. 

When a mutable object is a constructor parameter, the instance variable should be initialized with a copy of the referenced object. In this way, the instance variable is not an an alias of the original object, and methods are prevented from modifying the state of the original object.

When no constructor is written, Java provides a no-argument constructor, and the instance variables are set to default values.

Default values:

- `int` = `0`
- `double` = `0.0`
- `String` (and other objects) = `null`

## 5.3 Documentation with Comments

Comments are ignored by the compiler and are not executed when the program is run

Three types of comments in Java:

- `//` Single line comments
- `/* `Block/multi-line comments `*/`
- `/**`Javadoc comments (used to create API documentation)  `*/`

### Javadoc Comment Tags

`@author` Author of program

`@since` Date released

`@version` Version of program

`@param` Parameter of a method

`@return` Return value for a method

### Preconditions and Postconditions 

A precondition is a condition that must be true just prior to the execution of a section of program code in order for the method to behave as expected. There is no expectation that the method will check to ensure preconditions are satisfied. An example of a precondition is that an object parameter is not `null`.

A postcondition is a condition that must always be true after the execution of a section of program code. Postconditions describe the outcome of the execution in terms of what is being returned or the state of an object. Programmers write method code to satisfy the post conditions when the preconditions are met.

## 5.4 Accessor Methods

An accessor method allows other objects to obtain the value of instance variables or static variables. A non-void method returns a single value. Its header includes the return type in place of the keyword `void`. In non-void methods, a return expression compatible with the return type is evaluated, and a copy of that value is returned. This is referred to as "return by value." When the return expression is a reference to an object, a copy of that reference is returned, not a copy of the object. The `return` keyword is used to return the flow of control to the point immediacy following where the method or constructor was called.

The `toString` method is an overridden method that is included in classes to provide a description of a specific object. It generally includes what values are stored in the instance data of the object. 

If `System.out.print` or `System.out.println` is passed an object, that object's `toString` method is called, and the returned string is printed.

```java
public class MyClass {
    
    private int my_A;
    
    public MyClass(int a) {
        my_A = a;
    }
    
    // accessor/get method
    public int getMy_A() {
        return my_A;
    }
}
```

## 5.5 Mutator Methods

A void method does not return a value. Its header contains the keyword `void` before the method name. A mutator (modifier) method is often a void method that changes the values of instance variables or static variables.

```java
public class MyClass {
    
    private int my_A;
    
    public MyClass(int a) {
        my_A = a;
    }
    
    // mutator/set method
    public void setMy_A(int aa) {
        my_A = a;
    }
}
```

## 5.6 Writing Methods

Methods can only access the private data and methods of a parameter that is a reference to an object when the parameter is the same type as the method's enclosing class. Non-void methods with parameters receive values through parameters, use those values, and return a computed value of the specified type. It is good programming practice not to modify mutable objects that are passed as parameters unless required in the specification. When an actual parameter is a primitive value, the formal parameter is initialed with a copy of that value. Changes to the formal parameter have no effect on the corresponding actual parameter.

When an actual parameter is a reference to an object, the formal parameter is initialized with a copy of that reference, not a copy of the object. If the reference is to a mutable object, the method or constructor can use this reference to alter the state of the object. Passing a reference parameter results in the formal parameter and the actual parameter being aliases. They both refer to the same object.

## 5.7 Static Variables and Methods

Static methods are associated with the class, not objects of the class. They do not need an object in order to execute. Static methods include the keyword `static` in the header before the method name. Example: `public static void myMethod()`

Static methods cannot access or change the values of instance variables. They can only access or change the values of instance variables. Static methods do not have a `this` reference and are unable to use the class's instance variables or call non-static methods.

Static variables belong to the class, with all objects of a class sharing a single static variable. They can be designated as either `public` or `private` and are designated with the `static` keyword before the variable type. Static variables are used with the class name and the dot operator, since they are associated with the class, not the objects of a class.

```java
public class MyClass {
    
    // static variable
    public static String myStaticVariable;
    
    // static method
    public static String myStaticMethod() {
        
    }
}

class Main {
    public static void main(String[] args) {
        System.out.println(MyClass.myStaticVariable);
        MyClass.myStaticMethod();
    }
}
```

## 5.8 Scope and Access

Local variables can be declared in the body of constructors and methods. These variables may only be used within the constructor or method and cannot be declared to be `public` or `private`. When there is a local variable with the same name as an instance variable, the variable name will refer to the local variable instead of the instance variable. Formal parameters and variables declared in a method or constructor can only be used within that method or constructor. Through method decomposition, a programmer breaks down a large problem into smaller subproblems by creating methods to solve each individual subproblem. 

3 levels of scope:

- Class Level Scope for instance variables inside a class
- Method Level Scope for local variables (including parameter values) inside a method
- Block Level Scope for loop variables and other local variables defined inside of blocks of code with { }

## 5.9 `THIS` Keyword

Within a non-static method or constructor, the keyword `this` is a reference to the current object--the object whose method or constructor is being called. The keyword `this` can be used to pass the current object as an actual parameter in a method call. Example: 

```java
class MyClass {
    
    private int my_A;
    private int my_B;
    
    public MyClass(int my_A, int my_B) {
        this.my_A = my_A;
        this.my_B = my_B;
    }
}
```

## 5.10 Ethical and Social Implications of Computing Systems

System reliability is limited. Programmers should make an effort to maximize system reliability. Legal issues and intellectual property concerns arise when creating programs. The creation of programs has impacts on society, economies, and culture. These impacts can be beneficial and/or harmful.



# Array

## 6.1 Array Creation and Access

The use of array objects allows multiple related items to be represented using a single variable. The size of an array is established at the time of creation and <u>cannot be changed</u>. Arrays can store either primitive data or object reference data. 

### Creating an Array

When an array is created using the keyword `new`, all of its elements are initialized with a specific value based on the type of elements: 

- Elements of type `int` are initialize to `0`
- Elements of type `double` are initialized to `0.0`
- Elements of type `boolean` are initialized to `false`
- Elements of a reference type are initialized to the reference value `null`. No objects are automatically created

```java
int arrLength = 10;
int[] arr = new int[arrLength];
```

Initializer lists can be used to create and initialize arrays. Example: `int[] arr = {1, 2, 3, 4};`

### Access and Modify Array Values

Square brackets (`[ ]`) are used to access and modify an element in a 1-D array using an index. 

Accessor method:  `arr[2]` accesses the 3rd index in the array

Modifier method: `arr[2] = 10` modifies the 3rd index to hold the value `10`

### Domain of the Array

The valid index values for an array are 0 through one less than the number of elements in the array (inclusive). Using an index value from outside of this range will result in an `ArrayIndexOutOfBoundsException` being thrown.

### Length 

The length of an array is a public read-only instance variable (NOT A METHOD). Therefore, it can be accessed using dot-notation. Example: `arrayName.length`

## 6.2 Traversing Arrays

Iteration statements can be used to access all the elements in an array. This is called traversing an array. Traversing an array with an indexed `for` loop or `while` loop requires elements to be accessed using their indices. Example: `for (int i = 0, i < arrayName.length i++)`

> Remember: the length is an instance variable, not a method!

### Looping From Back to Front

```java
for (int i = arrayName.length-1; i >= 0, i--) {
    System.out.printnln(arrayName[i]);
}
```

### Looping Through Part of an Array

```java
for (int i = 0; i < arrayName.length %% i < 5; i++) {
    System.out.println(arrayName[i]);
}
```

### “Off by One” Error

Since the indices  for an array start at 0 and end at the number of elements - 1, "off by one" errors are easy to make when traversing an array, resulting in an `ArrayIndexOutOfBoundsException` being thrown.

## 6.3 Enhanced `for` Loop for Arrays

An enhanced `for` loop header includes a variable, referred to as the enhanced `for` loop variable. For each iteration of the enhanced `for` loop, the enhanced `for` loop variable is assigned a copy of an element without using its index. <u>**Assigning a new variable to the enhanced `for` loop variable does not change the value stored in the array.**</u> Program code written using an enhanced `for` loop to traverse and access elements in an array can be rewritten using an indexed `for` loop or a `while` loop. 

```java
for (int e : arrayName) {
    System.out.println(e);
}
```

## 6.4 Developing Algorithms Using Arrays 

Standard algorithms that utilize array traversals to:

- Determine a minimum or maximum value
- Compute the sum, average, or mode
- Determine if at least one element has a particular property
- Determine if all elements have a particular property
- Access all consecutive parts of elements
- Determine the presence or absence of duplicated elements
- Determine the number of elements meeting specific criteria

Standard array algorithms that utilize transversals to:

- Shift or rotate elements left or right
- Reverse the order of the elements



# ArrayList

## 7.1 Introduction to ArrayList

An `ArrayList` object is mutable and contains object references. The `ArrayList` constructor `ArrayList()` constructs an empty list. Java allows the generic type `ArrayList<E>`, where the generic type `E` specifies the type of the elements. When `ArrayList<E>` is specified, these types of the reference parameters and return type when using the methods are type `E`. `ArrayList<E>` is preferred over `ArrayList` because it allows the compiler to find errors that would otherwise be found at run-time.

```java
// ArrayList<Type> name = new ArrayList<Type>();
ArrayList<String> strArrayList = new ArrayList<String>();
```

> ArrayLists take in object values. If you want to hold primitive values, you must use wrapper classes
>
> ```java
> ArrayList<Integer> numbers = new ArrayList<Integer>();
> ```

## 7.2 ArrayList Methods

The following are `ArrayList` methods:

`int size()`: returns the number of elements in the list

`boolean add (E obj)`: appends `obj` to end of list; returns `true`

> Remember the return statement.

`void add(int index, E obj)`: inserts ``obj` at position `index` (0 <= index <= size), moving elements at position `index` and higher to the right (adds 1 to their indices) and adds 1 to side 

`E get(int index)`: returns the element at the position `index` in the list

`E set(int index, E obj)`: replaces the element at position `index` with `obj`;  returns the element formerly at position `index`

> Remember the return statement.

`E remove(int index)`: removes element from position `index`, moving elements at position `index + 1` and higher to the left (subtracts 1 from their indices) and subtracts 1 from size; returns the element formerly at position `index`

> Remember the return statement.

## 7.3 Traversing ArrayLists

Iteration statements can be used to access all the elements in an `ArrayList`. This is called traversing the `ArrayList`. 

Deleting elements during a transversal of an `ArrayList` requires using special techniques to avoid skipping elements ELABORATE

Since the indices of an `ArrayList` start at 0 and end at the number of elements - 1, accessing an index value outside of this range will result in an `IndexOutOfBoundsException` being thrown.

Changing the size of an `ArrayList` while traversing it using an enhanced `for` loop can result in a `ConcurrentModificationException` being thrown. Therefore, when using an enhanced `for` loop to traverse an `ArrayList`, you should not add or remove elements.

## 7.4 Developing Algorithms Using ArrayLists

There are standard `ArrayList` algorithms that utilize traversals to: 

- Insert elements 
- Delete elements 
- Apply the same standard algorithms that are used with 1-D arrays

Some algorithms require multiple `String`, array, or `ArrayList` objects to be traversed simultaneously.

## 7.5 Searching

Sequential/linear search algorithms check each element in order until the desired value is found or all elements in the array or `ArrayList` have been checked. 

## 7.6 Sorting

Selection sort and insertion sort are iterative sorting algorithms that can be used to sort elements in an array or ``ArrayList``.

Informal run-time comparisons of program code segments can be made using statement execution counts.

## 7.7 Ethical Issues Around Data Collection

When using the computer, personal privacy is at risk. Programmers should attempt to safeguard personal privacy. 

Computer use and the creation of programs have an impact on personal security. These impacts can be beneficial and/or harmful.



# 2-D Array

## 8.1 2-D Array

2-D arrays are stored as arrays of arrays. Therefore, the way 1-D arrays are created and indexed is similar to 1-D array objects.

```java
int[][] myArray1 = new int[2][3];

// initializer list
int[][] myArray2 = {{2, 3, 4}, {6,  7, 8}};
```

> Will not be assessed on 2-D arrays that are not rectangular.

When assessing the element at `arr[first][second]`, the first index is used for rows, the second index is used for columns.

The initializer list used to create and initialize 2-D array consists of initializer lists that represent 1-D arrays. The square brackets `[row][col]` are used to access and modify an element in a 2-D array. “Row-major” order refers to an ordering of 2-D array elements where traversal occurs across each row, while “column-major order” traversal occurs down each column.

```java
// modify a value
myArray[0][1] = 2;
```

## 8.2 Traversing 2-D Arrays

Nested iteration statements are used to traverse and access all elements in a 2-D array. Since 2-D arrays are stored as arrays of arrays, the way 2-D arrays are traversed using `for` loops and enhanced `for` loops is similar to 1-D array objects. Nested iteration statements can be written to traverse the 2-D array in “row-major order” or “column-major order.” The outer loop of a nested enhanced `for` loop used to traverse a 2-D array traverses the rows. Therefore, the enhanced `for` loop variable must be the type of each row, which is a 1-D array. The inner loop traverses a single row. Therefore, the inner enhanced `for` loop variable must be the same type as the elements stored in the 1-D array.

```java
myArray.length		// returns the number of rows
myArray[0].length	// returns the number of columns

// standard for loop
for (int row = 0; row < myArray.lenth; row++) {
	for (int col = 0; col < myArray[0].length; col++) {
		System.out.println(myArray[row][col]);
	}
}

// enhanced for loop
for (int[] row : myArray) {
	for (int num : row) {
		System.out.println(num);
	}
}
```

When applying sequential/linear search algorithms to 2-D arrays, each row must be accessed then sequential/linear search algorithm applied to each row of a 2-D array. 

All standard 1-D array algorithms can be applied to 2-D array objects.



# Inheritance

## 9.1 Creating Superclasses and Subclasses

A class hierarchy can be developed by putting common attributes and behaviors of related classes into a single class called a superclass. Classes that extend a superclass (aka a parent class), called subclasses (or child classes), can draw upon the existing attributes and behaviors of the superclass without repeating these in the code.

The keyword `extends` is used to establish an inheritance relationship between a subclass and a superclass. A class can extend only one superclass.

```java
public class Vehicle {
    // some stuff
}

public class Car extends Vehicle {
    // vehicle stuff + car stuff 
}
```

### `instanceof` Operator

The `instanceof` operator will return true if the object is an instance of that class or is inherited from that class.

```java
public class Vehicle {
    // some stuff
}

public class Car extends Vehicle {
	// vehicle stuff + car stuff
}

public static void main(String[] args) {
	Car car = new Car();
	System.out.println(car instanceof Car);		// true
	System.out.println(car instanceof Vehicle); // true
}
```

### is-a vs. has-a Relationship

Extending a subclass from a superclass creates an “is-a” relationship from the subclass to the superclass.

A "has-a" relationship is created when a class is used as an instance variable in another class.

```java
public class Book {
	private Author author;				// creates a "has-a" relationship
	// some stuff
}

public class Author {
	// some stuff
}

public class InColdBlood extends Book { // creates an "is-a" relationship
	// some stuff
}
```

## 9.2 Writing Constructors for Subclasses

Constructors are not inherited. The superclass constructor can be called using the first line of a subclass constructor by using the keyword `super` and by passing appropriate parameters. The actual parameters passed in the call to the superclass provide values that the constructor can use to initialize the object’s instance variables. When a subclass’s constructor does not explicitly call a superclass’s constructor using `super`, Java inserts a call to the superclass’s no-argument constructor.

Regardless of whether the superclass constructor is called implicitly or explicitly, the process of calling superclass constructors continues until the `object` constructor is called. At this point, all of the constructors within the hierarchy execute beginning with the `object` constructor.

```java
public class Vehicle {
    private String color;
    
    public Vehicle() {
    	color = "";
    }
    
    public Vehicle(String color) {
    	this.color = color;
    }
}

public class Car extends Vehicle {
	private String carType;
	
	public Car() {
		super();
		carType = "";
	}
	
	public Car(String carType, String color) {
		super(color);
		this.carType = carType;
	}
}
```

## 9.3 Overriding Methods

Method overriding occurs when a public method in a subclass has the same method signature as the public method in the superclass. Any method that is called must be defined within its own class or its superclass. A subclass is usually designed to have modified (overridden) or additional methods or instance variables. A subclass will inherit all public methods from the superclass; these methods remain public in the subclass.

```java
public class Vehicle {
	// some constructor
	
	public void whatAreYou() {
		System.out.println("I am a vehicle!");
	}

}

public class Car extends Vehicle {
	// some constructor
	
	// overrides the whatAreYou() method in the Vehicle class
	public void whatAreYou() {
		System.out.println("I am a car!");
	}
}
```

## 9.4 `super` Keyword

The superclass method can be called in a subclass by using the keyword `super` with the method name and passing appropriate parameters.

```java
public class Vehicle {
	// some constructor
	
	public void whatAreYou() {
		System.out.println("I am a vehicle!");
	}

}

public class Car extends Vehicle {
	// some constructor
	
	public void whatAreYou() {
		System.out.println("I am a car!");
	}
	
	public void parentWhatAreYou() {
		System..out.println(super.whatAreYou());
	}
}

public static void main(String[] args) {
	Car car = new Car();
	car.whatAreYou;			// I am a car!
	car.parentWhatAreYou	// I am a vehicle!
}
```

## 9.5 Creating References Using Inheritance Hierarchies

When a class `S` “is-a” class `T`. `T` is referred to as a superclass, and `S` is referred to as a subclass. Assigning an object of type `S` to a reference of type `T` facilitates polymorphism. A reference of type `T` can be used to refer to an object of type `T` or `S`.

```java
public class Vehicle {
    // some stuff
}

public class Car extends Vehicle {
	// vehicle stuff + car stuff
}

public static void main(String[] args) {
	Vehicle obj1 = new Vehicle();		// works
	Car obj2 = new Car();				// works
	Vehicle obj3 = new Car();			// works
	Car obj4 = new Vehicle();			// does not work
}
```

Declaring references of type `T`, when using `S` is a subclass of `T`, is useful in the following declarations:

- Formal method parameters

- Arrays–`T[] varArrayList<T>var`

  ```java
  Vehicle[] vehicleArray = {new Vehicle(), new Car()};
  ArrayList<Vehicle> = new ArrayList<Vehicle>();
  ```

## 9.6 Polymorphism

Utilize the `object` class through inheritance. At compile-time, methods in or inherited by the declared type determine the correctness of a non-static method call. At run-time, the method in the actual object type is executed for a non-static method call.

> All the methods that the new object uses must be declared in the parent class.  This will be checked at compile-time. However, at run-time, the methods that will be executed will come from the child class.

```java
public class Vehicle {
    // some stuff
}

public class Car extends Vehicle {
	// vehicle stuff + car stuff
}

public static void main(String[] args) {
	/*compile time: */ Vehicle obj = new /*run time: */ Car();			
}
```



## 9.7 Object Superclass

The `object` class is the superclass of all other objects in Java. The following are `object` class methods:

- `boolean equals(Object other)`
- `String toString()`

The subclasses of `object` often override the `equals` and `toString` methods with class-specific implementations.



# Recursion

## 10.1 Recursion

A recursive method is a method that calls itself. It contains at least one base case, which halts the recursion, and at least one recursive call. 

```java
public static int mystery2(int x)
{
   if (x == 1) {	// base case
       return 1;
   }
   else {
       return x + mystery2(x-1);
   }
}
```

The call stack keeps track of the methods that have been called. When you are executing one method and it calls another method, the newer method call is placed on the stack.

Each recursive call has its own set of local variables, including formal parameters. Parameter values capture the progress of a recursive process, much like loop control variables capture the progress of a loop.

Any recursive solution can be replicated through the use of an iterative approach.

> Will not be required to write recursive program code.

## 10.2 Recursive Searching and Sorting

### Binary Search

Data must be in sorted order to use the binary search algorithm. The binary search algorithm starts at the middle of a sorted array or `ArrayList` and eliminates half of the array or `ArrayList` in each iteration until the desired value is found or all elements have been eliminated. Binary search can be more efficient than sequential/linear search.

> Will not be assessed an any search algorithms other than sequential/linear search and binary search.

The binary search algorithm can be written either iteratively or recursively.

### Merge Sort

Merge sort is a recursive sorting algorithm that can be used to sort elements in an array or `ArrayList`. It is more efficient than selection sort and insertion sort. 

A merge sort recursively breaks the values to be sorted in half until there is only one value to be sorted and then merges the sorted lists into one sorted list.