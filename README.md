# Bargo

Bargo is a shipment tracking and delivery platform written in Java.

A package can travel through several cities, carriers and transportation networks before reaching its destination. For customers, it's one shipment, but tracking information is often scattered across different systems.

Bargo aims to bring that journey together, from choosing a shipping option and booking a courier to tracking the package and communicating with the person delivering it.

## Technology Stack

- **Language:** Java 25
- **Framework:** Spring Boot, Spring Modulith
- **Build System:** Gradle (Kotlin DSL)
- **Database:** PostgreSQL, jOOQ, Flyway
- **Messaging:** Apache Kafka (planned)
- **Testing:** JUnit, Testcontainers, ArchUnit

## Architecture

Bargo starts as a modular monolith with Hexagonal Architecture inside each application module. Modules will be extracted into independently deployable microservices where domain and operational requirements justify it.

## Project Management

- [GitHub Project](https://github.com/users/Amir-Golmoradi/projects/8)
- [Milestones](https://github.com/Amir-Golmoradi/Bargo/milestones)
- [Issues](https://github.com/Amir-Golmoradi/Bargo/issues)
- [Releases](https://github.com/Amir-Golmoradi/Bargo/releases)

The [first milestone, v0.1.0](https://github.com/Amir-Golmoradi/Bargo/milestone/1), focuses on package registration, integration with a simulated carrier, tracking event persistence, and shipment status and history retrieval. Duplicate events, delayed updates and carrier failures must be handled without compromising tracking accuracy.

## Git Strategy

- Trunk-based development
- Short-lived branches (`amg-<description>`)
- Pull requests with required CI checks
- Squash merging
- Semantic Versioning

## CI/CD

- **GitHub Actions:** Build, testing and image publishing
- **Docker:** Application containerization
- **GHCR:** Container registry
- **Minikube:** Local Kubernetes development and testing
- **Argo CD:** GitOps-based continuous deployment

## Deployment Strategy

Deployment is incremental and release-driven. Each release will be tested, packaged as a versioned container image and published to GHCR. Kubernetes manifests are updated through Git, and Argo CD synchronizes the target environment.

Small releases will be deployed throughout development rather than waiting for the entire milestone to be complete. The production Kubernetes environment has yet to be selected.

## Status

Early development. The first release is v0.1.0.
