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