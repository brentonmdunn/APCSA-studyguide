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