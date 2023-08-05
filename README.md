# Taskify - Task Management Web Application

Taskify is a Task Management web application built with Angular for the frontend and ASP.NET Core microservices for the backend. The application allows users to create, manage, and prioritize tasks.

## Architecture

Taskify follows a microservices architecture with separate microservices for authentication and tasks. Both microservices share a centralized PostgreSQL database.

### Frontend - Angular

- The frontend is developed with Angular, providing an intuitive user interface for task management and user authentication.

### Backend Microservices

1. **Authentication Microservice**

   - Handles user registration, login, and authentication using JWT (JSON Web Tokens).
   - Ensures secure user authentication and token validation.

2. **Tasks Microservice**
   - Manages CRUD operations for tasks.
   - Associates tasks with users using JWT tokens for authentication.

### Database - PostgreSQL

- Utilizes a centralized PostgreSQL database to store user authentication data and task information.

## Prerequisites

- Node.js and npm installed.
- ASP.NET Core SDK installed.
- PostgreSQL database set up and running.

## Getting Started

1. Clone the repository and navigate to the project directory.

2. **Frontend Setup:**

   ```bash
   cd frontend
   npm install
   ```

3. **BackendSetup:**

   ```bash
   cd backend/authentication
   dotnet restore

   cd ../tasks
   dotnet restore

   ```

4. **Database Configuration:**

   - Create a PostgreSQL database and update the connection string in the respective microservice's configuration.

5. **Running the Application:**  
    a, Frontend:

   ```bash
   cd frontend
   ng serve
   ```

   b, Backend:

   ```bash
    cd backend/authentication
    dotnet run
    cd ../tasks
    dotnet run
   ```

6. **Access the Application:**

   - Open your web browser and visit http://localhost:4200 to access the Taskify application.

## Deployment - Amazon ECS with Fargate

To deploy Taskify to production, follow these steps:

1. Build Docker images for both the authentication and tasks microservices.

2. Push the Docker images to a container registry like Amazon ECR (Elastic Container Registry).

3. Set up an Amazon ECS cluster with Fargate launch type.

4. Create task definitions for both microservices, specifying the Docker images and required configurations.

5. Configure an Application Load Balancer (ALB) to distribute traffic between microservices.

6. Deploy the task definitions to ECS with Fargate.

This deployment approach ensures scalability, fault tolerance, and easy management of the Taskify application. It allows the backend microservices to run in a containerized environment and automatically handles scaling and load balancing, making it suitable for production deployments.

## Contributing

If you'd like to contribute to Taskify, please follow our [Contribution Guidelines](CONTRIBUTING.md). We welcome bug reports, feature requests, and pull requests!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
