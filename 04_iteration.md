# Iteration

## 4.1 While Loops

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

## 4.2 For Loops

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