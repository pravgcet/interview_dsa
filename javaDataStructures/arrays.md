### Arrays in Java

An **array** in Java is a data structure that allows you to store multiple values of the same type in a single variable. Arrays are fixed in size, meaning their length cannot be changed once they are created.

#### Key Features of Arrays:

1. **Fixed Size**: The size of an array is defined when it is created and cannot be changed later.
2. **Indexed Access**: Elements in an array are accessed using zero-based indexing.
3. **Homogeneous Data**: All elements in an array must be of the same data type.
4. **Efficient Memory Allocation**: Arrays store elements in contiguous memory locations, making access and iteration efficient.

#### Syntax for Declaring and Initializing Arrays:

1. **Declaration**:

   ```java
   int[] numbers; // Preferred syntax
   int numbers[]; // Valid but less common
   ```

2. **Instantiation**:

   ```java
   numbers = new int[5]; // Creates an array of size 5
   ```

3. **Initialization**:
   ```java
   int[] numbers = {1, 2, 3, 4, 5}; // Declares, instantiates, and initializes
   ```

#### Accessing Array Elements:

You can access elements using their index:

```java
int[] numbers = {10, 20, 30, 40, 50};
System.out.println(numbers[0]); // Outputs: 10
numbers[2] = 35; // Updates the third element to 35
```

#### Common Operations:

1. **Iterating through an array**:

   - Using a `for` loop:
     ```java
     for (int i = 0; i < numbers.length; i++) {
         System.out.println(numbers[i]);
     }
     ```
   - Using an enhanced `for` loop:
     ```java
     for (int num : numbers) {
         System.out.println(num);
     }
     ```

2. **Finding the length of an array**:

   ```java
   int length = numbers.length;
   ```

3. **Sorting an array**:
   ```java
   Arrays.sort(numbers); // Requires import: import java.util.Arrays;
   ```

#### Multidimensional Arrays:

Java supports arrays with more than one dimension, such as 2D arrays:

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
System.out.println(matrix[1][2]); // Outputs: 6
```

#### Advantages of Arrays:

- Easy to use and access elements.
- Efficient for storing and accessing a fixed number of elements.

#### Limitations of Arrays:

- Fixed size: Cannot dynamically grow or shrink.
- Homogeneous: Cannot store mixed data types.

For dynamic-sized collections, consider using classes like `ArrayList` from the `java.util` package.
