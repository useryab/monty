# monty

## 0x19. C - Stacks, Queues - LIFO, FIFO

**Stacks and Queues:**

* **Stacks:** A stack is a linear data structure that follows the **LIFO (Last In First Out)** principle. Imagine a stack of plates: the last plate you put on is the first one you can take off. In C, stacks are often implemented using arrays or linked lists.

* **Queues:** A queue is another linear data structure that follows the **FIFO (First In First Out)** principle. Think of a line at a store: the first person in line gets served first. In C, queues can also be implemented using arrays or linked lists.

**LIFO vs FIFO:**

* **LIFO (Last In First Out):** With LIFO, the element that is added to the stack last (the "top" element) is the first one to be removed. This is like the plate analogy mentioned earlier.

* **FIFO (First In First Out):** With FIFO, the element that is added to the queue first (the "front" element) is the first one to be removed. This is like the line at the store analogy.

**Choosing Between Stacks and Queues:**

The choice between using a stack or a queue depends on the specific needs of your program. Here are some general guidelines:

* Use a stack when you need to follow a LIFO order, such as:
    * Undo/redo functionality
    * Function call history
    * Expression evaluation (postfix notation)

* Use a queue when you need to follow a FIFO order, such as:
    * Processing tasks in a specific order
    * Simulating a waiting line
    * Breadth-first search algorithms


* You can find resources online that explore implementing stacks and queues in C code, including examples. Search for "C stack implementation" or "C queue implementation" to find tutorials.
* Here are some additional resources that you might find helpful:
    * Stacks and Queues in C: [https://data-flair.training/blogs/stack-in-data-structure/](https://data-flair.training/blogs/stack-in-data-structure/)


**Stacks:**

* **Concept:** A stack follows **LIFO (Last In First Out)**, like a stack of plates. The last plate added is the first one you can remove.

* **Diagram:**

Imagine a vertical stack of plates:

```
+-----> (Top)  <- Newest element
| Plate 3
| Plate 2
| Plate 1 (Bottom) <- Oldest element
+----->
```

* **Operations:**
    * **Push:** Add an element to the "top" of the stack.
    * **Pop:** Remove the element from the "top" of the stack.

* **C Implementation:** Stacks can be implemented using arrays or linked lists. Here's a simplified example (assuming an array):

```c
#define MAX_SIZE 100

int stack[MAX_SIZE];
int top = -1; // Initially stack is empty

void push(int data) {
  if (top == MAX_SIZE - 1) {
    printf("Stack Overflow\n");
  } else {
    stack[++top] = data;
  }
}

int pop() {
  if (top == -1) {
    printf("Stack Underflow\n");
    return -1;
  } else {
    return stack[top--];
  }
}
```

**Queues:**

* **Concept:** A queue follows **FIFO (First In First Out)**, like a line at a store. The first person in line gets served first.

* **Diagram:**

Imagine a line of people waiting:

```
       (Front)  -> Person who came first
Person 3  ->
Person 2  ->
Person 1 (Rear)  <- Person who came last
```

* **Operations:**
    * **Enqueue:** Add an element to the "back" (rear) of the queue.
    * **Dequeue:** Remove the element from the "front" of the queue.

* **C Implementation:** Similar to stacks, queues can be implemented using arrays or linked lists. Here's a simplified example (assuming an array):

```c
#define MAX_SIZE 100

int queue[MAX_SIZE];
int front = -1, rear = -1; // Initially queue is empty

void enqueue(int data) {
  if (rear == MAX_SIZE - 1) {
    printf("Queue Overflow\n");
  } else {
    if (front == -1) {
      front = 0;
    }
    queue[++rear] = data;
  }
}

int dequeue() {
  if (front == -1 || front > rear) {
    printf("Queue Underflow\n");
    return -1;
  } else {
    int data = queue[front];
    if (front == rear) {
      front = rear = -1; // Reset if only one element
    } else {
      front++;
    }
    return data;
  }
}
```

**Choosing Between Stacks and Queues:**

Remember, the choice depends on your program's needs:

* Use a stack for LIFO operations (undo/redo, function calls).
* Use a queue for FIFO operations (processing tasks, waiting lines).

I hope this explanation with pictures and diagrams helps you understand stacks and queues in C better!
