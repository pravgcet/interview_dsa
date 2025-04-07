### Maps in Java

A **Map** in Java is a data structure that stores key-value pairs, where each key is unique, and each key maps to exactly one value. Maps are part of the `java.util` package and are widely used for fast lookups and associations.

#### Key Features of Maps:

1. **Key-Value Pair Storage**: Each entry in a map consists of a key and a corresponding value.
2. **Unique Keys**: Keys in a map must be unique, but values can be duplicated.
3. **Efficient Lookups**: Maps provide fast retrieval of values based on their keys.

#### Types of Maps in Java:

1. **HashMap**:

   - **Description**: A `HashMap` is an implementation of the `Map` interface that uses a hash table for storage. It allows `null` keys and values.
   - **Features**:
     - Unordered: Does not maintain any order of keys.
     - Fast: Provides constant-time performance for basic operations like `get` and `put`.
   - **Example**:

     ```java
     import java.util.HashMap;

     public class HashMapExample {
         public static void main(String[] args) {
             HashMap<String, Integer> map = new HashMap<>();
             map.put("Apple", 1);
             map.put("Banana", 2);
             map.put("Cherry", 3);

             System.out.println(map.get("Apple")); // Outputs: 1
         }
     }
     ```

2. **LinkedHashMap**:

   - **Description**: A `LinkedHashMap` is similar to `HashMap` but maintains the insertion order of keys.
   - **Features**:
     - Ordered: Iterates over keys in the order they were inserted.
     - Slightly slower than `HashMap` due to the ordering overhead.
   - **Example**:

     ```java
     import java.util.LinkedHashMap;

     public class LinkedHashMapExample {
         public static void main(String[] args) {
             LinkedHashMap<String, Integer> map = new LinkedHashMap<>();
             map.put("Apple", 1);
             map.put("Banana", 2);
             map.put("Cherry", 3);

             System.out.println(map); // Outputs: {Apple=1, Banana=2, Cherry=3}
         }
     }
     ```

3. **TreeMap**:

   - **Description**: A `TreeMap` is a `Map` implementation that stores keys in a sorted order (natural or custom).
   - **Features**:
     - Sorted: Keys are sorted in ascending order by default.
     - Slower than `HashMap` due to sorting overhead.
   - **Example**:

     ```java
     import java.util.TreeMap;

     public class TreeMapExample {
         public static void main(String[] args) {
             TreeMap<String, Integer> map = new TreeMap<>();
             map.put("Banana", 2);
             map.put("Apple", 1);
             map.put("Cherry", 3);

             System.out.println(map); // Outputs: {Apple=1, Banana=2, Cherry=3}
         }
     }
     ```

4. **Hashtable**:

   - **Description**: A `Hashtable` is a legacy implementation of the `Map` interface. It is synchronized and does not allow `null` keys or values.
   - **Features**:
     - Thread-safe: Suitable for multi-threaded environments.
     - Slower than `HashMap` due to synchronization overhead.
   - **Example**:

     ```java
     import java.util.Hashtable;

     public class HashtableExample {
         public static void main(String[] args) {
             Hashtable<String, Integer> map = new Hashtable<>();
             map.put("Apple", 1);
             map.put("Banana", 2);

             System.out.println(map.get("Apple")); // Outputs: 1
         }
     }
     ```

5. **ConcurrentHashMap**:

   - **Description**: A `ConcurrentHashMap` is a thread-safe implementation of `HashMap` that allows concurrent access by multiple threads.
   - **Features**:
     - Thread-safe: Optimized for concurrent read and write operations.
     - Does not allow `null` keys or values.
   - **Example**:

     ```java
     import java.util.concurrent.ConcurrentHashMap;

     public class ConcurrentHashMapExample {
         public static void main(String[] args) {
             ConcurrentHashMap<String, Integer> map = new ConcurrentHashMap<>();
             map.put("Apple", 1);
             map.put("Banana", 2);

             System.out.println(map.get("Banana")); // Outputs: 2
         }
     }
     ```

#### Comparison of Map Implementations:

| Map Type            | Allows Null Keys/Values            | Maintains Order       | Thread-Safe |
| ------------------- | ---------------------------------- | --------------------- | ----------- |
| `HashMap`           | Yes (1 null key, many null values) | No                    | No          |
| `LinkedHashMap`     | Yes                                | Yes (insertion order) | No          |
| `TreeMap`           | No                                 | Yes (sorted order)    | No          |
| `Hashtable`         | No                                 | No                    | Yes         |
| `ConcurrentHashMap` | No                                 | No                    | Yes         |

#### Use Cases of Maps:

- **HashMap**: General-purpose map for fast lookups.
- **LinkedHashMap**: When insertion order matters.
- **TreeMap**: When sorted keys are required.
- **Hashtable**: Legacy code requiring thread safety.
- **ConcurrentHashMap**: Multi-threaded applications.
