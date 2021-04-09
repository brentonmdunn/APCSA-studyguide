# 2-D Array

## 8.1 2-D Array

2-D arrays are stored as arrays of arrays. Therefore, the way 1-D arrays are created and indexed is similar to 1-D array objects.

```java
int[][] myArray1 = new int[2][3];

// initializer list
int[][] myArray2 = {{2, 3, 4}, {6,  7, 8}};
```

> Will not be assessed on 2-D arrays that are not rectangular.

When assessing the element at `arr[first][second]`, the first index is used for rows, the second index is used for columns.

The initializer list used to create and initialize 2-D array consists of initializer lists that represent 1-D arrays. The square brackets `[row][col]` are used to access and modify an element in a 2-D array. “Row-major” order refers to an ordering of 2-D array elements where traversal occurs across each row, while “column-major order” traversal occurs down each column.

```java
// modify a value
myArray[0][1] = 2;
```

## 8.2 Traversing 2-D Arrays

Nested iteration statements are used to traverse and access all elements in a 2-D array. Since 2-D arrays are stored as arrays of arrays, the way 2-D arrays are traversed using `for` loops and enhanced `for` loops is similar to 1-D array objects. Nested iteration statements can be written to traverse the 2-D array in “row-major order” or “column-major order.” The outer loop of a nested enhanced `for` loop used to traverse a 2-D array traverses the rows. Therefore, the enhanced `for` loop variable must be the type of each row, which is a 1-D array. The inner loop traverses a single row. Therefore, the inner enhanced `for` loop variable must be the same type as the elements stored in the 1-D array.

```java
myArray.length		// returns the number of rows
myArray[0].length	// returns the number of columns

// standard for loop
for (int row = 0; row < myArray.lenth; row++) {
	for (int col = 0; col < myArray[0].length; col++) {
		System.out.println(myArray[row][col]);
	}
}

// enhanced for loop
for (int[] row : myArray) {
	for (int num : row) {
		System.out.println(num);
	}
}
```

When applying sequential/linear search algorithms to 2-D arrays, each row must be accessed then sequential/linear search algorithm applied to each row of a 2-D array. 

All standard 1-D array algorithms can be applied to 2-D array objects.