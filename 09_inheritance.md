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

