### Stack in Java

A **Stack** in Java is a linear data structure that follows the **LIFO (Last In, First Out)** principle, where the last element added to the stack is the first one to be removed. It is commonly used for tasks like expression evaluation, backtracking, and undo operations.

#### Key Features of Stack:

1. **LIFO Order**: The last element added is the first to be removed.
2. **Operations**:
   - `push()`: Adds an element to the top of the stack.
   - `pop()`: Removes and returns the top element of the stack.
   - `peek()`: Retrieves the top element without removing it.
   - `isEmpty()`: Checks if the stack is empty.

#### Stack Implementation in Java:

Java provides a built-in `Stack` class in the `java.util` package. It extends the `Vector` class and provides standard stack operations.

##### Example: Using `Stack` in Java

```java
import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();

        // Push elements onto the stack
        stack.push(10);
        stack.push(20);
        stack.push(30);

        // Peek at the top element
        System.out.println("Top element: " + stack.peek()); // Outputs: 30

        // Pop elements from the stack
        System.out.println("Popped: " + stack.pop()); // Outputs: 30
        System.out.println("Popped: " + stack.pop()); // Outputs: 20

        // Check if the stack is empty
        System.out.println("Is stack empty? " + stack.isEmpty()); // Outputs: false

        // Remaining stack
        System.out.println("Stack: " + stack); // Outputs: [10]
    }
}
```

#### Custom Implementation of Stack:

You can also implement a stack using an array or a `LinkedList`.

##### Example: Custom Stack Implementation Using Array

```java
class CustomStack {
    private int[] stack;
    private int top;
    private int capacity;

    public CustomStack(int size) {
        stack = new int[size];
        capacity = size;
        top = -1;
    }

    // Push an element onto the stack
    public void push(int value) {
        if (top == capacity - 1) {
            System.out.println("Stack Overflow");
            return;
        }
        stack[++top] = value;
    }

    // Pop an element from the stack
    public int pop() {
        if (top == -1) {
            System.out.println("Stack Underflow");
            return -1;
        }
        return stack[top--];
    }

    // Peek at the top element
    public int peek() {
        if (top == -1) {
            System.out.println("Stack is empty");
            return -1;
        }
        return stack[top];
    }

    // Check if the stack is empty
    public boolean isEmpty() {
        return top == -1;
    }
}

public class CustomStackExample {
    public static void main(String[] args) {
        CustomStack stack = new CustomStack(5);

        stack.push(10);
        stack.push(20);
        stack.push(30);

        System.out.println("Top element: " + stack.peek()); // Outputs: 30
        System.out.println("Popped: " + stack.pop()); // Outputs: 30
        System.out.println("Is stack empty? " + stack.isEmpty()); // Outputs: false
    }
}
```

#### Use Cases of Stack:

1. **Expression Evaluation**: Used for evaluating postfix or prefix expressions.
2. **Backtracking**: Helps in algorithms like maze solving or recursion.
3. **Undo Operations**: Used in text editors to implement undo functionality.
4. **Function Call Stack**: Used to manage function calls in programming languages.

#### Advantages of Stack:

- Simple and easy to use.
- Efficient for managing data with LIFO order.

#### Limitations of Stack:

- Fixed size if implemented using an array.
- Limited functionality compared to other data structures like queues or deques.
