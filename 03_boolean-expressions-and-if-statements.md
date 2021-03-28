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
