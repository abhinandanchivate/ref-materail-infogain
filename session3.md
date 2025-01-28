### Hands-on Lab: Day 5 - Lambda Expressions, Higher-Order Functions, Functional Collections, and Null Safety

---

### **Lab Overview**

In this lab, you will explore advanced functional programming concepts in Kotlin, including lambda expressions, higher-order functions, functional collection operations, and null safety. Through hands-on tasks, you will implement practical use cases, work with complex scenarios, and complete assignments to deepen your understanding of Kotlin's functional programming capabilities and best practices.

---

### **1. Lab Preparation**

#### **Prerequisites**
- Basic understanding of Kotlin programming.
- Familiarity with functional programming concepts.
- IDE setup (e.g., IntelliJ IDEA or Eclipse).
- Kotlin runtime and build tools (Gradle or Maven).

#### **Tools Required**
- IntelliJ IDEA or Eclipse.
- Local Kotlin development environment.

---

### **2. Lambda Expressions: Syntax and Use Cases**

#### **Objective**
- Understand the syntax and usage of lambda expressions in Kotlin.
- Write lambda functions to process data.

#### **Task 1: Write a Lambda Function**

1. Open your IDE and create a new Kotlin project.
2. Define a lambda function to calculate the square of a number.
3. Use the lambda function to manipulate a list of numbers.

#### **Example Code**
```kotlin
fun main() {
    val square: (Int) -> Int = { it * it }
    val numbers = listOf(1, 2, 3, 4, 5)
    val squares = numbers.map(square)
    println("Squares: $squares")
}
```

#### **Deliverable**
- A Kotlin program using lambda expressions to manipulate data.

---

### **3. Higher-Order Functions: Map, Filter, Reduce**

#### **Objective**
- Understand higher-order functions and their applications.
- Use `map`, `filter`, and `reduce` to process collections.

#### **Task 2: Create a Higher-Order Function**

1. Define a higher-order function that takes a list and a lambda as parameters.
2. Use this function to filter and process data.

#### **Example Code**
```kotlin
fun processList(numbers: List<Int>, operation: (Int) -> Boolean): List<Int> {
    return numbers.filter(operation)
}

fun main() {
    val numbers = listOf(10, 20, 30, 40, 50)
    val result = processList(numbers) { it > 25 }
    println("Filtered List: $result")
}
```

#### **Deliverable**
- A higher-order function that processes lists using lambdas.

---

### **4. Functional Collections: List, Set, Map Operations**

#### **Objective**
- Perform operations on functional collections such as `List`, `Set`, and `Map`.
- Leverage Kotlin's standard library functions.

#### **Task 3: Manipulate Collections**

1. Create a program to demonstrate operations on `List`, `Set`, and `Map`.
2. Use functions like `map`, `filter`, `groupBy`, and `reduce`.

#### **Example Code**
```kotlin
fun main() {
    val items = listOf("Apple", "Banana", "Cherry", "Apple", "Banana")
    val itemCounts = items.groupBy { it }.mapValues { it.value.size }
    println("Item Counts: $itemCounts")

    val numbers = setOf(1, 2, 3, 4, 5)
    val doubled = numbers.map { it * 2 }
    println("Doubled Set: $doubled")

    val map = mapOf(1 to "One", 2 to "Two", 3 to "Three")
    val keys = map.keys.filter { it % 2 == 1 }
    println("Filtered Keys: $keys")
}
```

#### **Deliverable**
- A program demonstrating operations on `List`, `Set`, and `Map`.

---

### **5. Null Safety: Safe Calls, Elvis Operator, and Non-Null Assertions**

#### **Objective**
- Handle null values using safe call (`?.`), Elvis operator (`?:`), and non-null assertions (`!!`).
- Avoid runtime exceptions by applying null safety practices.

#### **Task 4: Implement Null Safety**

1. Create a program that reads nullable data and applies null safety operators.
2. Handle null values gracefully using Kotlin’s null safety features.

#### **Example Code**
```kotlin
fun main() {
    val name: String? = null

    // Safe Call
    println("Name Length: ${name?.length}")

    // Elvis Operator
    val defaultName = name ?: "Unknown"
    println("Name: $defaultName")

    // Non-Null Assertion
    try {
        println("Forcing Non-Null: ${name!!.length}")
    } catch (e: NullPointerException) {
        println("Caught NullPointerException")
    }
}
```

#### **Deliverable**
- A Kotlin program showcasing null safety practices.

---

### **6. Assignments**

#### **Assignment 1**: Lambda Functions
- Write lambda expressions to:
  - Calculate factorial.
  - Find the longest string in a list.

#### **Assignment 2**: Higher-Order Functions
- Create a higher-order function that takes a list and a lambda to transform its elements.

#### **Assignment 3**: Functional Collections
- Write a program to:
  - Group people by age from a list of `Person(name: String, age: Int)`.
  - Find the total sum of numbers in a `List` using `reduce`.

#### **Assignment 4**: Null Safety
- Create a program to safely read user input and display a default value if the input is null or blank.

---

### **7. Scenario-Based Questions**

1. **Scenario:** How can you use a higher-order function to process a list of integers and return only the even numbers?
2. **Scenario:** Given a nullable list of strings, how would you safely iterate through the list and print each element?
3. **Scenario:** Write a function that takes a `Map<Int, String>` and returns a filtered map containing only entries where the key is even.
4. **Scenario:** How would you design a lambda expression to calculate the sum of squares of numbers in a list?

---

### **8. Best Practices Summary**

- **Lambda Expressions**: Keep lambda expressions concise and readable.
- **Higher-Order Functions**: Use higher-order functions to simplify code and reduce boilerplate.
- **Functional Collections**: Leverage Kotlin’s rich collection API for cleaner and efficient code.
- **Null Safety**: Always prefer safe calls and the Elvis operator over non-null assertions.

This lab ensures a hands-on understanding of functional programming concepts in Kotlin through practical tasks, assignments, and scenario-based questions while adhering to industry best practices.

