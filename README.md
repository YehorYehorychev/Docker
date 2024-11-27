# Dockerized Time Application

This repository contains a time application consisting of a **frontend**, **backend**, and **database**, fully containerized using Docker and orchestrated with Docker Compose.

## Project Structure

- **Frontend**: Built with Vue.js framework.
- **Backend**: Developed using Node.js and Express.js.
- **Database**: MySQL is used for data storage.
- **Adminer**: Provides an easy-to-use UI for managing the MySQL database.

---

## Prerequisites

Before running the project, ensure you have the following installed:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

---

## Getting Started

### Clone the Repository

```bash
git clone https://github.com/YehorYehorychev/Dockerized-Time-App.git
cd Dockerized-Time-App
```

## Start the Application

### Run the following command to start all services:

```docker-compose up -d```

### This will initialize the following services:

    Frontend: Accessible at http://localhost:3000
    Backend: Accessible at http://localhost:5555
    Adminer: Accessible at http://localhost:8888

### Docker Compose Configuration
Services:

    Frontend:
        Runs on port 3000.
        Maps node_modules and application code for live updates.

    Backend:
        Runs on port 5555.
        Depends on the MySQL service for database connectivity.

    MySQL:
        Runs on the default MySQL port 3306.
        Contains a health check to ensure the service is ready.
        Database name: time_db.

    Adminer:
        Runs on port 8888.
        Provides a graphical interface to interact with the MySQL database.

### Environment Variables

The following environment variables are used in the project:
MySQL

    MYSQL_HOST: Hostname for the database (default: mysql).
    MYSQL_USER: Database username (default: root).
    MYSQL_PASSWORD: Password for the database user (default: password).
    MYSQL_DATABASE: Database name (default: time_db).
    MYSQL_ROOT_PASSWORD: Root password for the database (default: password).

### Stopping the Application

To stop and remove all containers, run:

``` docker-compose down```

### Troubleshooting
Common Issues:

- Port Conflicts: If any service port is already in use, update the ports in the docker-compose.yml file.

- MySQL Connection Issues: Ensure the MySQL service is healthy before the backend starts. The depends_on configuration and health checks manage this automatically.
