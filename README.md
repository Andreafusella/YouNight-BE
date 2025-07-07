# 🥂 YouNight Backend

Welcome to the backend system of **YouNight**, a platform designed to connect nightlife venues with their audience. This backend is built using a microservices architecture and exposes powerful APIs to manage events, posts, tickets, menus, drinks, and more.

## 🚀 Technologies

![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=for-the-badge&logo=rabbitmq&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)

---

## 🧠 Description

**YouNight Backend** is composed of two main microservices — `Core` and `Warehouse` — and a shared library called `Commons DTO`. The services communicate via **RabbitMQ**, and the system is designed to manage interactions between users and nightlife venues.

### 🧱 Architecture

- **Core**:
    - Exposes all REST APIs.
    - Handles authentication (with Keycloak and JWT).
    - Manages business logic and acts as an orchestrator.
    - Communicates with Warehouse via RabbitMQ.
    - Integrates with OpenAI, Firebase, and Geocoding APIs.

- **Warehouse**:
    - Handles storage, stock management, and all CRUD operations.
    - Listens to asynchronous events from Core.
    - Returns processed data through RabbitMQ.

- **Commons DTO**:
    - Shared module with all Data Transfer Objects.


## 👤 User Roles

### 🔹 Business User
- Create events
- Publish posts for events
- Add/manage tickets
- Define custom menus, drinks, and ingredients
- Track and manage stock via Warehouse

### 🔸 Customer User
- Browse event-related posts (similar to Instagram)
- Like and save events
- Purchase tickets
- Order drinks during an event
- Receive confirmation emails and push notifications via Firebase

---

## 🌐 External APIs

- **OpenAI**: Natural language processing for event search.
- **Firebase**: Push notifications and email handling.
- **Geocoding (e.g. OpenCage)**: Convert cities to coordinates and filter events by distance.

---