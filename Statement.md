# Problem Statement & System Design Specification

## 1. Problem Statement
In high-throughput e-commerce scenarios such as flash sales, concurrent order submissions frequently cause race conditions on shared inventory resources. Unsynchronized state updates lead to overselling (negative inventory levels), data inconsistency, and corrupted order records. 

The objective is to design a multithreaded inventory management and order processing system that guarantees data integrity under heavy thread contention, supports heterogeneous product catalog types, ensures fail-safe persistence, and outputs clean auditing logs.

## 2. System Architecture & Core Requirements
- **Thread Safety & Race-Condition Prevention**: Protect critical inventory mutation points through synchronized object monitors and concurrent collection structures.
- **Object-Oriented Domain Modeling**: Leverage abstraction and inheritance to handle distinct billing rules (e.g., physical shipping fee calculations vs. zero-shipping digital goods).
- **Graceful Error Handling**: Prevent application crashes via checked exceptions for domain failures (`OutOfStockException`, `ProductNotFoundException`).
- **Resilient Persistence Engine**: Interface with a persistent relational storage layer via JDBC, while offering automatic runtime fallback to in-memory processing if database drivers are unavailable.
- **File System Auditing**: Provide buffered I/O stream generation for invoice and reporting records.
