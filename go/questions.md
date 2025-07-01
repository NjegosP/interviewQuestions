# Go Interview Questions

---

### 1. What is the difference between slices and arrays in Go?

**Difficulty**: Easy

**Sample Answer**:

-   **Arrays** in Go are fixed-size collections of elements of the same type. Their size is part of the type (e.g., `[5]int`). Arrays are value types, so assigning or passing them copies the entire array.
-   **Slices** are dynamically-sized, flexible views into arrays. They are reference types, pointing to an underlying array, and can grow or shrink using the `append` function. Slices have a length and a capacity, and changes to a slice affect the underlying array.

**Comparison:**

-   Use arrays when you need a fixed-size, value-type collection.
-   Use slices for most cases, as they are more flexible and idiomatic in Go.

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [Go Blog: Arrays, slices (oh my!)](https://blog.golang.org/slices-intro)
-   [Effective Go: Slices](https://golang.org/doc/effective_go.html#slices)
-   [Go by Example: Slices](https://gobyexample.com/slices)

---

### 2. What are goroutines and how do they differ from threads?

**Difficulty**: Easy

**Sample Answer**:
**Goroutines** are lightweight, managed threads in Go, created using the `go` keyword. They are multiplexed onto a small number of OS threads by the Go runtime scheduler, allowing thousands of goroutines to run concurrently with low overhead (2KB stack vs. 1MB for OS threads).

**Differences from threads:**

-   Goroutines are cheaper to create and manage.
-   The Go scheduler handles multiplexing and context switching.
-   Communication between goroutines is typically done via channels, not shared memory.

**Connected Questions**: [#3](#3), [#9](#9)

**Further Reading**:

-   [Go Blog: Concurrency is not parallelism](https://blog.golang.org/concurrency-is-not-parallelism)
-   [Go by Example: Goroutines](https://gobyexample.com/goroutines)
-   [Go Concurrency Patterns](https://blog.golang.org/pipelines)

---

### 3. Explain the concept of channels in Go and their types.

**Difficulty**: Easy

**Sample Answer**:
**Channels** are typed conduits for communication between goroutines. They allow safe data exchange and synchronization. Channels can be:

-   **Unbuffered**: Send blocks until receive is ready, and vice versa. Used for synchronization.
-   **Buffered**: Has a capacity; send blocks only when buffer is full, receive blocks when buffer is empty. Used for decoupling sender and receiver.

Channels are created with `make(chan Type)` and can be closed to signal no more values will be sent.

**Connected Questions**: [#2](#2), [#9](#9)

**Further Reading**:

-   [Go Blog: Channels](https://blog.golang.org/channels)
-   [Go by Example: Channels](https://gobyexample.com/channels)
-   [Go Concurrency Patterns](https://blog.golang.org/pipelines)

---

### 4. What is the difference between `var`, `:=`, and `const` in Go?

**Difficulty**: Easy

**Sample Answer**:

-   `var` declares a variable, optionally with a type and initial value. If no value is given, the zero value is used.
-   `:=` is short variable declaration, only inside functions, with type inferred from the right-hand side.
-   `const` declares a constant value, which must be assigned at compile time and cannot be changed.

**Comparison:**

-   Use `var` for package-level variables or when you need explicit type.
-   Use `:=` for concise local variable declarations.
-   Use `const` for values that never change.

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [Effective Go: Declarations and scope](https://golang.org/doc/effective_go.html#declaration)
-   [Go by Example: Variables](https://gobyexample.com/variables)
-   [Go by Example: Constants](https://gobyexample.com/constants)

---

### 5. Explain Go's interface system and how it differs from other languages.

**Difficulty**: Easy

**Sample Answer**:
Go interfaces are collections of method signatures. A type implements an interface simply by implementing its methods—no explicit declaration is needed. This is called **implicit implementation** and enables a form of duck typing: "if it walks like a duck and quacks like a duck, it's a duck."

**Differences from other languages:**

-   No `implements` keyword; implementation is automatic.
-   Interfaces are often small and focused (single-method interfaces are common).
-   The empty interface (`interface{}`) can hold any value.

**Connected Questions**: [#4](#4)

**Further Reading**:

-   [Effective Go: Interfaces](https://golang.org/doc/effective_go.html#interfaces)
-   [Go by Example: Interfaces](https://gobyexample.com/interfaces)
-   [Go Proverbs](https://go-proverbs.github.io/)

---

### 6. What is the difference between `defer`, `panic`, and `recover`?

**Difficulty**: Easy

**Sample Answer**:

-   `defer` schedules a function call to run after the surrounding function returns, often used for cleanup (e.g., closing files).
-   `panic` stops normal execution and begins panicking, unwinding the stack. Used for unrecoverable errors.
-   `recover` regains control of a panicking goroutine, allowing the program to continue. Only works inside deferred functions.

**Best Practices:**

-   Use `defer` for resource cleanup.
-   Use `panic` for truly exceptional situations.
-   Use `recover` sparingly, typically at the top level of a goroutine.

**Connected Questions**: [#7](#7)

**Further Reading**:

-   [Effective Go: Defer, Panic, and Recover](https://golang.org/doc/effective_go.html#defer)
-   [Go by Example: Panic](https://gobyexample.com/panic)
-   [Go by Example: Recover](https://gobyexample.com/recover)

---

### 7. Explain Go's memory management and garbage collection.

**Difficulty**: Easy

**Sample Answer**:
Go uses a concurrent, tri-color mark-and-sweep garbage collector. Memory is automatically managed, and the runtime determines whether variables are allocated on the stack or heap (using escape analysis). The GC runs in the background, minimizing pause times and allowing most programs to run with low-latency memory management.

**Best Practices:**

-   Minimize allocations in performance-critical code.
-   Use slices and structs efficiently to avoid unnecessary heap allocations.
-   Profile memory usage with Go tools.

**Connected Questions**: [#6](#6)

**Further Reading**:

-   [Go Memory Management](https://golang.org/doc/faq#garbage_collection)
-   [Go Blog: Memory Management](https://blog.golang.org/memory-management)
-   [Go Blog: The GC: Go's Real-time Garbage Collector](https://blog.golang.org/ismmkeynote)

---

### 8. What are Go modules and how do they work?

**Difficulty**: Easy

**Sample Answer**:
**Go modules** are the dependency management system introduced in Go 1.11. A module is a collection of related Go packages with a `go.mod` file at its root, specifying the module path and dependencies. Modules support semantic versioning and allow reproducible builds.

**Key Features:**

-   `go.mod` tracks dependencies and versions.
-   `go.sum` ensures cryptographic integrity.
-   Modules replace the older GOPATH workflow.

**Connected Questions**: [#4](#4)

**Further Reading**:

-   [Go Blog: Using Go Modules](https://blog.golang.org/using-go-modules)
-   [Go Modules Reference](https://golang.org/ref/mod)
-   [Go by Example: Modules](https://gobyexample.com/modules)

---

### 9. Explain the difference between `sync.Mutex` and `sync.RWMutex`.

**Difficulty**: Easy

**Sample Answer**:

-   `sync.Mutex` provides mutual exclusion, allowing only one goroutine to access a critical section at a time.
-   `sync.RWMutex` allows multiple readers or one writer. Multiple goroutines can acquire the read lock simultaneously, but only one can acquire the write lock, and only when no readers hold the lock.

**Best Practices:**

-   Use `Mutex` for simple mutual exclusion.
-   Use `RWMutex` when reads greatly outnumber writes.
-   Avoid deadlocks by always locking and unlocking in the same order.

**Connected Questions**: [#2](#2), [#3](#3)

**Further Reading**:

-   [Go by Example: Mutexes](https://gobyexample.com/mutexes)
-   [Go by Example: RWMutex](https://gobyexample.com/rwmutex)
-   [Go Blog: Share Memory by Communicating](https://blog.golang.org/share-memory-by-communicating)

---

### 10. What is the difference between `make` and `new` in Go?

**Difficulty**: Easy

**Sample Answer**:

-   `new(Type)` allocates zeroed storage for a new item of type `Type` and returns a pointer to it. Used for all types.
-   `make(Type, ...)` initializes and returns a reference to an object of type slice, map, or channel. Only works for these built-in types, and returns the type itself (not a pointer).

**Comparison:**

-   Use `new` for allocating structs or arrays.
-   Use `make` for slices, maps, and channels, as it initializes the internal data structures.

**Connected Questions**: [#1](#1), [#4](#4)

**Further Reading**:

-   [Effective Go: new vs make](https://golang.org/doc/effective_go.html#new)
-   [Go by Example: new](https://gobyexample.com/new)
-   [Go by Example: make](https://gobyexample.com/make)

### 11. What is a goroutine and how does it differ from a thread?

**Difficulty**: Easy

**Sample Answer**:
A goroutine is a lightweight thread managed by the Go runtime. Unlike OS threads, goroutines are multiplexed onto a smaller number of system threads, making them more memory-efficient and faster to create. The Go scheduler handles their execution, allowing thousands of goroutines to run concurrently.

**Connected Questions**: [#2](#2), [#12](#12)

**Further Reading**:

-   [Go Blog: Goroutines](https://blog.golang.org/goroutines)
-   [Go by Example: Goroutines](https://gobyexample.com/goroutines)

---

### 12. What is a channel in Go and how is it used?

**Difficulty**: Easy

**Sample Answer**:
A channel is a typed conduit for communication between goroutines. Channels allow goroutines to send and receive values, enabling safe data exchange and synchronization. Channels can be buffered or unbuffered, and are essential for building concurrent programs in Go.

**Connected Questions**: [#11](#11), [#2](#2)

**Further Reading**:

-   [Go Blog: Channels](https://blog.golang.org/channels)
-   [Go by Example: Channels](https://gobyexample.com/channels)

---

### 13. What is a Go interface and how does it enable polymorphism?

**Difficulty**: Easy

**Sample Answer**:
A Go interface is a type that specifies a set of method signatures. Any type that implements those methods satisfies the interface, enabling polymorphism. This allows functions to accept arguments of different types as long as they implement the required methods, supporting flexible and decoupled code.

**Connected Questions**: [#4](#4)

**Further Reading**:

-   [Go Blog: Interfaces](https://blog.golang.org/interfaces)
-   [Go by Example: Interfaces](https://gobyexample.com/interfaces)

---

### 14. How does Go handle memory management and garbage collection?

**Difficulty**: Easy

**Sample Answer**:
Go uses automatic garbage collection to manage memory. The runtime tracks object references and reclaims memory that is no longer reachable. Go's garbage collector is designed for low latency and efficiency, and escape analysis determines whether variables are allocated on the stack or heap.

**Connected Questions**: [#5](#5)

**Further Reading**:

-   [Go Blog: Memory Management](https://blog.golang.org/go-memory-management)
-   [Go Blog: Garbage Collection](https://blog.golang.org/garbage-collection)

---

### 15. What is a Go module and how does dependency management work?

**Difficulty**: Easy

**Sample Answer**:
A Go module is a collection of related Go packages with versioning and dependency management. The `go.mod` file defines the module path and dependencies. Go modules enable reproducible builds and easy dependency updates using commands like `go mod tidy` and `go get`.

**Connected Questions**: [#6](#6)

**Further Reading**:

-   [Go Blog: Using Go Modules](https://blog.golang.org/using-go-modules)
-   [Go Modules Reference](https://golang.org/ref/mod)

---

### 16. How does Go handle error handling and what are best practices?

**Difficulty**: Easy

**Sample Answer**:
Go uses explicit error handling, where functions return error values that must be checked. The `error` interface is used for error types, and custom errors can be created. Best practices include handling errors at the appropriate level, wrapping errors for context, and avoiding panic for expected errors.

**Connected Questions**: [#7](#7)

**Further Reading**:

-   [Go Blog: Error Handling](https://blog.golang.org/error-handling-and-go)
-   [Go by Example: Errors](https://gobyexample.com/errors)

---

### 17. What is a Go context and how is it used for cancellation and timeouts?

**Difficulty**: Easy

**Sample Answer**:
The `context` package in Go provides a way to carry deadlines, cancellation signals, and other request-scoped values across API boundaries. Contexts are used to control goroutines, especially in servers and concurrent applications, enabling graceful shutdown and resource cleanup.

**Connected Questions**: [#2](#2), [#11](#11)

**Further Reading**:

-   [Go Blog: Context](https://blog.golang.org/context)
-   [Go by Example: Context](https://gobyexample.com/context)

---

### 18. How does Go's type system support composition over inheritance?

**Difficulty**: Easy

**Sample Answer**:
Go favors composition over inheritance. Instead of class-based inheritance, Go uses struct embedding and interfaces to compose behavior. Embedding allows one struct to include another, inheriting its fields and methods, while interfaces enable polymorphism.

**Connected Questions**: [#13](#13)

**Further Reading**:

-   [Go Blog: Composition](https://blog.golang.org/laws-of-reflection)
-   [Go by Example: Struct Embedding](https://gobyexample.com/struct-embedding)

---

### 19. What is the purpose of the `defer` statement in Go?

**Difficulty**: Easy

**Sample Answer**:
The `defer` statement schedules a function call to run after the surrounding function returns. It is commonly used for resource cleanup, such as closing files or unlocking mutexes, ensuring cleanup code runs even if an error occurs.

**Connected Questions**: [#8](#8)

**Further Reading**:

-   [Go by Example: Defer](https://gobyexample.com/defer)
-   [Go Blog: Defer, Panic, and Recover](https://blog.golang.org/defer-panic-and-recover)

---

### 20. How does Go support testing and what are best practices for writing tests?

**Difficulty**: Easy

**Sample Answer**:
Go has built-in support for testing via the `testing` package. Tests are written in files ending with `_test.go` and use functions starting with `Test`. Best practices include writing table-driven tests, using subtests, and measuring code coverage with `go test -cover`.

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [Go Blog: Testing Techniques](https://blog.golang.org/subtests)
-   [Go by Example: Testing](https://gobyexample.com/testing)
