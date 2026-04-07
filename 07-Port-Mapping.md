# 🌐 Docker Port Mapping (-p)

## Definition
The `-p` flag maps a port from the host system to a port inside the container, allowing external access to containerized applications.

## How it Works
Containers run in an isolated network by default. They are not accessible from the outside.
- **Docker setting:** NAT (Network Address Translation) connects the Host Port → Container Port.

## Syntax & Examples
```bash
docker run -p <host_port>:<container_port> <image>
```

### Mapping Nginx
```bash
docker run -p 8080:80 nginx
```
*Explanation:*
- `8080` → Port on your Host machine
- `80` → Port inside the Nginx container
*Access:* `http://localhost:8080` in your web browser.

## Common Mistakes
❌ `docker run -p 8080 80 nginx` (Missing colon)
✅ `docker run -p 8080:80 nginx` (Correct)

## Random Port Mapping
```bash
docker run -p 80 nginx
```
Docker will assign a random host port available to bind to port 80 internally.
