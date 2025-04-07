### Set in Java

A **Set** in Java is a collection that does not allow duplicate elements. It is part of the `java.util` package and is commonly used when you need to store unique elements and perform operations like union, intersection, and difference.

#### Key Features of Set:

1. **No Duplicates**: A `Set` does not allow duplicate elements.
2. **Unordered**: The order of elements is not guaranteed (except for specific implementations like `LinkedHashSet`).
3. **Efficient Operations**: Provides efficient methods for checking membership and performing set operations.

#### Types of Set in Java:

1. **HashSet**:

   - **Description**: A `HashSet` is a collection that uses a hash table for storage. It does not maintain any order of elements.
   - **Features**:
     - Fast: Provides constant-time performance for basic operations like `add`, `remove`, and `contains`.
     - Allows `null` values.
   - **Example**:

     ```java
     import java.util.HashSet;

     public class HashSetExample {
         public static void main(String[] args) {
             HashSet<String> set = new HashSet<>();
             set.add("Apple");
             set.add("Banana");
             set.add("Cherry");
             set.add("Apple"); // Duplicate, will not be added

             System.out.println(set); // Outputs: [Banana, Cherry, Apple] (order may vary)
         }
     }
     ```

2. **LinkedHashSet**:

   - **Description**: A `LinkedHashSet` is similar to `HashSet` but maintains the insertion order of elements.
   - **Features**:
     - Ordered: Iterates over elements in the order they were inserted.
     - Slightly slower than `HashSet` due to the ordering overhead.
   - **Example**:

     ```java
     import java.util.LinkedHashSet;

     public class LinkedHashSetExample {
         public static void main(String[] args) {
             LinkedHashSet<String> set = new LinkedHashSet<>();
             set.add("Apple");
             set.add("Banana");
             set.add("Cherry");

             System.out.println(set); // Outputs: [Apple, Banana, Cherry]
         }
     }
     ```

3. **TreeSet**:

   - **Description**: A `TreeSet` is a `Set` implementation that stores elements in a sorted order (natural or custom).
   - **Features**:
     - Sorted: Elements are sorted in ascending order by default.
     - Does not allow `null` values.
   - **Example**:

     ```java
     import java.util.TreeSet;

     public class TreeSetExample {
         public static void main(String[] args) {
             TreeSet<String> set = new TreeSet<>();
             set.add("Banana");
             set.add("Apple");
             set.add("Cherry");

             System.out.println(set); // Outputs: [Apple, Banana, Cherry]
         }
     }
     ```

#### Comparison of Set Implementations:

| Set Type        | Allows Null Values | Maintains Order       | Sorted |
| --------------- | ------------------ | --------------------- | ------ |
| `HashSet`       | Yes                | No                    | No     |
| `LinkedHashSet` | Yes                | Yes (insertion order) | No     |
| `TreeSet`       | No                 | Yes (sorted order)    | Yes    |

#### Use Cases of Set:

- **HashSet**: When you need a collection of unique elements and order does not matter.
- **LinkedHashSet**: When you need unique elements and want to preserve the insertion order.
- **TreeSet**: When you need unique elements in a sorted order.

#### Common Operations on Set:

1. **Adding Elements**:

   ```java
   set.add("Element");
   ```

2. **Removing Elements**:

   ```java
   set.remove("Element");
   ```

3. **Checking Membership**:

   ```java
   set.contains("Element");
   ```

4. **Iterating Over Elements**:

   ```java
   for (String element : set) {
       System.out.println(element);
   }
   ```

5. **Set Operations**:
   - **Union**:
     ```java
     set1.addAll(set2);
     ```
   - **Intersection**:
     ```java
     set1.retainAll(set2);
     ```
   - **Difference**:
     ```java
     set1.removeAll(set2);
     ```
