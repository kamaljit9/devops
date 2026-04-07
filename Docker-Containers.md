# 📦 Docker Containers

## What is a Container?
A container is the running instance of a Docker Image. If an image is the "Class", the container is the "Object".

## Listing Containers
```bash
# Show ONLY running containers
docker ps

# Show ALL containers (running + stopped)
docker ps -a
```
*💡 Real-life Example:* Like checking closed and active apps on your task manager.

## Executing Commands Inside Containers
Sometimes you need to SSH or terminal into a running container.
```bash
# Open an interactive bash shell in a running container
docker exec -it <container_id> bash
```
*Note:* `exec` is used because the container is already running.

## Deleting Containers Auto-Magically
Using `--rm` will delete the container immediately after it stops.
```bash
docker run --rm ubuntu bash
```
*💡 Real-life Example:* Like using a disposable paper cup!
