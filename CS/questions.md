# Computer Science Interview Questions

---

## Questions

### 1. **Question**: Explain the difference between a stack and a queue. When would you use each?

**Difficulty**: Easy  
**Category**: Data Structures  
**Key Concepts**: LIFO vs FIFO, abstract data types, use cases  
**Sample Answer**:
A **stack** is a linear data structure that follows the Last-In, First-Out (LIFO) principle. The last element added is the first one to be removed. Common operations are `push` (add to top), `pop` (remove from top), and `peek` (view top element). Stacks are used in function call management (call stack), undo operations in editors, and parsing expressions.

A **queue** is a linear data structure that follows the First-In, First-Out (FIFO) principle. The first element added is the first one to be removed. Common operations are `enqueue` (add to rear), `dequeue` (remove from front), and `peek` (view front element). Queues are used in task scheduling, breadth-first search, and buffering data streams.

**Comparison:**

-   Stacks are ideal for problems where you need to reverse order or backtrack (e.g., DFS, undo).
-   Queues are ideal for problems where order of processing matters (e.g., BFS, print queues).

**Connected Questions**: [#5: Explain how a depth-first search (DFS) works and provide a use case.], [#7: Explain the concept of Big O notation and provide examples.]

**Further Reading**:

-   [Introduction to Algorithms by Cormen et al.](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/)
-   [GeeksforGeeks: Stack Data Structure](https://www.geeksforgeeks.org/stack-data-structure/)
-   [GeeksforGeeks: Queue Data Structure](https://www.geeksforgeeks.org/queue-data-structure/)

---

### 2. **Question**: What is the time complexity of binary search and when is it most effective?

**Difficulty**: Easy  
**Category**: Algorithms  
**Key Concepts**: Time complexity, divide and conquer, sorted arrays  
**Sample Answer**:
**Binary search** is an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing the search interval in half. If the value of the search key is less than the item in the middle, the search continues on the left half; otherwise, it continues on the right half.

-   **Time Complexity:** O(log n), where n is the number of elements. Each step halves the search space.
-   **Space Complexity:** O(1) for iterative, O(log n) for recursive (due to call stack).
-   **Effectiveness:** Binary search is most effective on large, sorted arrays or lists. It is not suitable for unsorted data or data structures with slow random access (like linked lists).

**Connected Questions**: [#7: Explain the concept of Big O notation and provide examples.], [#3: Explain the difference between a hash table and a binary search tree.]

**Further Reading**:

-   [Introduction to Algorithms by Cormen et al.](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/)
-   [Wikipedia: Binary Search Algorithm](https://en.wikipedia.org/wiki/Binary_search_algorithm)
-   [Khan Academy: Binary Search](https://www.khanacademy.org/computing/computer-science/algorithms/binary-search/a/binary-search)

---

### 3. **Question**: Explain the difference between a hash table and a binary search tree.

**Difficulty**: Medium  
**Category**: Data Structures  
**Key Concepts**: Hash functions, collision resolution, tree properties, order  
**Sample Answer**:
A **hash table** is a data structure that maps keys to values using a hash function. It provides average-case O(1) time complexity for insert, delete, and search operations. However, hash tables do not maintain any order among elements. Collisions are handled using techniques like chaining or open addressing.

A **binary search tree (BST)** is a tree data structure where each node has at most two children, and for each node, all elements in the left subtree are less, and all in the right subtree are greater. BSTs provide O(log n) average-case time complexity for insert, delete, and search if balanced, but can degrade to O(n) if unbalanced. BSTs maintain elements in sorted order, enabling in-order traversal.

**Comparison:**

-   Use hash tables for fast lookups without order.
-   Use BSTs when you need to maintain sorted order or perform range queries.

**Connected Questions**: [#2: What is the time complexity of binary search and when is it most effective?], [#7: Explain the concept of Big O notation and provide examples.]

**Further Reading**:

-   [Cracking the Coding Interview by Gayle Laakmann McDowell](https://www.crackingthecodinginterview.com/)
-   [GeeksforGeeks: Hash Table](https://www.geeksforgeeks.org/hashing-data-structure/)
-   [GeeksforGeeks: Binary Search Tree](https://www.geeksforgeeks.org/binary-search-tree-data-structure/)

---

### 4. **Question**: What is the difference between a process and a thread?

**Difficulty**: Medium  
**Category**: Operating Systems  
**Key Concepts**: Process management, threading, memory isolation, concurrency  
**Sample Answer**:
A **process** is an independent program in execution with its own memory space, resources, and system state. Processes are isolated from each other, and communication between them requires inter-process communication (IPC) mechanisms.

A **thread** is the smallest unit of execution within a process. Threads within the same process share memory and resources, making context switching between threads faster than between processes. Threads are used for parallelism within a single application, while processes are used for isolation and running multiple applications.

**Comparison:**

-   Processes: Strong isolation, more overhead, used for running separate applications.
-   Threads: Lightweight, share memory, used for parallel tasks within an application.

**Connected Questions**: [#9: Explain the concept of a deadlock and how to prevent it.]

**Further Reading**:

-   [Operating System Concepts by Silberschatz, Galvin, Gagne](https://www.os-book.com/)
-   [Wikipedia: Process (computing)](<https://en.wikipedia.org/wiki/Process_(computing)>)
-   [Wikipedia: Thread (computing)](<https://en.wikipedia.org/wiki/Thread_(computing)>)

---

### 5. **Question**: Explain how a depth-first search (DFS) works and provide a use case.

**Difficulty**: Medium  
**Category**: Algorithms  
**Key Concepts**: Graph traversal, recursion, backtracking, stack  
**Sample Answer**:
**Depth-first search (DFS)** is an algorithm for traversing or searching tree or graph data structures. It starts at the root (or an arbitrary node) and explores as far as possible along each branch before backtracking. DFS can be implemented using recursion or an explicit stack.

**Use Cases:**

-   Solving mazes and puzzles
-   Topological sorting
-   Detecting cycles in graphs
-   Pathfinding in games

DFS is useful when you want to explore all possible paths or need to backtrack to previous states.

**Connected Questions**: [#1: Explain the difference between a stack and a queue.], [#7: Explain the concept of Big O notation and provide examples.]

**Further Reading**:

-   [Introduction to Algorithms by Cormen et al.](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/)
-   [GeeksforGeeks: Depth First Search](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/)
-   [Khan Academy: DFS](https://www.khanacademy.org/computing/computer-science/algorithms/graph-representation/a/depth-first-search)

---

### 6. **Question**: What is the difference between TCP and UDP?

**Difficulty**: Medium  
**Category**: Computer Networks  
**Key Concepts**: Transport layer protocols, reliability, connection-oriented vs connectionless  
**Sample Answer**:
**TCP (Transmission Control Protocol)** is a connection-oriented protocol that ensures reliable, ordered, and error-checked delivery of data between applications. It establishes a connection before transmitting data and guarantees that data arrives in order and without duplication.

**UDP (User Datagram Protocol)** is a connectionless protocol that sends data without establishing a connection. It does not guarantee delivery, order, or error checking, making it faster but less reliable than TCP.

**Comparison:**

-   Use TCP for applications where reliability is critical (e.g., web browsing, file transfer).
-   Use UDP for applications where speed is more important than reliability (e.g., video streaming, online gaming).

**Connected Questions**: [#4: What is the difference between a process and a thread?]

**Further Reading**:

-   [Computer Networking: A Top-Down Approach by Kurose & Ross](https://www.pearson.com/en-us/subject-catalog/p/computer-networking-a-top-down-approach/P200000003481/9780136681557)
-   [Wikipedia: TCP](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)
-   [Wikipedia: UDP](https://en.wikipedia.org/wiki/User_Datagram_Protocol)

---

### 7. **Question**: Explain the concept of Big O notation and provide examples.

**Difficulty**: Easy  
**Category**: Algorithms  
**Key Concepts**: Algorithm analysis, asymptotic complexity, worst-case analysis  
**Sample Answer**:
**Big O notation** describes the upper bound of an algorithm's running time or space requirements in terms of input size (n). It provides a way to classify algorithms according to their worst-case or upper-bound performance as the input size grows.

**Common Big O Classes:**

-   O(1): Constant time (e.g., accessing an array element)
-   O(log n): Logarithmic time (e.g., binary search)
-   O(n): Linear time (e.g., traversing an array)
-   O(n log n): Linearithmic time (e.g., merge sort)
-   O(n^2): Quadratic time (e.g., bubble sort)

Big O helps compare the efficiency of algorithms and guides the selection of the most appropriate one for a given problem.

**Connected Questions**: [#2: What is the time complexity of binary search and when is it most effective?], [#3: Explain the difference between a hash table and a binary search tree.], [#5: Explain how a depth-first search (DFS) works and provide a use case.]

**Further Reading**:

-   [Introduction to Algorithms by Cormen et al.](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/)
-   [Big O Cheat Sheet](https://www.bigocheatsheet.com/)
-   [Khan Academy: Big O notation](https://www.khanacademy.org/computing/computer-science/algorithms/asymptotic-notation/a/big-o-notation)

---

### 8. **Question**: How does garbage collection work in programming languages?

**Difficulty**: Hard  
**Category**: Programming Languages  
**Key Concepts**: Memory management, reference counting, mark and sweep, generational GC  
**Sample Answer**:
**Garbage collection (GC)** is the process of automatically reclaiming memory that is no longer in use by the program. Common GC algorithms include reference counting, mark-and-sweep, and generational collection.

-   **Reference Counting:** Each object has a count of references. When the count drops to zero, the object is deallocated. Simple but cannot handle cyclic references.
-   **Mark-and-Sweep:** The GC marks all reachable objects and then sweeps through memory to collect unmarked (unreachable) objects. Handles cycles but can cause program pauses.
-   **Generational GC:** Divides objects by age (young/old). Young objects are collected more frequently. Improves performance by focusing on short-lived objects.

GC simplifies memory management for developers but can introduce overhead and unpredictable pauses.

**Connected Questions**: [#10: What is the difference between a compiler and an interpreter?]

**Further Reading**:

-   [Garbage Collection Handbook by Jones, Hosking, Moss](https://www.springer.com/gp/book/9781420082791)
-   [Wikipedia: Garbage Collection (computer science)](<https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)>)
-   [Java Garbage Collection Basics](https://www.oracle.com/webfolder/technetwork/tutorials/obe/java/gc01/index.html)

---

### 9. **Question**: Explain the concept of a deadlock and how to prevent it.

**Difficulty**: Hard  
**Category**: Operating Systems  
**Key Concepts**: Resource allocation, synchronization, deadlock conditions, prevention  
**Sample Answer**:
A **deadlock** occurs when two or more processes are each waiting for the other to release a resource, causing all to be blocked indefinitely. Four conditions must hold for a deadlock: mutual exclusion, hold and wait, no preemption, and circular wait.

**Prevention Techniques:**

-   **Resource ordering:** Impose a global order on resource acquisition.
-   **Avoid hold and wait:** Require processes to request all resources at once.
-   **Preemption:** Allow resources to be forcibly taken from processes.
-   **Deadlock detection and recovery:** Detect cycles and recover by terminating or rolling back processes.

**Connected Questions**: [#4: What is the difference between a process and a thread?]

**Further Reading**:

-   [Operating System Concepts by Silberschatz, Galvin, Gagne](https://www.os-book.com/)
-   [Wikipedia: Deadlock](https://en.wikipedia.org/wiki/Deadlock)
-   [GeeksforGeeks: Deadlock in Operating System](https://www.geeksforgeeks.org/deadlock-in-operating-system/)

---

### 10. **Question**: What is the difference between a compiler and an interpreter?

**Difficulty**: Medium  
**Category**: Programming Languages  
**Key Concepts**: Code execution, translation, compilation vs interpretation  
**Sample Answer**:
A **compiler** translates the entire source code of a program into machine code before execution. The resulting executable runs directly on the hardware, leading to faster execution times. Examples: C, C++ compilers.

An **interpreter** translates and executes code line by line at runtime, without producing a separate executable. This allows for more flexibility and easier debugging but generally results in slower execution. Examples: Python, JavaScript interpreters.

Some modern languages use a mix of both (e.g., Java uses a compiler to bytecode and a Just-In-Time (JIT) compiler/interpreter at runtime).

**Connected Questions**: [#8: How does garbage collection work in programming languages?]

**Further Reading**:

-   [Compilers: Principles, Techniques, and Tools by Aho, Lam, Sethi, Ullman](https://www.pearson.com/en-us/subject-catalog/p/compilers-principles-techniques-and-tools/P200000003481/9780136067056)
-   [Wikipedia: Compiler](https://en.wikipedia.org/wiki/Compiler)
-   [Wikipedia: Interpreter (computing)](<https://en.wikipedia.org/wiki/Interpreter_(computing)>)
