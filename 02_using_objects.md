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

