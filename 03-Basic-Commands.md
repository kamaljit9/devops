# 📜 Basic Docker Commands (Foundation)

Before jumping into advanced concepts, these foundational commands are critical!

## Checking the Status
```bash
# Verify installation
docker --version

# View system details, active containers, images count
docker info
```

## Logs and Deletion
```bash
# Display logs for a specific container
docker logs <container_id_or_name>

# Stop a running container
docker stop <container_name>

# Start an existing stopped container
docker start <container_name>

# Delete a container
docker rm <container_name>

# Delete an image
docker rmi <image_name>
```

**🔥 Pro Tip:** You cannot delete an image if a container is currently using it. You must stop and remove the container first!
