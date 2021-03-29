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
-  `/* `Block/multi-line comments `*/`
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