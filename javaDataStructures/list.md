### List in Java

A **List** in Java is an ordered collection that allows duplicate elements. It is part of the `java.util` package and is widely used for storing and manipulating a sequence of elements.

#### Key Features of List:

1. **Ordered Collection**: Elements are stored in the order they are inserted.
2. **Allows Duplicates**: A `List` can contain duplicate elements.
3. **Indexed Access**: Elements can be accessed by their index (zero-based).

#### Types of List in Java:

1. **ArrayList**:

   - **Description**: A resizable array implementation of the `List` interface.
   - **Features**:
     - Fast random access due to array-based implementation.
     - Slower for insertions and deletions in the middle of the list.
   - **Example**:

     ```java
     import java.util.ArrayList;

     public class ArrayListExample {
         public static void main(String[] args) {
             ArrayList<String> list = new ArrayList<>();
             list.add("Apple");
             list.add("Banana");
             list.add("Cherry");

             System.out.println(list); // Outputs: [Apple, Banana, Cherry]
         }
     }
     ```

2. **LinkedList**:

   - **Description**: A doubly-linked list implementation of the `List` interface.
   - **Features**:
     - Faster for insertions and deletions compared to `ArrayList`.
     - Slower for random access due to sequential traversal.
   - **Example**:

     ```java
     import java.util.LinkedList;

     public class LinkedListExample {
         public static void main(String[] args) {
             LinkedList<String> list = new LinkedList<>();
             list.add("Apple");
             list.add("Banana");
             list.add("Cherry");

             System.out.println(list); // Outputs: [Apple, Banana, Cherry]
         }
     }
     ```

3. **Vector**:

   - **Description**: A legacy implementation of the `List` interface that is synchronized.
   - **Features**:
     - Thread-safe but slower due to synchronization overhead.
     - Rarely used in modern applications.
   - **Example**:

     ```java
     import java.util.Vector;

     public class VectorExample {
         public static void main(String[] args) {
             Vector<String> list = new Vector<>();
             list.add("Apple");
             list.add("Banana");
             list.add("Cherry");

             System.out.println(list); // Outputs: [Apple, Banana, Cherry]
         }
     }
     ```

4. **Stack**:

   - **Description**: A subclass of `Vector` that implements a LIFO (Last In, First Out) stack.
   - **Features**:
     - Provides stack-specific methods like `push()`, `pop()`, and `peek()`.
   - **Example**:

     ```java
     import java.util.Stack;

     public class StackExample {
         public static void main(String[] args) {
             Stack<String> stack = new Stack<>();
             stack.push("Apple");
             stack.push("Banana");
             stack.push("Cherry");

             System.out.println(stack.pop()); // Outputs: Cherry
         }
     }
     ```

#### Common Operations on List:

1. **Adding Elements**:

   ```java
   list.add("Element");
   ```

2. **Accessing Elements**:

   ```java
   String element = list.get(0); // Access the first element
   ```

3. **Removing Elements**:

   ```java
   list.remove("Element"); // Remove by value
   list.remove(0);         // Remove by index
   ```

4. **Iterating Over Elements**:

   - Using a `for` loop:
     ```java
     for (int i = 0; i < list.size(); i++) {
         System.out.println(list.get(i));
     }
     ```
   - Using an enhanced `for` loop:
     ```java
     for (String element : list) {
         System.out.println(element);
     }
     ```

5. **Checking Membership**:
   ```java
   boolean contains = list.contains("Element");
   ```

#### Comparison of List Implementations:

| List Type    | Backing Structure  | Allows Duplicates | Maintains Order | Thread-Safe |
| ------------ | ------------------ | ----------------- | --------------- | ----------- |
| `ArrayList`  | Resizable Array    | Yes               | Yes             | No          |
| `LinkedList` | Doubly Linked List | Yes               | Yes             | No          |
| `Vector`     | Resizable Array    | Yes               | Yes             | Yes         |
| `Stack`      | Resizable Array    | Yes               | Yes             | Yes         |

#### Use Cases of List:

- **ArrayList**: When frequent random access is required.
- **LinkedList**: When frequent insertions and deletions are required.
- **Vector**: When thread safety is required (legacy code).
- **Stack**: When LIFO operations are needed.
