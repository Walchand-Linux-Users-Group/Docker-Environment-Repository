# Docker Image: PostgreSQL + pgAdmin Environment 🐘

## Description
This Docker Compose setup is designed for **Database Systems**, providing a ready-to-use **PostgreSQL** database with a **pgAdmin** web interface.  
It allows developers to **set up, manage, and visualize PostgreSQL databases** quickly using Docker — no manual installation required.

With this setup, users can:
- Run a PostgreSQL server instantly for development or testing.
- Manage and explore databases through pgAdmin’s web interface.
- Persist data between restarts using Docker volumes.

---

## Getting Started

### Prerequisites
Ensure you have the following installed:
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

---

### Building the Image
To start both containers (PostgreSQL and pgAdmin), navigate to project directory:

1) **First-time setup (build images if not present):**
```bash
docker-compose up --build
```

2) **Subsequent runs (if images already exist):**
```bash
docker-compose up -d
```

To stop and remove the containers:
```bash
docker-compose down
```


---

### Accessing pgAdmin and Connecting to Postgresql
Once the containers are up, open your browser and visit:
```
http://localhost:9090
```

Login credentials:
```
Email: admin@local.com
Password: admin
```

To connect pgAdmin to PostgreSQL:
* In pgAdmin, right-click on Servers → Register → Server...
* Under the General tab, enter any name (e.g., Local PostgreSQL).
* Go to the Connection tab and fill in the following details:
    * Host: postgres
    * Port: 5432
    * Username: devuser
    * Password: devpass

---

### Features
* PostgreSQL Database Server (v15) for development and testing.
* pgAdmin 4 Web Interface to manage PostgreSQL visually via browser.
* Persistent Storage using Docker volumes.
* Environment Variables for easy customization.
* One-Command Setup with Docker Compose.

---