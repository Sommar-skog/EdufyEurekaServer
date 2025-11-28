# EdufyEurekaServer
[![Java](https://img.shields.io/badge/Java-21-blue.svg)](https://www.oracle.com/java/technologies/javase/jdk21-archive-downloads.html)  
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.5.7-brightgreen.svg)](https://spring.io/projects/spring-boot)

## 🛰️ Overview
EdufyEurekaServer provides **service discovery** for the entire Edufy microservice ecosystem.  
All media services (Video, Music, Pod) as well as supporting services (Creator, Genre, Thumb, Utility, User) register themselves to this server.

Eureka enables:
- Service lookup
- Load balancing support (via Spring Cloud LoadBalancer)
- Centralized service registry
- Simplified communication between microservices

This service contains **no business logic** and exposes **no API endpoints**.  
It only hosts the Eureka dashboard and service registry.

---

## 🧩 Related Projects

### Organization
- [EdufyProjects](https://github.com/EudfyProjects)

### Connections
- [Edufy-infra](https://github.com/EudfyProjects/Edufy-infra) – Docker-compose + init.db
- [EdufyEurekaServer](https://github.com/Sommar-skog/EdufyEurekaServer) – Service discovery
- [Gateway](https://github.com/SaraSnail/EdufyGateway) – Entry point for all requests
- [EdufyUser](https://github.com/Jamtgard/EdufyUser) – User service
- [EdufyKeycloak](https://github.com/Sommar-skog/EdufyKeycloak) – Auth pipeline

### Media connections
- [EdufyCreator](https://github.com/Sommar-skog/EdufyCreator) – Creators
- [EdufyGenre](https://github.com/a-westerberg/EdufyGenre) – Genres
- [EdufyThumb](https://github.com/a-westerberg/EdufyThumb) – Thumbs up/down records
- [EdufyUtility](https://github.com/a-westerberg/EdufyUtility) – Placeholder for algorithms

### Media Services
- [EdufyMusic](https://github.com/Jamtgard/EdufyMusic) - Music
- [EdufyVideo](https://github.com/Sommar-skog/EdufyVideo) - Video
- [EdufyPod](https://github.com/SaraSnail/EdufyPod) - Pod

---


## 🚀 Tech Stack

- **Language:** Java 21
- **Build Tool:** Maven
- **Framework:** Spring Boot 3.5.7
    - Spring Cloud Netflix Eureka Server
- **Security:**
    - (None — Eureka dashboard is not protected in dev mode)

---

## 🏁 Getting Started

### Prerequisites
- Java 21
- Maven
- Docker

---

### 🔌 Ports

- **Eureka:** `8761`
    - Dashboard: `http://localhost:8761/`
    - All services register here automatically

---

## 🔒 Authentication & Roles

This service does **not** use OAuth2 or Keycloak.  
It has **no protected endpoints** and **no user roles**, since its only purpose is service discovery.

---

## 📚 API Endpoints
Eureka Server provides **no REST API** for external clients beyond its own internal registry mechanisms.

There are **no controllers** or **public endpoints** in this project.

---

## 🐳 Docker
- Eureka Server is started through `docker-compose.yml` in **Edufy-infra**
- Runs inside the shared `edufy-network`
- All microservices depend on this container being up

---
## ✨ Current Status
Edufy Eureka Server is fully functional and forms a stable core of the Edufy ecosystem.  
It requires no additional development unless the team decides to add:
- Security
- Clustering (Eureka peers)
- Custom metadata handling

---

## 📌 Notes
Eureka Server must always be started **before** any media or support service — otherwise they cannot register.

---

## ✨ Credits
README created by **Sommar-skog**, aligned with the Edufy project documentation standard.
> _README made by [Sommar-skog](https://github.com/Sommar-skog)_