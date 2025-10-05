# queue.array-cpp

### **Aim**

To implement a **Linear Queue** data structure using a class and a static array, demonstrating the core operations of **enqueue**, **dequeue**, and **display**.

***

### **Theory**

A **Queue** is a linear data structure that follows the **FIFO** (First-In, First-Out) principle, meaning the element inserted first is the one removed first.

* **Pointers:** The queue uses two pointers:
    * **`front`**: Points to the element at the beginning of the queue (the element to be removed next).
    * **`rear`**: Points to the element at the end of the queue (the last inserted element).
* **Operations:**
    * **`enqueue` (Insertion):** Elements are added at the **`rear`** end.
        * **Overflow:** Occurs if `rear` reaches the maximum size limit (`SIZE - 1`).
    * **`dequeue` (Deletion):** Elements are removed from the **`front`** end.
        * **Underflow:** Occurs if the queue is empty (`front == -1` or `front > rear`).
* **Implementation:** This specific implementation is a **static array-based queue**, where the size is fixed (`SIZE` is $5$). A limitation of this linear implementation is that space released at the front is not reused once the `rear` reaches the end of the array, leading to inefficient use of memory.

***

### **Algorithm**

1.  **Define Constants and Class:**
    a.  Define a constant `SIZE` as $5$ for the queue's maximum capacity.
    b.  Define a class `Queue` with a private array `arr[SIZE]`, and private integer pointers `front` and `rear`, initialized to $-1$ in the constructor.
2.  **`enqueue(int value)` Method:**
    a.  Check for **Overflow**: If `rear == SIZE - 1`, print "Queue Overflow!" and return.
    b.  If the queue is empty (`front == -1`), set `front = 0`.
    c.  Increment `rear` and insert the `value` into `arr[rear]`.
3.  **`dequeue()` Method:**
    a.  Check for **Underflow**: If `front == -1` or `front > rear`, print "Queue Underflow!" and return.
    b.  Print the element being removed (`arr[front]`).
    c.  Increment `front` to logically remove the element.
4.  **`display()` Method:**
    a.  Check for an empty queue (same condition as Underflow).
    b.  If not empty, iterate from the current `front` index up to the current `rear` index and print each element.
5.  **In `main`:**
    a.  Create a `Queue` object `q`.
    b.  Perform a sequence of operations to demonstrate the functionality: enqueue $10, 20, 30$; display; dequeue; display; enqueue $40$; display.

***

### **Conclusion**

This experiment successfully demonstrated the implementation of a **Linear Queue** using a static array, encapsulating the data structure within a C++ class. The program correctly modeled the **FIFO** (First-In, First-Out) principle through the **`enqueue`** operation at the **`rear`** and the **`dequeue`** operation at the **`front`**. It also incorporated essential error handling for **Queue Overflow** (when the array is full) and **Underflow** (when the queue is empty) conditions.
