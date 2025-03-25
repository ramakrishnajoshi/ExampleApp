# Kotlin Coroutines Learning Guide

## Table of Contents
1. [Basic Concepts](#basic-concepts)
2. [Coroutine Builders](#coroutine-builders)
3. [Dispatchers](#dispatchers)
4. [Suspend Functions](#suspend-functions)
5. [Structured Concurrency](#structured-concurrency)
6. [Error Handling](#error-handling)
7. [Real-world Examples](#real-world-examples)

## Basic Concepts

### What are Coroutines?
Coroutines are lightweight threads that allow you to write asynchronous code in a sequential way. They help in:
- Managing long-running tasks that might otherwise block the main thread
- Handling concurrent operations
- Simplifying asynchronous programming

### What is delay()?
`delay()` is a suspend function that pauses the coroutine for a specified time without blocking the thread. 
- Unlike `Thread.sleep()`, which blocks the entire thread
- `delay()` only suspends the coroutine, allowing other coroutines to use the thread
- Only works inside coroutines or suspend functions

Example:
```kotlin
// Blocks the thread - BAD
Thread.sleep(1000) // Other work can't be done on this thread

// Suspends only the coroutine - GOOD
delay(1000) // Other coroutines can use the thread
```