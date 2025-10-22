# Monolithic vs Microservice Architecture

This document provides a comprehensive overview of **Monolithic** and **Microservice** architectures, their types, advantages, disadvantages, and use-cases, useful for developers and for interview preparation.

---

## Table of Contents

1. [Overview](#overview)  
2. [Monolithic Architecture](#monolithic-architecture)  
   - [Definition](#definition)  
   - [Types](#types)  
   - [Advantages](#advantages)  
   - [Disadvantages](#disadvantages)  
   - [When to Use](#when-to-use)  
3. [Microservice Architecture](#microservice-architecture)  
   - [Definition](#definition-1)  
   - [Types](#types-1)  
   - [Advantages](#advantages-1)  
   - [Disadvantages](#disadvantages-1)  
   - [When to Use](#when-to-use-1)  
4. [Monolithic vs Microservices](#monolithic-vs-microservices)  
5. [Key Interview Questions](#key-interview-questions)  
6. [References](#references)

---

## Overview

Software architecture determines how an application is structured and how components interact. The **two most popular approaches** are:

- **Monolithic Architecture**: The traditional, single-tiered software architecture where all components are integrated into a single application.  
- **Microservice Architecture**: A modern approach where the application is divided into independent, loosely-coupled services, each responsible for a specific functionality.

---

## Monolithic Architecture

### Definition
A **Monolithic Architecture** is an application built as a single, unified unit. All modules (UI, business logic, data access) are part of one codebase.

### Types
1. **Layered Monolithic**  
   - Components are divided into logical layers like Presentation, Business Logic, and Data Access.  
   - Each layer interacts with the next but all are deployed together.

2. **Modular Monolithic**  
   - Components are organized as independent modules within the same codebase.  
   - Promotes modularity but deployment remains single.

### Advantages
- Simple to develop, test, and deploy initially.  
- Easier to debug and monitor.  
- Less operational overhead (single deployment).

### Disadvantages
- Hard to scale selectively; scaling requires scaling the entire application.  
- Changes in one module may affect the entire system.  
- Long-term maintenance can be difficult for large applications.

### When to Use
- Small to medium-sized applications.  
- Teams with limited resources.  
- Projects where simplicity and speed of development are prioritized.

---

## Microservice Architecture

### Definition
A **Microservice Architecture** divides an application into small, independent services that communicate over APIs (HTTP/REST, gRPC, messaging). Each service has its own database and deployment lifecycle.

### Types
1. **API-first Microservices**  
   - Services expose well-defined APIs.  
   - Focus on interoperability and service contracts.

2. **Event-driven Microservices**  
   - Services communicate via events (message queues, brokers).  
   - Good for asynchronous, decoupled systems.

3. **Database-per-service**  
   - Each microservice manages its own database.  
   - Promotes independence but requires careful data management.

### Advantages
- Independent development and deployment.  
- Better scalability (scale services individually).  
- Fault isolation; one service failure doesn’t crash the entire app.  
- Supports polyglot programming (different languages/tech per service).

### Disadvantages
- Complex to develop, deploy, and monitor.  
- Requires service discovery, API management, and distributed logging.  
- Inter-service communication can increase latency.

### When to Use
- Large, complex applications with multiple teams.  
- Applications requiring high scalability and flexibility.  
- Projects that need frequent updates and continuous deployment.

---

## Monolithic vs Microservices

| Feature                     | Monolithic                          | Microservices                         |
|-------------------------------|------------------------------------|--------------------------------------|
| Codebase                     | Single codebase                    | Multiple independent services        |
| Deployment                   | Single deployment                  | Independent deployments per service  |
| Scalability                  | Whole application                  | Service-level scaling                 |
| Fault Isolation              | Low                                 | High                                  |
| Development Speed            | Fast initially                      | Slower initially, faster later        |
| Complexity                   | Simple                              | Complex                               |
| Ideal For                    | Small to medium apps                 | Large, complex, evolving apps         |

---

## Key Interview Questions

1. What is Monolithic architecture and its drawbacks?  
2. Explain Microservices and its benefits.  
3. When should you choose Monolithic over Microservices and vice versa?  
4. What is the difference between Layered and Modular Monolithic?  
5. How do microservices communicate? (REST, gRPC, Messaging)  
6. How do you handle transactions across microservices?  
7. What are challenges in deploying microservices?  
8. How does scaling differ between Monolithic and Microservices?

---

## References

1. [Martin Fowler – Microservices](https://martinfowler.com/articles/microservices.html)  
2. [Microsoft – Monolithic vs Microservices](https://learn.microsoft.com/en-us/azure/architecture/guide/architecture-styles/monolithic)  
3. [Microservices.io](https://microservices.io/)  

---

