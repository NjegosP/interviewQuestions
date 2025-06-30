# Go Interview Questions

---

## Questions

### 1. **Question**: Explain the difference between slices and arrays in Go.

**Difficulty**: Easy  
**Category**: Data Structures  
**Key Concepts**: Arrays, slices, dynamic sizing, memory allocation  
**Sample Answer**:

-   **Arrays** in Go are fixed-size collections of elements of the same type. Their size is part of the type (e.g., `[5]int`). Arrays are value types, so assigning or passing them copies the entire array.
-   **Slices** are dynamically-sized, flexible views into arrays. They are reference types, pointing to an underlying array, and can grow or shrink using the `append` function. Slices have a length and a capacity, and changes to a slice affect the underlying array.

**Comparison:**

-   Use arrays when you need a fixed-size, value-type collection.
-   Use slices for most cases, as they are more flexible and idiomatic in Go.

**Connected Questions**: [#10: What is the difference between `make` and `new` in Go?]

**Further Reading**:

-   [Go Blog: Arrays, slices (oh my!)](https://blog.golang.org/slices-intro)
-   [Effective Go: Slices](https://golang.org/doc/effective_go.html#slices)
-   [Go by Example: Slices](https://gobyexample.com/slices)

---

### 2. **Question**: What are goroutines and how do they differ from threads?

**Difficulty**: Medium  
**Category**: Concurrency  
**Key Concepts**: Goroutines, lightweight threads, scheduler, memory usage  
**Sample Answer**:
**Goroutines** are lightweight, managed threads in Go, created using the `go` keyword. They are multiplexed onto a small number of OS threads by the Go runtime scheduler, allowing thousands of goroutines to run concurrently with low overhead (2KB stack vs. 1MB for OS threads).

**Differences from threads:**

-   Goroutines are cheaper to create and manage.
-   The Go scheduler handles multiplexing and context switching.
-   Communication between goroutines is typically done via channels, not shared memory.

**Connected Questions**: [#3: Explain the concept of channels in Go and their types.], [#9: Explain the difference between `sync.Mutex` and `sync.RWMutex`.]

**Further Reading**:

-   [Go Blog: Concurrency is not parallelism](https://blog.golang.org/concurrency-is-not-parallelism)
-   [Go by Example: Goroutines](https://gobyexample.com/goroutines)
-   [Go Concurrency Patterns](https://blog.golang.org/pipelines)

---

### 3. **Question**: Explain the concept of channels in Go and their types.

**Difficulty**: Medium  
**Category**: Concurrency  
**Key Concepts**: Channels, buffered vs unbuffered, blocking, communication  
**Sample Answer**:
**Channels** are typed conduits for communication between goroutines. They allow safe data exchange and synchronization. Channels can be:

-   **Unbuffered**: Send blocks until receive is ready, and vice versa. Used for synchronization.
-   **Buffered**: Has a capacity; send blocks only when buffer is full, receive blocks when buffer is empty. Used for decoupling sender and receiver.

Channels are created with `make(chan Type)` and can be closed to signal no more values will be sent.

**Connected Questions**: [#2: What are goroutines and how do they differ from threads?], [#9: Explain the difference between `sync.Mutex` and `sync.RWMutex`.]

**Further Reading**:

-   [Go Blog: Channels](https://blog.golang.org/channels)
-   [Go by Example: Channels](https://gobyexample.com/channels)
-   [Go Concurrency Patterns](https://blog.golang.org/pipelines)

---

### 4. **Question**: What is the difference between `var`, `:=`, and `const` in Go?

**Difficulty**: Easy  
**Category**: Language Fundamentals  
**Key Concepts**: Variable declaration, type inference, constants  
**Sample Answer**:

-   `var` declares a variable, optionally with a type and initial value. If no value is given, the zero value is used.
-   `:=` is short variable declaration, only inside functions, with type inferred from the right-hand side.
-   `const` declares a constant value, which must be assigned at compile time and cannot be changed.

**Comparison:**

-   Use `var` for package-level variables or when you need explicit type.
-   Use `:=` for concise local variable declarations.
-   Use `const` for values that never change.

**Connected Questions**: [#10: What is the difference between `make` and `new` in Go?]

**Further Reading**:

-   [Effective Go: Declarations and scope](https://golang.org/doc/effective_go.html#declaration)
-   [Go by Example: Variables](https://gobyexample.com/variables)
-   [Go by Example: Constants](https://gobyexample.com/constants)

---

### 5. **Question**: Explain Go's interface system and how it differs from other languages.

**Difficulty**: Medium  
**Category**: Object-Oriented Programming  
**Key Concepts**: Interfaces, implicit implementation, duck typing  
**Sample Answer**:
Go interfaces are collections of method signatures. A type implements an interface simply by implementing its methods—no explicit declaration is needed. This is called **implicit implementation** and enables a form of duck typing: "if it walks like a duck and quacks like a duck, it's a duck."

**Differences from other languages:**

-   No `implements` keyword; implementation is automatic.
-   Interfaces are often small and focused (single-method interfaces are common).
-   The empty interface (`interface{}`) can hold any value.

**Connected Questions**: [#4: What is the difference between `var`, `:=`, and `const` in Go?]

**Further Reading**:

-   [Effective Go: Interfaces](https://golang.org/doc/effective_go.html#interfaces)
-   [Go by Example: Interfaces](https://gobyexample.com/interfaces)
-   [Go Proverbs](https://go-proverbs.github.io/)

---

### 6. **Question**: What is the difference between `defer`, `panic`, and `recover`?

**Difficulty**: Medium  
**Category**: Error Handling  
**Key Concepts**: Deferred functions, panic recovery, error handling patterns  
**Sample Answer**:

-   `defer` schedules a function call to run after the surrounding function returns, often used for cleanup (e.g., closing files).
-   `panic` stops normal execution and begins panicking, unwinding the stack. Used for unrecoverable errors.
-   `recover` regains control of a panicking goroutine, allowing the program to continue. Only works inside deferred functions.

**Best Practices:**

-   Use `defer` for resource cleanup.
-   Use `panic` for truly exceptional situations.
-   Use `recover` sparingly, typically at the top level of a goroutine.

**Connected Questions**: [#7: Explain Go's memory management and garbage collection.]

**Further Reading**:

-   [Effective Go: Defer, Panic, and Recover](https://golang.org/doc/effective_go.html#defer)
-   [Go by Example: Panic](https://gobyexample.com/panic)
-   [Go by Example: Recover](https://gobyexample.com/recover)

---

### 7. **Question**: Explain Go's memory management and garbage collection.

**Difficulty**: Hard  
**Category**: Memory Management  
**Key Concepts**: Garbage collection, memory allocation, escape analysis  
**Sample Answer**:
Go uses a concurrent, tri-color mark-and-sweep garbage collector. Memory is automatically managed, and the runtime determines whether variables are allocated on the stack or heap (using escape analysis). The GC runs in the background, minimizing pause times and allowing most programs to run with low-latency memory management.

**Best Practices:**

-   Minimize allocations in performance-critical code.
-   Use slices and structs efficiently to avoid unnecessary heap allocations.
-   Profile memory usage with Go tools.

**Connected Questions**: [#6: What is the difference between `defer`, `panic`, and `recover`?]

**Further Reading**:

-   [Go Memory Management](https://golang.org/doc/faq#garbage_collection)
-   [Go Blog: Memory Management](https://blog.golang.org/memory-management)
-   [Go Blog: The GC: Go's Real-time Garbage Collector](https://blog.golang.org/ismmkeynote)

---

### 8. **Question**: What are Go modules and how do they work?

**Difficulty**: Medium  
**Category**: Package Management  
**Key Concepts**: Modules, go.mod, versioning, dependency management  
**Sample Answer**:
**Go modules** are the dependency management system introduced in Go 1.11. A module is a collection of related Go packages with a `go.mod` file at its root, specifying the module path and dependencies. Modules support semantic versioning and allow reproducible builds.

**Key Features:**

-   `go.mod` tracks dependencies and versions.
-   `go.sum` ensures cryptographic integrity.
-   Modules replace the older GOPATH workflow.

**Connected Questions**: [#4: What is the difference between `var`, `:=`, and `const` in Go?]

**Further Reading**:

-   [Go Blog: Using Go Modules](https://blog.golang.org/using-go-modules)
-   [Go Modules Reference](https://golang.org/ref/mod)
-   [Go by Example: Modules](https://gobyexample.com/modules)

---

### 9. **Question**: Explain the difference between `sync.Mutex` and `sync.RWMutex`.

**Difficulty**: Medium  
**Category**: Concurrency  
**Key Concepts**: Mutexes, read-write locks, synchronization  
**Sample Answer**:

-   `sync.Mutex` provides mutual exclusion, allowing only one goroutine to access a critical section at a time.
-   `sync.RWMutex` allows multiple readers or one writer. Multiple goroutines can acquire the read lock simultaneously, but only one can acquire the write lock, and only when no readers hold the lock.

**Best Practices:**

-   Use `Mutex` for simple mutual exclusion.
-   Use `RWMutex` when reads greatly outnumber writes.
-   Avoid deadlocks by always locking and unlocking in the same order.

**Connected Questions**: [#2: What are goroutines and how do they differ from threads?], [#3: Explain the concept of channels in Go and their types.]

**Further Reading**:

-   [Go by Example: Mutexes](https://gobyexample.com/mutexes)
-   [Go by Example: RWMutex](https://gobyexample.com/rwmutex)
-   [Go Blog: Share Memory by Communicating](https://blog.golang.org/share-memory-by-communicating)

---

### 10. **Question**: What is the difference between `make` and `new` in Go?

**Difficulty**: Medium  
**Category**: Memory Allocation  
**Key Concepts**: Memory allocation, initialization, built-in functions  
**Sample Answer**:

-   `new(Type)` allocates zeroed storage for a new item of type `Type` and returns a pointer to it. Used for all types.
-   `make(Type, ...)` initializes and returns a reference to an object of type slice, map, or channel. Only works for these built-in types, and returns the type itself (not a pointer).

**Comparison:**

-   Use `new` for allocating structs or arrays.
-   Use `make` for slices, maps, and channels, as it initializes the internal data structures.

**Connected Questions**: [#1: Explain the difference between slices and arrays in Go.], [#4: What is the difference between `var`, `:=`, and `const` in Go?]

**Further Reading**:

-   [Effective Go: new vs make](https://golang.org/doc/effective_go.html#new)
-   [Go by Example: new](https://gobyexample.com/new)
-   [Go by Example: make](https://gobyexample.com/make)
