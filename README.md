# WhatsApp Clone - Spring Boot Application

## 📌 Overview
This is a WhatsApp Clone built using **Spring Boot**, **WebSockets**, and **Spring Security**. The application runs with **PostgreSQL** and **Keycloak** for authentication and authorization. To simplify setup, a `docker-compose.yml` file is provided to manage services.

## 🛠️ Technologies Used
- **Spring Boot** (Backend framework)
- **WebSockets** (Real-time messaging)
- **Spring Security** (Authentication & Authorization)
- **Keycloak** (Identity and Access Management)
- **PostgresSQL** (Database)
- **Docker Compose** (Service orchestration)

---

## 🚀 Getting Started

### 1️⃣ Prerequisites
Ensure you have the following installed:
- [Docker & Docker Compose](https://docs.docker.com/get-docker/)
- [Java 17+](https://adoptopenjdk.net/)
- [Maven](https://maven.apache.org/install.html)

### 2️⃣ Configure Environment Variables
Create a `.env` file in the root directory and set the necessary environment variables:

```env
# PostgreSQL Configuration
POSTGRES_DB=whatsapp_clone
POSTGRES_USER=your_user
POSTGRES_PASSWORD=your_password
PGDATA=/var/lib/postgresql/data

# Keycloak Configuration
KEYCLOAK_ADMIN=admin
KEYCLOAK_ADMIN_PASSWORD=admin

# Application Configuration
DB_HOST=postgres
DB_PORT=5432
DB_NAME=whatsapp_clone
DB_USERNAME=your_user
DB_PASSWORD=your_password
OAUTH2_JWT_ISSUER_URI=http://localhost:9090/realms/whatsapp-clone
SERVLET_MULTIPART_MAX_FILE_SIZE=10MB
FRONTEND_URL=http://localhost:3000
```

### 3️⃣ Run the Application with Docker Compose
Run the following command to start all services:

```sh
docker-compose up -d
```
This will spin up:
- PostgresSQL database
- Keycloak authentication server
- The Spring Boot backend

### 4️⃣ Access the Application
- **Spring Boot API**: http://localhost:8081
- **Keycloak Admin Console**: http://localhost:8080/auth (default admin: `admin/admin`)
- **Database**: Exposed on port `5432`

### 5️⃣ Stop Services
To stop and remove all containers, run:
```sh
docker-compose down
```

---

## 🔒 Authentication & Security
This application uses **Spring Security** with **OAuth2** and **JWT** tokens. Keycloak manages user authentication. Make sure you configure the **Keycloak realm**, **clients**, and **roles** accordingly before running the app.

---

## 🛠️ Development
### Run the Backend Locally (Without Docker)
1. Start PostgresSQL and Keycloak manually.
2. Configure `application.properties` with the correct database and Keycloak settings.
3. Run:
   ```sh
   mvn spring-boot:run
   ```

---


## API Documentation
This application uses **Swagger** for API documentation. 
Once the application is running, you can access the Swagger UI at:
```
http://localhost:8081/swagger-ui/index.html
```

**Swagger** provides a user-friendly interface to explore and test the API endpoints.


---


## 📜 License
This project is licensed under the [MIT License](LICENSE).
---

## 📩 Contact
For any questions or contributions, feel free to open an issue or submit a pull request!

