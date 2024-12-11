# **Real-Time Collaboration Backend API**

Welcome to the **Real-Time Collaboration Backend API** project! This is a scalable, microservices-based backend designed for a real-time collaborative document editor. The system supports user authentication, document management, real-time collaboration, and version control, built with modern technologies and best practices.

---

## **Features**

- **Authentication & Authorization**  
  - JWT-based authentication.  
  - Role-based access control (Admin, Editor, Viewer).  

- **Document Management**  
  - Create, read, update, and delete documents.  
  - Support for version history and rollbacks.  

- **Real-Time Collaboration**  
  - WebSocket-based real-time updates.  
  - Conflict resolution using Operational Transformation (OT) or CRDTs.  

- **User Presence Tracking**  
  - Track and broadcast online status of users in real time.  

- **Flexible Data Querying**  
  - REST and GraphQL endpoints for document and user operations.  

---
## Prerequisites

Before you begin, ensure you have the following installed on your system:

- [Git](https://git-scm.com/)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

---
## Cloning the Repository

To clone the repository and get started:

1. Clone the repository using Git:

   ```bash
   git clone https://github.com/Michael233ctrl/real-time-collaboration.git
   cd real-time-collaboration
   
2. Create a file with environment variables called `.env.local` in the `/infra/env` directory

    #### Example `.env` File Structure
    ```plaintext
    # User Configuration
    FIRST_SUPERUSER=superuser@example.com
    FIRST_SUPERUSER_PASSWORD=example_password
    
    # MongoDB Configuration
    MONGO_REPLICA_SET=0
    MONGO_REPLICA_SET_NAME=rs0
    MONGO_DATABASE_URI=mongodb://username:password@mongo:27017/database_name?authSource=admin
    MONGO_DATABASE=database_name
    MONGO_INITDB_ROOT_USERNAME=username
    MONGO_INITDB_ROOT_PASSWORD=password
    
    # JWT Configuration
    JWT_ALGORITHM=HS512
    SECRET_KEY=your_secret_key
    TOTP_SECRET_KEY=your_totp_secret_key
    ACCESS_TOKEN_EXPIRE_SECONDS=2592000
    REFRESH_TOKEN_EXPIRE_SECONDS=2592000
    
    # Auth Service Configuration
    AUTH_PROJECT_NAME=Authenticator
    AUTH_SERVER_NAME=authenticator
    AUTH_API_V1_STR=/api/v1
    BACKEND_CORS_ORIGINS=["http://localhost", "http://frontend.com"]
    AUTH_URL=http://localhost:9020/api/v1/login/oauth
    
    # Document Management Configuration
    DOCS_PROJECT_NAME=DocumentManagement
    DOCS_SERVER_NAME=document-management
    DOCS_API_V1_STR=/api/v1

---
## Starting Services

To start all services:

1. Open your terminal and navigate to the `infra/` directory:

   ```bash
   cd infra/
   
2. Run the following command:
    ```bash
   make build && make start
   
3. Verify that all services are running by listing the containers:
    ```bash 
   make show_containers