### Queue and Deque in Java

A **Queue** in Java is a linear data structure that follows the **FIFO (First In, First Out)** principle, where elements are added at the rear and removed from the front. A **Deque (Double-Ended Queue)** is an extension of a queue that allows elements to be added or removed from both ends.

#### Queue in Java

The `Queue` interface in Java is part of the `java.util` package and is implemented by classes like `LinkedList`, `PriorityQueue`, and `ArrayDeque`.

##### Key Features of Queue:

1. **FIFO Order**: Elements are processed in the order they are added.
2. **Operations**:
   - `offer()`: Adds an element to the rear of the queue.
   - `poll()`: Removes and returns the front element of the queue.
   - `peek()`: Retrieves the front element without removing it.

##### Example: Using `Queue` in Java

```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {
    public static void main(String[] args) {
        Queue<Integer> queue = new LinkedList<>();

        // Add elements to the queue
        queue.offer(10);
        queue.offer(20);
        queue.offer(30);

        // Peek at the front element
        System.out.println("Front element: " + queue.peek()); // Outputs: 10

        // Remove elements from the queue
        System.out.println("Removed: " + queue.poll()); // Outputs: 10
        System.out.println("Removed: " + queue.poll()); // Outputs: 20

        // Check the queue
        System.out.println("Queue: " + queue); // Outputs: [30]
    }
}
```

#### Deque in Java

A **Deque (Double-Ended Queue)** is a linear data structure that allows insertion and deletion from both ends. It is implemented by classes like `ArrayDeque` and `LinkedList`.

##### Key Features of Deque:

1. **Flexible Operations**: Supports both FIFO and LIFO (Last In, First Out) operations.
2. **Operations**:
   - `addFirst()`: Adds an element to the front.
   - `addLast()`: Adds an element to the rear.
   - `removeFirst()`: Removes the front element.
   - `removeLast()`: Removes the rear element.
   - `peekFirst()`: Retrieves the front element without removing it.
   - `peekLast()`: Retrieves the rear element without removing it.

##### Example: Using `Deque` in Java

```java
import java.util.ArrayDeque;
import java.util.Deque;

public class DequeExample {
    public static void main(String[] args) {
        Deque<Integer> deque = new ArrayDeque<>();

        // Add elements to the deque
        deque.addFirst(10);
        deque.addLast(20);
        deque.addLast(30);

        // Peek at both ends
        System.out.println("Front element: " + deque.peekFirst()); // Outputs: 10
        System.out.println("Rear element: " + deque.peekLast()); // Outputs: 30

        // Remove elements from both ends
        System.out.println("Removed from front: " + deque.removeFirst()); // Outputs: 10
        System.out.println("Removed from rear: " + deque.removeLast()); // Outputs: 30

        // Check the deque
        System.out.println("Deque: " + deque); // Outputs: [20]
    }
}
```

#### Differences Between Queue and Deque:

| Feature               | Queue                                       | Deque                      |
| --------------------- | ------------------------------------------- | -------------------------- |
| **Insertion/Removal** | Only at rear/front                          | Both ends                  |
| **Order**             | FIFO                                        | FIFO or LIFO               |
| **Implementation**    | `LinkedList`, `PriorityQueue`, `ArrayDeque` | `ArrayDeque`, `LinkedList` |

#### Use Cases:

- **Queue**: Task scheduling, breadth-first search (BFS), and producer-consumer problems.
- **Deque**: Palindrome checking, undo/redo operations, and implementing stacks or queues.
