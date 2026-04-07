# 🐙 Docker Compose

## What is it?
When dealing with multi-container applications (e.g., a React Frontend, Node Backend, and MySQL Database), doing `docker run` manually for each is tedious. `docker-compose` simplifies this.

## Create a `docker-compose.yml`
```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
  db:
    image: mysql
    environment:
      MYSQL_ROOT_PASSWORD: root
```

## Commands
```bash
# Start all services (in background)
docker-compose up -d

# View logs for all services
docker-compose logs

# Stop and remove all services
docker-compose down
```
