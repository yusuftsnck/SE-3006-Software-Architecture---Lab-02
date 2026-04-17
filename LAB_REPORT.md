# Lab 02 Report: Modular Monolith Built with Pure Java
Course: SE 3006 - Software Architectur
Yusuf Şaban Tosuncuk

## Objective
The primary goal of this laboratory was to refactor a tightly coupled Layered Architecture into a Modular Monolith. The system was divided into distinct vertical business domains (catalog and orders) to establish clear module boundaries and eliminate direct database sharing.

## Key Architectural Concepts Applied
Information Hiding: We utilized Java's package-private (default) access modifier. Internal domain components like ProductRepository, Product, and CatalogServiceImpl were hidden from outside modules to prevent unauthorized access and tight coupling.

## Interface-Driven Communication (APIs): 
Modules now interact exclusively through public interfaces. The orders module has no knowledge of the internal structures of the catalog; it communicates solely via the public CatalogService interface to reduce stock.

## Factory Pattern & Dependency Injection: 
We implemented CatalogFactory and OrdersFactory. These public factories handle the internal wiring of dependencies (via constructor injection) and return only the public interfaces to the outside world, acting as the sole entry points for the modules.

## Conclusion
By enforcing strict access modifiers and utilizing factories for dependency injection, we successfully decoupled the system. The orders module can no longer directly manipulate the catalog database. This ensures strict modular boundaries, better maintainability, and true modularity within a monolithic architecture.