+++
title = "Rust note - 01"
description = "Introduction and key concepts"
date = 2024-01-26
[taxonomies]
categories = ["learning","rust"]
tags = ["key-concepts","notes","threads","process","unit-type","reference-counting","smart-pointers"]
+++
## Introduction

In order to learn Rust, I decided to read the book [The Rust Programming Language](https://www.amazon.com/Rust-Programming-Language-2nd/dp/1718503105) by Steve Klabnik. To this day (2024-12-26), I don't remember why I didn't finish reading it. I later bought the book [rust in action](https://www.amazon.com/Rust-Action-TS-McNamara/dp/1617294551) by Tim McNamara, because in an article listing books to learn `Rust`, it was well ranked and its description appealed to me.

As I start the blog, I already have some notes on the book, I'm on page 42/456 😅. The notes I'm taking are more memos than course notes. For the blog I may motivate myself and make sentences. The notes won't just be about the Rust language, but perhaps also about questions asked when reading the books or working on projects.  

The first note is just some questions I asked an AI about key concepts.

## **Key Concepts:**

### **Threads**

- **Smallest Unit of Execution**: A thread is the smallest sequence of programmed instructions that can be managed by the OS scheduler.
- **Concurrent Execution**: Allows multiple threads to execute concurrently, improving performance.
- **Shared Resources**: Threads within the same process share memory and resources.
- **Individual Execution Stack**: Each thread has its own stack, but shares heap memory.
- **Use in Multicore Systems**: Ideal for parallel execution on multicore systems.

### **Processes**

- **Program Instance**: An executing instance of a program.
- **Memory Isolation**: Operates in its own memory space, isolated from other processes.
- **Contains Threads**: A process can contain multiple threads, which are its executable units.
- **Inter-Process Communication**: Uses IPC methods to communicate with other processes.
- **Resource Intensive**: Requires more resources than managing threads.
- **OS Managed**: Managed by the operating system for creation, scheduling, and termination.

### **Unit type**

- **Description**: The unit type in Rust, denoted as **`()`**, is a zero-sized type that signifies 'no value'.
- **Usage**: Commonly used as the return type for functions that do not return a meaningful value.
- **Comparison**: Similar to **`void`** in C/C++, but in Rust, **`()`** is an actual type and can be used where types are required.
- **Functionality**: In functions, **`return;`** or no return statement implicitly returns **`()`**.

### **Reference counting**

- **Memory Management Technique**: Manages the lifetime of objects through reference counts.
- **Reference Count Tracking**: Counts the number of references to an object.
- **Automatic Deallocation**: Object is deallocated when reference count reaches zero.
- **Prevents Memory Leaks**: Helps in automatic memory cleanup, avoiding manual memory management.
- **Usage in Shared Resources**: Useful for managing shared data structures and resources.
- **Increment/Decrement Counts**: Reference count increases with new references and decreases when references are removed.
- **Garbage Collection Assistance**: Simplifies garbage collection processes in some programming languages.

### **Smart pointers**

- **Automatic Memory Management**: Handles memory allocation and deallocation.
- **Resource Control**: Manages object lifetimes, preventing memory leaks.
- **Ownership Semantics**: Defines rules for object ownership (unique or shared).
- **Scoped Lifetimes**: Ensures cleanup when going out of scope.
- **Use in Complex Structures**: Ideal for managing resources in complex data structures.
- **Enhanced Safety**: Reduces errors like dangling pointers.
- **Overhead Handling**: More resource-intensive than raw pointers.
- **Language Implementation**: Common in C++, Rust, and other languages without garbage collection.
