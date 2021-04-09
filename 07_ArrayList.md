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