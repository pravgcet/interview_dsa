### Heap in Java

A **Heap** is a special tree-based data structure that satisfies the **heap property**:

- In a **Max-Heap**, the value of each parent node is greater than or equal to the values of its children.
- In a **Min-Heap**, the value of each parent node is less than or equal to the values of its children.

Heaps are commonly used to implement priority queues and for efficient sorting algorithms like **Heap Sort**.

#### Key Features of Heap:

1. **Complete Binary Tree**: A heap is always a complete binary tree, meaning all levels are fully filled except possibly the last, which is filled from left to right.
2. **Heap Property**:
   - Max-Heap: Parent nodes are greater than or equal to their children.
   - Min-Heap: Parent nodes are less than or equal to their children.
3. **Efficient Operations**:
   - Insertion and deletion take **O(log n)** time.
   - Accessing the root (max or min) takes **O(1)** time.

#### Heap Implementation in Java:

Java provides a built-in class called `PriorityQueue` in the `java.util` package, which implements a Min-Heap by default.

##### Example: Using `PriorityQueue` as a Min-Heap

```java
import java.util.PriorityQueue;

public class MinHeapExample {
    public static void main(String[] args) {
        // Create a Min-Heap
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();

        // Add elements to the heap
        minHeap.add(10);
        minHeap.add(20);
        minHeap.add(5);
        minHeap.add(15);

        // Access and remove elements
        System.out.println("Min element: " + minHeap.peek()); // Outputs: 5
        System.out.println("Removed: " + minHeap.poll()); // Outputs: 5
        System.out.println("Min element after removal: " + minHeap.peek()); // Outputs: 10
    }
}
```

##### Example: Using `PriorityQueue` as a Max-Heap

To implement a Max-Heap, you can use a custom comparator:

```java
import java.util.Collections;
import java.util.PriorityQueue;

public class MaxHeapExample {
    public static void main(String[] args) {
        // Create a Max-Heap
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());

        // Add elements to the heap
        maxHeap.add(10);
        maxHeap.add(20);
        maxHeap.add(5);
        maxHeap.add(15);

        // Access and remove elements
        System.out.println("Max element: " + maxHeap.peek()); // Outputs: 20
        System.out.println("Removed: " + maxHeap.poll()); // Outputs: 20
        System.out.println("Max element after removal: " + maxHeap.peek()); // Outputs: 15
    }
}
```

#### Custom Implementation of Heap:

You can also implement a heap manually using an array.

##### Example: Custom Min-Heap Implementation

```java
class MinHeap {
    private int[] heap;
    private int size;
    private int capacity;

    public MinHeap(int capacity) {
        this.capacity = capacity;
        this.size = 0;
        this.heap = new int[capacity];
    }

    private int parent(int i) { return (i - 1) / 2; }
    private int leftChild(int i) { return 2 * i + 1; }
    private int rightChild(int i) { return 2 * i + 2; }

    public void insert(int value) {
        if (size == capacity) {
            System.out.println("Heap Overflow");
            return;
        }
        heap[size] = value;
        int current = size;
        size++;

        // Heapify up
        while (current > 0 && heap[current] < heap[parent(current)]) {
            swap(current, parent(current));
            current = parent(current);
        }
    }

    public int extractMin() {
        if (size == 0) return Integer.MIN_VALUE;
        if (size == 1) return heap[--size];

        int root = heap[0];
        heap[0] = heap[--size];
        heapify(0);
        return root;
    }

    private void heapify(int i) {
        int smallest = i;
        int left = leftChild(i);
        int right = rightChild(i);

        if (left < size && heap[left] < heap[smallest]) smallest = left;
        if (right < size && heap[right] < heap[smallest]) smallest = right;

        if (smallest != i) {
            swap(i, smallest);
            heapify(smallest);
        }
    }

    private void swap(int i, int j) {
        int temp = heap[i];
        heap[i] = heap[j];
        heap[j] = temp;
    }
}

public class CustomHeapExample {
    public static void main(String[] args) {
        MinHeap heap = new MinHeap(10);
        heap.insert(10);
        heap.insert(20);
        heap.insert(5);
        heap.insert(15);

        System.out.println("Extracted Min: " + heap.extractMin()); // Outputs: 5
        System.out.println("Extracted Min: " + heap.extractMin()); // Outputs: 10
    }
}
```

#### Use Cases of Heap:

1. **Priority Queues**: Used to manage tasks with priorities.
2. **Heap Sort**: Sorting algorithm with **O(n log n)** complexity.
3. **Graph Algorithms**: Used in Dijkstra's and Prim's algorithms.
4. **Median Finder**: Efficiently find the median in a stream of numbers.

#### Advantages of Heap:

- Efficient for priority-based operations.
- Provides fast access to the smallest or largest element.

#### Limitations of Heap:

- Not suitable for searching arbitrary elements.
- Requires additional memory for dynamic resizing.
