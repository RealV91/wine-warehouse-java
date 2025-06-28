
# 🍷 Wine Warehouse Management System (Java SE)

[![Java](https://img.shields.io/badge/Java-SE%2011+-red)]()
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20Mac-blue)]()
[![License](https://img.shields.io/badge/License-MIT-green.svg)]()
[![Build](https://img.shields.io/badge/Build-Passed-brightgreen.svg)]()
[![Made by](https://img.shields.io/badge/Made%20by-Alessio%20Vautero-blueviolet)]()

This project is my final assignment for the Object-Oriented Programming (OOP) course. The goal was to apply core Java SE concepts including OOP principles, required design patterns, secure coding practices, and technologies like Java I/O, Logging, Collections, and JUnit testing.

It simulates a **warehouse for wine bottles**, where the system tracks:
- **entry orders**: wines arriving at the warehouse
- **exit orders**: wines shipped to customers
- **return orders**: wines that come back (e.g. failed delivery)

---

## 🔐 Application Security (Important Focus)
Security was a **top priority** throughout the development, as strongly emphasized during the course. The project includes:

- ✅ **Exception shielding**: all business logic (e.g., order execution) is protected using `try-catch` blocks.
- ✅ **No crashes on invalid input**: e.g., trying to remove more wine than available will log a warning, not crash.
- ✅ **Logging**: all actions are written to `warehouse.log` using `java.util.logging`.
- ✅ **No hardcoded secrets**: there are no credentials or exposed sensitive data.
- ✅ **Sanitized I/O**: files are handled with care, using `BufferedWriter` with resource closing, avoiding injection or leaks.

---

## ✅ Features Implemented
- Register wines in the warehouse by code, name, and quantity
- Process three types of orders: `Entry`, `Exit`, `Return`
- Support grouped orders via Composite pattern
- Save inventory to `inventory.csv`
- List and iterate through order history
- Run tests via JUnit

---

## 👨‍🏫 Object-Oriented Programming Concepts
This project demonstrates key **OOP principles**:

| Concept             | Description |
|---------------------|-------------|
| **Abstraction**     | `Order` interface hides implementation details of order types |
| **Encapsulation**   | All class fields are private with public getters/setters |
| **Inheritance**     | Not directly used but could be extended from an abstract `BaseOrder` class |
| **Polymorphism**    | All orders (`Entry`, `Exit`, `Return`, `Composite`) implement the `Order` interface |

---

## 🧠 Design Patterns Implemented
| Pattern              | Role in this project |
|---------------------|----------------------|
| **Factory**         | `OrderFactory` creates different order objects |
| **Composite**       | `OrderComposite` groups multiple orders in one container |
| **Iterator**        | `OrderIterator` provides clean iteration over orders |
| **Exception Shielding** | Used in `Warehouse` to avoid exposing internal errors to the user |

---

## 🛠️ Technologies Used
- **Java Collections** (`Map`, `List`)
- **Java Generics**
- **Java I/O**
- **Logging API**
- **JUnit 5**

---

## ▶️ How to Compile and Run

### Requirements
- Java 11+

### Compile the project
```bash
javac -d bin src/**/*.java
```

### Run the application
```bash
java -cp bin Main
```

### Run JUnit Tests
```bash
javac -d bin -cp .:junit-platform-console-standalone.jar test/*.java
java -jar junit-platform-console-standalone.jar --class-path bin --scan-class-path
```

---

## 📁 Project Structure
```
wine-warehouse/
├── src/
│   ├── model/
│   ├── factory/
│   ├── service/
│   ├── util/
├── test/
├── README.md
├── inventory.csv
├── warehouse.log
```

---

## 📐 UML Class Diagram (Simplified)
```
Main
├── Warehouse
│   ├── Map<String, Wine>
│   ├── List<Order>
├── Wine
├── Order (interface)
│   ├── EntryOrder
│   ├── ExitOrder
│   ├── ReturnOrder
│   └── OrderComposite
├── OrderFactory
├── OrderIterator
├── LogUtil
```

---

## 🔬 Unit Tests (JUnit)
Tested with **JUnit 5**, includes:
- `OrderTest.java`
- `WarehouseTest.java`

---

## 👨‍🎓 Author
**Alessio Vautero** – Java SE Course 2024/2025 Final Project  
GitHub Repo: https://github.com/RealV91/wine-warehouse-java
