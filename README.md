# E-Commerce Inventory and Order Management System

## Project Overview
The **E-Commerce Inventory and Order Management System** is a console-based Java application developed for the VITyarthi Build Your Own Project (BYOP) evaluation. It demonstrates object-oriented programming, inheritance, abstraction, polymorphism, exception handling, collections, file handling, and multithreading.

The system allows a user to:
- View available products and stock.
- Place customer orders.
- Calculate order totals for physical and digital products.
- Handle invalid product IDs and insufficient stock.
- Simulate a flash sale using multiple threads.
- Export completed order invoices to a text file.

## Problem Statement
Small e-commerce systems need a simple way to maintain product stock, process customer orders, prevent overselling, and generate order records. This project provides a lightweight Java-based solution that demonstrates these operations through a command-line interface.

## Objectives
1. Build a modular Java application using OOP principles.
2. Maintain product details and inventory quantities.
3. Process orders with validation and custom exceptions.
4. Demonstrate inheritance through physical and digital products.
5. Demonstrate thread-safe stock reduction during a flash sale.
6. Export invoice details for completed orders.

## Major Functional Modules
### 1. Inventory Management
- Add products.
- Display product ID, category, name, price, and stock.
- Search products by product ID.

### 2. Order Processing
- Accept customer name, product ID, and quantity.
- Validate input.
- Reduce stock after a successful order.
- Generate an order ID and invoice details.

### 3. Flash Sale Simulation
- Creates multiple buyer tasks.
- Uses an ExecutorService thread pool.
- Ensures stock is not reduced below zero.
- Reports successful and failed buyers.

### 4. Invoice Export
- Writes completed orders to `invoices_report.txt`.
- Uses buffered file writing.
- Handles file I/O errors.

## Technologies Used
- Java
- Java Collections Framework
- Exception Handling
- Multithreading and ExecutorService
- File Handling
- VS Code / IntelliJ IDEA / Eclipse
- Git and GitHub

## Project Structure
```text
ECommerceVITyarthiProject/
├── README.md
├── statement.md
├── .gitignore
├── src/
│   └── ecommerce/
│       ├── Product.java
│       ├── PhysicalProduct.java
│       ├── DigitalProduct.java
│       ├── Order.java
│       ├── InventoryService.java
│       ├── FlashSaleSimulator.java
│       ├── OutOfStockException.java
│       ├── ProductNotFoundException.java
│       └── ECommerceOrderApp.java
└── docs/
    ├── REPORT_CONTENT.md
    └── diagrams.md
```

## How to Run

### Requirements
- JDK 17 or later
- VS Code or any Java IDE

### Compile
Open the project root in the terminal and run:

```bash
javac -d out src/ecommerce/*.java
```

### Run
```bash
java -cp out ecommerce.ECommerceOrderApp
```

## Menu Options
```text
1. View Available Inventory
2. Place Customer Order
3. Run Flash Sale Simulation
4. Export Invoices
5. Exit
```

## Example Test Cases

| Test Case | Input/Action | Expected Result |
|---|---|---|
| View inventory | Select 1 | Product list is displayed |
| Valid order | P102, quantity 2 | Order accepted and stock reduced |
| Invalid product | P999 | ProductNotFoundException message |
| Excess quantity | Quantity greater than stock | OutOfStockException message |
| Negative quantity | -2 | Validation error |
| Flash sale | Select 3 | Only available stock is sold |
| Export invoices | Select 4 | `invoices_report.txt` is created |

## Non-Functional Requirements
- **Usability:** Simple menu-driven interface.
- **Reliability:** Custom exceptions and input validation.
- **Performance:** Thread pool for concurrent flash-sale requests.
- **Maintainability:** Separate classes with clear responsibilities.
- **Resource efficiency:** Uses collections and buffered file writing.
- **Error handling:** Invalid input and order failures are reported to the user.

## OOP Concepts Demonstrated
- **Abstraction:** `Product` is an abstract class.
- **Encapsulation:** Product fields are private and accessed through methods.
- **Inheritance:** `PhysicalProduct` and `DigitalProduct` extend `Product`.
- **Polymorphism:** `calculateTotalCost()` is overridden.
- **Constructor:** Initializes product and order objects.
- **Exception handling:** Custom checked exceptions and try-catch blocks.
- **Multithreading:** `ExecutorService` runs concurrent buyer tasks.

## Limitations
- Data is stored in memory during execution.
- The current version does not include login, payment gateway, GUI, or online deployment.
- Invoice data is exported to a text file instead of a full database.

## Future Enhancements
- Add MySQL/SQLite database storage.
- Add a graphical user interface using JavaFX.
- Add customer login and admin login.
- Add payment simulation.
- Add search, update, and delete product operations.
- Add JUnit unit tests.
- Deploy as a web application.

## Author
**Name:** _ATHARVA TYAGI_________________________  
**Registration Number:** _____25BAI10133_____________________  
**Course:** Programming in Java  
**Institution:** VIT Bhopal University  
**Academic Year:** 2026–2027
