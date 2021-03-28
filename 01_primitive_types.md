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

Compound operators: `+=`, `−=`, ``*=`, `/=`, and `%=`

Increment operator: ++

Decrement operator: --

## 1.5 Casting and Ranges of Variables

Casting is used to create a temporary value converted to a different data type. 

Casting a `double` to an `int` causes the digits after the decimal to be taken off. 

The smallest possible `int` value is `Integer.MIN_VALUE`.
