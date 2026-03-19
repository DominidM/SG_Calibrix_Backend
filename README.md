# SG_Calibrix_Backend

Backend system built with a microservices architecture using Spring Boot, Java, and Maven. Each service is independently deployable and communicates through an API Gateway.

---

## 🧱 Tech Stack

| Technology | Version | Purpose |
|---|---|---|
| Java | 21 | Programming language |
| Spring Boot | 4.0.4 | Application framework |
| Maven | Latest | Dependency management & build tool |
| PostgreSQL | Latest | Relational database |
| Spring Cloud Gateway | Latest | API Gateway & routing |
| Spring Cloud Eureka | Latest | Service discovery |
| Spring Security + JWT | Latest | Authentication & authorization |

---

## 📦 Microservices

| Service | Description |
|---|---|
| `discovery-service` | Eureka Server — service registry |
| `api-gateway` | Entry point — routing & JWT filter |
| `auth-service` | Authentication & token management |
| *(more services)* | *(add as the project grows)* |

---

## 🗂️ Project Structure

```
SG_Calibrix_Backend/
├── discovery-service/
│   ├── src/
│   └── pom.xml
├── api-gateway/
│   ├── src/
│   └── pom.xml
├── auth-service/
│   ├── src/
│   └── pom.xml
└── README.md
```

---

## ⚙️ Prerequisites

- Java 21
- Maven 3.9+
- PostgreSQL
- IDE (IntelliJ IDEA recommended)

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-org/SG_Calibrix_Backend.git
cd SG_Calibrix_Backend
```

### 2. Configure environment variables

Each service requires its own configuration. Copy the example file and fill in your values:

```bash
cp src/main/resources/application.example.properties src/main/resources/application.properties
```

> ⚠️ Never commit `application.properties` with real credentials.

### 3. Start the services in order

```bash
# 1. Discovery Service (Eureka)
cd discovery-service && mvn spring-boot:run

# 2. API Gateway
cd api-gateway && mvn spring-boot:run

# 3. Auth Service
cd auth-service && mvn spring-boot:run
```

---

## 📡 API Gateway

All requests go through the API Gateway. Default port: `8080`

```
http://localhost:8080/{service-route}/...
```

---

## 🔐 Authentication

This project uses **JWT (JSON Web Tokens)** for stateless authentication. Include the token in the `Authorization` header:

```
Authorization: Bearer <your_token>
```

---

## 🗃️ Database

Each microservice manages its own PostgreSQL database schema following the **Database per Service** pattern.

> Connection details must be set in each service's `application.properties` (not committed to the repository).

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch following the convention:
   ```
   feat/<service>/<short-description>
   ```
3. Commit your changes using [Conventional Commits](https://www.conventionalcommits.org/):
   ```
   feat(auth): add refresh token endpoint
   fix(gateway): fix CORS headers on preflight
   ```
4. Open a Pull Request to `develop`

---

## 📄 License

This project is private and proprietary. All rights reserved.