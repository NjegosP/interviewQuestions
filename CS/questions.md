# Computer Science Interview Questions

---

### 1. What is the difference between a stack and a queue? When would you use each? [Easy]

**Sample Answer**:
A **stack** is a linear data structure that follows the Last-In, First-Out (LIFO) principle. The last element added is the first one to be removed. Common operations are `push` (add to top), `pop` (remove from top), and `peek` (view top element). Stacks are used in function call management (call stack), undo operations in editors, and parsing expressions.

A **queue** is a linear data structure that follows the First-In, First-Out (FIFO) principle. The first element added is the first one to be removed. Common operations are `enqueue` (add to rear), `dequeue` (remove from front), and `peek` (view front element). Queues are used in task scheduling, breadth-first search, and buffering data streams.

**Comparison:**

-   Stacks are ideal for problems where you need to reverse order or backtrack (e.g., DFS, undo).
-   Queues are ideal for problems where order of processing matters (e.g., BFS, print queues).

**Connected Questions**: [#5](#5), [#7](#7)

**Further Reading**:

-   [Introduction to Algorithms by Cormen et al.](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/)
-   [GeeksforGeeks: Stack Data Structure](https://www.geeksforgeeks.org/stack-data-structure/)
-   [GeeksforGeeks: Queue Data Structure](https://www.geeksforgeeks.org/queue-data-structure/)

### 2. What is the time complexity of binary search and when is it most effective? [Easy]

**Sample Answer**:
**Binary search** is an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing the search interval in half. If the value of the search key is less than the item in the middle, the search continues on the left half; otherwise, it continues on the right half.

-   **Time Complexity:** O(log n), where n is the number of elements. Each step halves the search space.
-   **Space Complexity:** O(1) for iterative, O(log n) for recursive (due to call stack).
-   **Effectiveness:** Binary search is most effective on large, sorted arrays or lists. It is not suitable for unsorted data or data structures with slow random access (like linked lists).

**Connected Questions**: [#7](#7), [#3](#3)

**Further Reading**:

-   [Introduction to Algorithms by Cormen et al.](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/)
-   [Wikipedia: Binary Search Algorithm](https://en.wikipedia.org/wiki/Binary_search_algorithm)
-   [Khan Academy: Binary Search](https://www.khanacademy.org/computing/computer-science/algorithms/binary-search/a/binary-search)

### 3. What is the difference between a hash table and a binary search tree? [Easy]

A **hash table** is a data structure that maps keys to values using a hash function. It provides average-case O(1) time complexity for insert, delete, and search operations. However, hash tables do not maintain any order among elements. Collisions are handled using techniques like chaining or open addressing.

A **binary search tree (BST)** is a tree data structure where each node has at most two children, and for each node, all elements in the left subtree are less, and all in the right subtree are greater. BSTs provide O(log n) average-case time complexity for insert, delete, and search if balanced, but can degrade to O(n) if unbalanced. BSTs maintain elements in sorted order, enabling in-order traversal.

**Comparison:**

-   Use hash tables for fast lookups without order.
-   Use BSTs when you need to maintain sorted order or perform range queries.

**Connected Questions**: [#2](#2), [#7](#7)

**Further Reading**:

-   [Cracking the Coding Interview by Gayle Laakmann McDowell](https://www.crackingthecodinginterview.com/)
-   [GeeksforGeeks: Hash Table](https://www.geeksforgeeks.org/hashing-data-structure/)
-   [GeeksforGeeks: Binary Search Tree](https://www.geeksforgeeks.org/binary-search-tree-data-structure/)

### 4. What is the difference between a process and a thread? [Easy]

A **process** is an independent program in execution with its own memory space, resources, and system state. Processes are isolated from each other, and communication between them requires inter-process communication (IPC) mechanisms.

A **thread** is the smallest unit of execution within a process. Threads within the same process share memory and resources, making context switching between threads faster than between processes. Threads are used for parallelism within a single application, while processes are used for isolation and running multiple applications.

**Comparison:**

-   Processes: Strong isolation, more overhead, used for running separate applications.
-   Threads: Lightweight, share memory, used for parallel tasks within an application.

**Connected Questions**: [#9](#9)

**Further Reading**:

-   [Operating System Concepts by Silberschatz, Galvin, Gagne](https://www.os-book.com/)
-   [Wikipedia: Process (computing)](<https://en.wikipedia.org/wiki/Process_(computing)>)
-   [Wikipedia: Thread (computing)](<https://en.wikipedia.org/wiki/Thread_(computing)>)

### 5. Explain how a depth-first search (DFS) works and provide a use case. [Easy]

**Sample Answer**:
**Depth-first search (DFS)** is an algorithm for traversing or searching tree or graph data structures. It starts at the root (or an arbitrary node) and explores as far as possible along each branch before backtracking. DFS can be implemented using recursion or an explicit stack.

**Use Cases:**

-   Solving mazes and puzzles
-   Topological sorting
-   Detecting cycles in graphs
-   Pathfinding in games

DFS is useful when you want to explore all possible paths or need to backtrack to previous states.

**Connected Questions**: [#1](#1), [#7](#7)

**Further Reading**:

-   [Introduction to Algorithms by Cormen et al.](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/)
-   [GeeksforGeeks: Depth First Search](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/)
-   [Khan Academy: DFS](https://www.khanacademy.org/computing/computer-science/algorithms/graph-representation/a/depth-first-search)

### 6. What is the difference between TCP and UDP? [Easy]

**Sample Answer**:
**TCP (Transmission Control Protocol)** is a connection-oriented protocol that ensures reliable, ordered, and error-checked delivery of data between applications. It establishes a connection before transmitting data and guarantees that data arrives in order and without duplication.

**UDP (User Datagram Protocol)** is a connectionless protocol that sends data without establishing a connection. It does not guarantee delivery, order, or error checking, making it faster but less reliable than TCP.

**Comparison:**

-   Use TCP for applications where reliability is critical (e.g., web browsing, file transfer).
-   Use UDP for applications where speed is more important than reliability (e.g., video streaming, online gaming).

**Connected Questions**: [#4](#4)

**Further Reading**:

-   [Computer Networking: A Top-Down Approach by Kurose & Ross](https://www.pearson.com/en-us/subject-catalog/p/computer-networking-a-top-down-approach/P200000003481/9780136681557)
-   [Wikipedia: TCP](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)
-   [Wikipedia: UDP](https://en.wikipedia.org/wiki/User_Datagram_Protocol)

### 7. Explain the concept of Big O notation and provide examples. [Easy]

**Sample Answer**:
**Big O notation** describes the upper bound of an algorithm's running time or space requirements in terms of input size (n). It provides a way to classify algorithms according to their worst-case or upper-bound performance as the input size grows.

**Common Big O Classes:**

-   O(1): Constant time (e.g., accessing an array element)
-   O(log n): Logarithmic time (e.g., binary search)
-   O(n): Linear time (e.g., traversing an array)
-   O(n log n): Linearithmic time (e.g., merge sort)
-   O(n^2): Quadratic time (e.g., bubble sort)

Big O helps compare the efficiency of algorithms and guides the selection of the most appropriate one for a given problem.

**Connected Questions**: [#2](#2), [#3](#3), [#5](#5)

**Further Reading**:

-   [Introduction to Algorithms by Cormen et al.](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/)
-   [Big O Cheat Sheet](https://www.bigocheatsheet.com/)
-   [Khan Academy: Big O notation](https://www.khanacademy.org/computing/computer-science/algorithms/asymptotic-notation/a/big-o-notation)

### 8. How does garbage collection work in programming languages? [Easy]

**Sample Answer**:
**Garbage collection (GC)** is the process of automatically reclaiming memory that is no longer in use by the program. Common GC algorithms include reference counting, mark-and-sweep, and generational collection.

-   **Reference Counting:** Each object has a count of references. When the count drops to zero, the object is deallocated. Simple but cannot handle cyclic references.
-   **Mark-and-Sweep:** The GC marks all reachable objects and then sweeps through memory to collect unmarked (unreachable) objects. Handles cycles but can cause program pauses.
-   **Generational GC:** Divides objects by age (young/old). Young objects are collected more frequently. Improves performance by focusing on short-lived objects.

GC simplifies memory management for developers but can introduce overhead and unpredictable pauses.

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [Garbage Collection Handbook by Jones, Hosking, Moss](https://www.springer.com/gp/book/9781420082791)
-   [Wikipedia: Garbage Collection (computer science)](<https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)>)
-   [Java Garbage Collection Basics](https://www.oracle.com/webfolder/technetwork/tutorials/obe/java/gc01/index.html)

### 9. Explain the concept of a deadlock and how to prevent it. [Easy]

**Sample Answer**:
A **deadlock** occurs when two or more processes are each waiting for the other to release a resource, causing all to be blocked indefinitely. Four conditions must hold for a deadlock: mutual exclusion, hold and wait, no preemption, and circular wait.

**Prevention Techniques:**

-   **Resource ordering:** Impose a global order on resource acquisition.
-   **Avoid hold and wait:** Require processes to request all resources at once.
-   **Preemption:** Allow resources to be forcibly taken from processes.
-   **Deadlock detection and recovery:** Detect cycles and recover by terminating or rolling back processes.

**Connected Questions**: [#4](#4)

**Further Reading**:

-   [Operating System Concepts by Silberschatz, Galvin, Gagne](https://www.os-book.com/)
-   [Wikipedia: Deadlock](https://en.wikipedia.org/wiki/Deadlock)
-   [GeeksforGeeks: Deadlock in Operating System](https://www.geeksforgeeks.org/deadlock-in-operating-system/)

### 10. What is the difference between a compiler and an interpreter? [Easy]

**Sample Answer**:
A **compiler** translates the entire source code of a program into machine code before execution. The resulting executable runs directly on the hardware, leading to faster execution times. Examples: C, C++ compilers.

An **interpreter** translates and executes code line by line at runtime, without producing a separate executable. This allows for more flexibility and easier debugging but generally results in slower execution. Examples: Python, JavaScript interpreters.

Some modern languages use a mix of both (e.g., Java uses a compiler to bytecode and a Just-In-Time (JIT) compiler/interpreter at runtime).

**Connected Questions**: [#8](#8)

**Further Reading**:

-   [Compilers: Principles, Techniques, and Tools by Aho, Lam, Sethi, Ullman](https://www.pearson.com/en-us/subject-catalog/p/compilers-principles-techniques-and-tools/P200000003481/9780136067056)
-   [Wikipedia: Compiler](https://en.wikipedia.org/wiki/Compiler)
-   [Wikipedia: Interpreter (computing)](<https://en.wikipedia.org/wiki/Interpreter_(computing)>)

### 11. What is dynamic programming and how does it differ from recursion and memoization? [Easy]

**Sample Answer**:
Dynamic programming (DP) is an algorithmic technique for solving problems with overlapping subproblems and optimal substructure. It involves breaking a problem into smaller subproblems, solving each subproblem only once, and storing their solutions (usually in a table) to avoid redundant computation. DP can be implemented top-down (with recursion and memoization) or bottom-up (tabulation).

-   **Recursion** solves subproblems but may recompute the same subproblem multiple times.
-   **Memoization** is a top-down DP approach that caches results of expensive function calls.
-   **Tabulation** is a bottom-up DP approach that fills a table iteratively.

**Connected Questions**: [#2](#2), [#7](#7)

**Further Reading**:

-   [Introduction to Algorithms by Cormen et al.](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/)
-   [GeeksforGeeks: Dynamic Programming](https://www.geeksforgeeks.org/dynamic-programming/)
-   [MIT OpenCourseWare: Dynamic Programming](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/lecture-videos/lecture-19-dynamic-programming-i-fibonacci-shortest-paths/)

### 12. What is a graph, and what are the main types of graphs used in computer science? [Easy]

**Sample Answer**:
A graph is a data structure consisting of nodes (vertices) and edges (connections between nodes). Graphs can be:

-   **Directed** (edges have direction) or **undirected** (edges are bidirectional)
-   **Weighted** (edges have weights/costs) or **unweighted**
-   **Cyclic** (contains cycles) or **acyclic** (no cycles)

Graphs are represented using adjacency lists (efficient for sparse graphs) or adjacency matrices (efficient for dense graphs).

**Connected Questions**: [#5](#5), [#13](#13)

**Further Reading**:

-   [Introduction to Algorithms by Cormen et al.]
-   [GeeksforGeeks: Graph Data Structure](https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/)
-   [Khan Academy: Graphs](https://www.khanacademy.org/computing/computer-science/algorithms/graphs/a/graphs)

### 13. What is breadth-first search (BFS) and how does it differ from DFS? [Easy]

**Sample Answer**:
Breadth-first search (BFS) is a graph traversal algorithm that explores all neighbors at the current depth before moving to the next level. It uses a queue to keep track of nodes to visit. BFS is ideal for finding the shortest path in unweighted graphs.

-   **DFS** explores as far as possible along each branch before backtracking (uses stack/recursion).
-   **BFS** explores all neighbors at the current level before moving deeper (uses queue).

**Connected Questions**: [#5](#5), [#12](#12)

**Further Reading**:

-   [GeeksforGeeks: Breadth First Search](https://www.geeksforgeeks.org/breadth-first-search-or-bfs-for-a-graph/)
-   [Khan Academy: BFS](https://www.khanacademy.org/computing/computer-science/algorithms/graph-representation/a/breadth-first-search)

### 14. What is a heap, and what are its main applications? [Easy]

**Sample Answer**:
A heap is a specialized tree-based data structure that satisfies the heap property:

-   **Min-heap**: Parent node is less than or equal to its children
-   **Max-heap**: Parent node is greater than or equal to its children

Heaps are commonly implemented as binary trees and are used to implement priority queues, heapsort, and for efficient retrieval of the minimum/maximum element.

**Connected Questions**: [#7](#7), [#15](#15)

**Further Reading**:

-   [GeeksforGeeks: Heap Data Structure](https://www.geeksforgeeks.org/heap-data-structure/)
-   [Wikipedia: Heap (data structure)](<https://en.wikipedia.org/wiki/Heap_(data_structure)>)

### 15. What is a priority queue and how is it implemented? [Easy]

**Sample Answer**:
A priority queue is an abstract data type where each element has a priority, and elements are served based on priority (not just insertion order). The most common implementation is a binary heap, which allows efficient insertion and removal of the highest (or lowest) priority element.

Applications include task scheduling, Dijkstra's shortest path algorithm, and event-driven simulation.

**Connected Questions**: [#14](#14), [#7](#7)

**Further Reading**:

-   [GeeksforGeeks: Priority Queue](https://www.geeksforgeeks.org/priority-queue-set-1-introduction/)
-   [Introduction to Algorithms by Cormen et al.]

### 16. What is a hash function, and what makes a good hash function? [Easy]

**Sample Answer**:
A hash function maps input data to a fixed-size value (hash code). A good hash function distributes inputs uniformly across the output range, minimizes collisions, and is fast to compute. In cryptography, hash functions must also be irreversible and collision-resistant.

**Connected Questions**: [#3](#3)

**Further Reading**:

-   [GeeksforGeeks: Hash Functions](https://www.geeksforgeeks.org/hashing-set-1-introduction/)
-   [Wikipedia: Hash Function](https://en.wikipedia.org/wiki/Hash_function)

### 17. What is a trie, and where is it used? [Easy]

**Sample Answer**:
A trie (prefix tree) is a tree-like data structure used to store a dynamic set of strings, where each node represents a character. Tries are efficient for prefix-based searches, autocomplete, and dictionary implementations. They allow fast insertion, deletion, and prefix queries.

**Connected Questions**: [#3](#3), [#16](#16)

**Further Reading**:

-   [GeeksforGeeks: Trie Data Structure](https://www.geeksforgeeks.org/trie-insert-and-search/)
-   [Wikipedia: Trie](https://en.wikipedia.org/wiki/Trie)

### 18. What is a Bloom filter and what are its trade-offs? [Easy]

**Sample Answer**:
A Bloom filter is a space-efficient probabilistic data structure used to test whether an element is a member of a set. It can return false positives (may say an element is in the set when it is not) but never false negatives. It uses multiple hash functions and a bit array.

**Trade-offs:**

-   Very space-efficient for large sets
-   Allows fast membership queries
-   Cannot remove elements (in standard Bloom filters)
-   False positives possible, but false negatives are not

**Connected Questions**: [#16](#16)

**Further Reading**:

-   [Bloom Filters by Thomas H. Cormen](https://www.cs.dartmouth.edu/~thc/cs50/lectures/0304/0304.html)
-   [Wikipedia: Bloom Filter](https://en.wikipedia.org/wiki/Bloom_filter)

### 19. What is a Turing machine and why is it important in computer science? [Easy]

**Sample Answer**:
A Turing machine is a mathematical model of computation that defines an abstract machine capable of simulating any algorithm. It consists of an infinite tape, a tape head, and a set of states. Turing machines are fundamental to the theory of computation, helping define what problems are computable and forming the basis for the Church-Turing thesis.

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [Introduction to the Theory of Computation by Michael Sipser](https://www.cengage.com/c/introduction-to-the-theory-of-computation-3e-sipser/9781133187790/)
-   [Wikipedia: Turing Machine](https://en.wikipedia.org/wiki/Turing_machine)

### 20. What is the halting problem? [Easy]

**Sample Answer**:
The halting problem is the question of determining, from a description of an arbitrary computer program and an input, whether the program will finish running or continue forever. Alan Turing proved in 1936 that a general algorithm to solve the halting problem for all possible program-input pairs cannot exist (it is undecidable).

**Connected Questions**: [#19](#19)

**Further Reading**:

-   [Introduction to the Theory of Computation by Michael Sipser]
-   [Wikipedia: Halting Problem](https://en.wikipedia.org/wiki/Halting_problem)
