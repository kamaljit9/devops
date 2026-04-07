# 🔬 Advanced Concepts & Commands

## Inspecting Objects
Want to see the IP Address, Volume mounts, or raw JSON config of a container?
```bash
docker inspect <container_name_or_id>
```

## Real-Time Resource Usage
Check CPU and RAM usage live (like Linux `top`).
```bash
docker stats
```

## Docker Commit
Save a modified container as a new image locally.
```bash
docker commit <container_id> my_new_image:v2
```

## Pushing to Docker Hub
```bash
# 1. Login to Docker Hub
docker login

# 2. Tag properly
docker tag my_image:latest username/my_image:latest

# 3. Push online
docker push username/my_image:latest
```
