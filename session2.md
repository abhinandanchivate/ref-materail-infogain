### Hands-on Lab: Day 4 - Classes, Inheritance, Interfaces, and Encapsulation

---

### **Lab Overview**

In this lab, you will explore advanced OOP concepts in Kotlin, including classes, inheritance, interfaces, and encapsulation. Through hands-on tasks, you will implement real-world scenarios, work with complex source codes, and complete assignments to deepen your understanding of OOP design principles and best practices.

---

### **1. Lab Preparation**

#### **Prerequisites**
- Basic understanding of Kotlin programming.
- Experience with object-oriented programming concepts.
- IDE setup (e.g., IntelliJ IDEA or Eclipse).
- Kotlin runtime and build tools (Gradle or Maven).

#### **Tools Required**
- IntelliJ IDEA or Eclipse.
- Postman or cURL for testing REST APIs (if applicable).
- Local Kotlin development environment.

---

### **2. Classes and Objects: Properties, Methods**

#### **Objective**
- Understand the structure of classes, properties, and methods.
- Implement classes to model real-world scenarios.

#### **Task 1: Create a Class**

1. Open your IDE and create a new Kotlin project.
2. Define a class `Employee` with properties `id`, `name`, and `department`.
3. Add methods `promote(newDepartment: String)` and `displayDetails()` to update and display employee information.

#### **Example Code**
```kotlin
class Employee(val id: Int, var name: String, var department: String) {
    init {
        require(id > 0) { "ID must be positive" }
    }

    fun promote(newDepartment: String) {
        department = newDepartment
        println("Employee $name promoted to $newDepartment department.")
    }

    fun displayDetails() {
        println("ID: $id, Name: $name, Department: $department")
    }
}

fun main() {
    val emp = Employee(101, "Alice", "HR")
    emp.promote("IT")
    emp.displayDetails()
}
```

#### **Deliverable**
- A class `Employee` with tested methods.

---

### **3. Inheritance: Open Classes, Overriding Methods**

#### **Objective**
- Understand how inheritance allows code reuse.
- Implement a base class and subclasses with overridden methods.

#### **Task 2: Create a Class Hierarchy**

1. Define a base class `Vehicle` with properties `name` and `speed`.
2. Add a method `displayInfo()` to display vehicle details.
3. Create a subclass `Car` that overrides `displayInfo()` to add additional information.

#### **Example Code**
```kotlin
open class Vehicle(val name: String, val speed: Int) {
    open fun displayInfo() {
        println("Vehicle: $name, Speed: $speed km/h")
    }
}

class Car(name: String, speed: Int, val type: String) : Vehicle(name, speed) {
    override fun displayInfo() {
        super.displayInfo()
        println("Type: $type")
    }
}

fun main() {
    val car = Car("Sedan", 180, "Luxury")
    car.displayInfo()
}
```

#### **Deliverable**
- A base class `Vehicle` and a subclass `Car` with tested methods.

---

### **4. Interfaces: Implementation, Default Methods**

#### **Objective**
- Implement interfaces to define a contract for classes.
- Use default methods for common functionality.

#### **Task 3: Create an Interface**

1. Define an interface `Logger` with a default method `log(message: String)`.
2. Implement the interface in a class `FileLogger` with custom behavior.

#### **Example Code**
```kotlin
interface Logger {
    fun log(message: String) {
        println("Default Log: $message")
    }
}

class FileLogger : Logger {
    override fun log(message: String) {
        println("File Log: $message")
    }
}

fun main() {
    val logger: Logger = FileLogger()
    logger.log("System error occurred.")
}
```

#### **Deliverable**
- An interface `Logger` and an implementing class `FileLogger`.

---

### **5. Encapsulation: Visibility Modifiers**

#### **Objective**
- Restrict access to internal data using visibility modifiers.
- Provide controlled access through getters and setters.

#### **Task 4: Encapsulate a Class**

1. Define a class `BankAccount` with private property `balance`.
2. Add methods `deposit(amount: Double)` and `withdraw(amount: Double)` for controlled access.
3. Implement validation logic in methods.

#### **Example Code**
```kotlin
class BankAccount(private var balance: Double) {
    init {
        require(balance >= 0) { "Balance cannot be negative" }
    }

    fun deposit(amount: Double) {
        if (amount > 0) balance += amount
    }

    fun withdraw(amount: Double) {
        if (amount > 0 && amount <= balance) {
            balance -= amount
        } else {
            println("Insufficient funds or invalid amount!")
        }
    }

    fun getBalance(): Double = balance
}

fun main() {
    val account = BankAccount(1000.0)
    account.deposit(500.0)
    println("Current Balance: ${account.getBalance()}")
}
```

#### **Deliverable**
- A class `BankAccount` with encapsulated logic and tested methods.

---

### **6. Assignments**

#### **Assignment 1**: Class Hierarchy
- Implement a class hierarchy for a zoo:
  - Base class: `Animal` (properties: `name`, `species`).
  - Subclasses: `Mammal`, `Bird` (add unique methods and properties).

#### **Assignment 2**: Interface Implementation
- Create an interface `Drawable` with methods `draw()` and `resize()`.
- Implement it in classes `Circle` and `Rectangle`.

#### **Assignment 3**: Encapsulation
- Build a `Library` class that encapsulates `books` and provides methods to add, remove, and search books.

#### **Assignment 4**: Advanced Use Case
- Design a `Restaurant Management System` with classes for `Restaurant`, `Menu`, `Dish`, and `Order`.
  - Include an interface `Orderable`.

---

### **7. Scenario-Based Questions**

1. **Scenario:** You are building a microservice for processing payments. Would you use an interface or abstract class for defining payment methods? Justify your choice.
2. **Scenario:** A developer creates a class with public properties for user data. How would you redesign it to follow encapsulation principles?
3. **Scenario:** In an e-commerce application, explain how inheritance can handle product categories like `Electronics` and `Clothing`.
4. **Scenario:** Your class hierarchy is becoming too complex due to deep inheritance. What design principle would you apply?
5. **Scenario:** You need to add logging functionality to multiple unrelated classes. How would you achieve this in Kotlin?

---

### **8. Best Practices Summary**

- **Classes and Objects**: Adhere to SOLID principles.
- **Inheritance**: Prefer composition over inheritance when possible.
- **Interfaces**: Keep them focused and minimal.
- **Encapsulation**: Expose only what is necessary and validate inputs.

This lab ensures a hands-on understanding of OOP concepts through practical tasks and assignments while incorporating real-world scenarios and best practices.

