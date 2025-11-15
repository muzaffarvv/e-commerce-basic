# e-commerce (Console-based Java Project)

This is a small educational **Console E-Commerce Application** built in **Java 17** using  
**OOP, Streams API, Functional Interfaces, JSON/XML storage**, and clean layered architecture.  
The project was developed as part of the Java PDP course (Module 4).

---

## 🚀 Features

- User management (register, login, authentication)
- Products CRUD (seller based)
- Categories CRUD
- Shopping cart system
- Order creation using **OrderBuilder**
- JSON/XML file-based data persistence
- Renderer classes for clean console output
- Utility classes for file operations and cart calculations

---

## 🧱 Project Architecture

```
src/
 ├── abstraction/
 │     └── OrderBuilder
 ├── base/
 │     ├── BaseModel
 │     └── BaseService
 ├── dao/
 │     ├── carts.json
 │     ├── categories.xml
 │     ├── orders.json
 │     ├── products.json
 │     └── users.xml
 ├── exception/
 │     ├── InvalidCartException
 │     ├── InvalidCartItemException
 │     ├── InvalidCategoryException
 │     ├── InvalidOrderException
 │     ├── InvalidProductException
 │     └── InvalidUserException
 ├── function/
 │     └── CheckedBiConsumer
 ├── model/
 │     ├── Cart
 │     ├── Category
 │     ├── Order
 │     ├── Product
 │     └── User
 ├── other/
 │     └── interface-prototype.txt
 ├── record/
 │     └── UserInfo
 ├── renderer/
 │     ├── CartRenderer
 │     ├── CategoryRenderer
 │     ├── OrderRenderer
 │     ├── ProductRenderer
 │     └── UserRenderer
 ├── service/
 │     ├── CartService
 │     ├── CategoryService
 │     ├── OrderService
 │     ├── ProductService
 │     └── UserService
 ├── util/
 │     ├── CartUtils
 │     └── FileUtils
 ├── ConsoleInterface
 └── DevControl
```

---

## 🗄 Data Storage

The project uses **file-based storage**, no database required.

- `JSON` → carts, orders, products  
- `XML` → users, categories  

Utilities used:

- `FileUtils.writeToJson()`
- `FileUtils.writeToXml()`
- `FileUtils.readFromJson()`
- `FileUtils.readFromXml()`

---

## 🧩 Core Components

### **BaseModel**
- Generates UUID  
- Tracks `createdAt`, `updatedAt`  
- Has `active` flag for soft-delete  
- Used by all domain models

### **BaseService<T>**
Generic CRUD interface:

- add(T t)
- get(UUID id)
- getAll()
- update(UUID id, T t)
- remove(UUID id)
- clearAndSave()

### **OrderBuilder**
Builds new orders from a cart:

- Converts Cart → Order
- Builds BoughtItem list
- Applies functional interfaces for seller/product lookup
- Calculates grand total via `CartUtils`

---

## 🖥 How to Run

1. Ensure Java 17 is installed  
2. Open terminal in project root  
3. Run:

```bash
javac -d out $(find src -name "*.java")
java -cp out uz.pdp.ConsoleInterface
```

---

## 📦 Requirements

- Java **17**
- Jackson Databind / Jackson XML
- Lombok

---

## 📘 Purpose

This project demonstrates:

- Clean OOP design  
- Working with Streams API  
- File I/O with JSON/XML  
- Builder pattern  
- Layered architecture  
- Console UI rendering  

Perfect for students practicing **Java Core + File I/O + Streams**.

---

## 🔖 License
This project was created for educational purposes under the Java PDP course module.

