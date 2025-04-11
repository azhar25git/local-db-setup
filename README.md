# 🐳 Local Development Databases with Docker Compose

This setup provides a fully containerized local environment for common databases:

- PostgreSQL 16
- Redis 7
- MySQL 8
- MongoDB 7

Perfect for development and local testing purposes.

---

## 🚀 Getting Started

### Prerequisites
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

### Start All Services
```bash
docker-compose up -d
```

### Stop All Services
```bash
docker-compose down
```

### Stop and Remove All Data
```bash
docker-compose down -v
```

---

## 🧩 Services Overview

### 🔷 PostgreSQL
- **Image**: `postgres:16`
- **Port**: `5432`
- **Credentials**:
  - `User`: `devuser`
  - `Password`: `devpass`
  - `Database`: `devdb`
- **Volume**: `pgdata`

---

### 🔶 MySQL
- **Image**: `mysql:8`
- **Port**: `3306`
- **Credentials**:
  - `User`: `devuser`
  - `Password`: `devpass`
  - `Root Password`: `rootpass`
  - `Database`: `devdb`
- **Volume**: `mysqldata`

---

### 🟥 Redis
- **Image**: `redis:7`
- **Port**: `6379`
- **Volume**: `redisdata`
- **Note**: No authentication is enabled in this basic setup. Add security if needed.

---

### 🟩 MongoDB
- **Image**: `mongo:7`
- **Port**: `27017`
- **Credentials**:
  - `User`: `devuser`
  - `Password`: `devpass`
- **Volume**: `mongodata`

---

## 🛠 Accessing the Services

Use your favorite client (e.g., DBeaver, TablePlus, Compass, RedisInsight, etc.) with the following credentials:

| Service   | Host       | Port  | Username | Password | Database |
|-----------|------------|-------|----------|----------|----------|
| PostgreSQL| 127.0.0.1  | 5432  | devuser  | devpass  | devdb    |
| MySQL     | 127.0.0.1  | 3306  | devuser  | devpass  | devdb    |
| Redis     | 127.0.0.1  | 6379  | -        | -        | -        |
| MongoDB   | 127.0.0.1  | 27017 | devuser  | devpass  | -        |

---

## 📦 Data Persistence

Each service uses a named volume for persistent data:

- `pgdata` → PostgreSQL
- `redisdata` → Redis
- `mysqldata` → MySQL
- `mongodata` → MongoDB

---

## 🧹 Clean Up Volumes

```bash
docker volume ls       # View all volumes
docker volume rm <name>  # Remove a specific volume
```

Or remove everything:
```bash
docker-compose down -v
```

---

## ✅ Notes

- Ports are bound to `127.0.0.1` for local-only access.
- This is **not production-ready** — designed for local development only.
- You can connect with local db managers like DBeaver, Arc etc.

---

Happy hacking! 💻🧪
```

---