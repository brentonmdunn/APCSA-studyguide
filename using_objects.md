# Using Objects

## 2.1 Objects: Instances of Classes

An object is an instance of a class. A class is a formal implementation of the attributes (variables) and behaviors (methods) of an object.

## 2.2 Creating and Storing Objects (Instantiation)

A signature consists of the constructor name and the parameter list. Example: `public MyClass(int a, boolean b, String c)`

The list of parameters are known as formal parameters. The values that are passed in the parameters are known as actual parameters. 

Objects are created using the `new` keyword followed by a call to one of the constructors. Constructors have the same name as the class.

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

Void methods are methods that do not have a return type. They are declared as type `void`. Example: 

```java
public void print_A() {
    System.out.println("A");
    // no return statement needed
}
```

An object's behavior is defined by its methods. Abstraction allows a programmer to use a method even if the do not know how the method is written. They just need to know the name, the parameters, and the return type. If a method and/or constructor is called, the code within the method and/or constructor is executed. After completed, the program goes back to where it left off before the method/constructor call.

Non-static methods are called through objects of the class. A dot operator is used to call them. Using a `null` reference to call a method or access an instance variable causes a `NullPointerException` to be thrown

## 2.4 Calling a Void Method with Parameters

A method signature consists of a method name and the ordered list of parameter types. The values in the parameter list need to correspond to the order and type in the method signature. Methods are said to be overloaded when there are multiple methods with the same name but different signatures. Example:

```java
public static void myMethod() {
    System.out.println("This is the method with no parameters!");
}

public static void myMethod(int a) {
    System.out.println("This method has different parameters than the method above! The parameter is: " + a);
}
```

## 2.5 Calling a Non-void Method

Non-void methods return a value that is the same type as the return type in the signature. The return value must be stored in a variable or used as part of an expression. Example:

```java
public static int myIntMethod() {
    return 1 + 2;
}
```

## 2.6 String Objects: Concatenation, Literals, and More

`String` objects can be created using string literals or by calling the `String` class constructor. Example:

```java
String strLiteral = "my string";
String strConstructor = new String("my string");
```

`String` objects are immutable--the `String` methods do not change the `String` object. Strings can be concatenated using `+` or `+=`, resulting in a new `String` object. Primitive values can be concatenated with `String` objects. The primitive is implicitly converted to a `String` object. Escape sequences start with a `\` and give the ability to use reserved characters in a `String`. Example: `\"`, `\\`, and `\n`.