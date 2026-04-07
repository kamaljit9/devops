# 🛠️ Image Building (Dockerfile)

## Definition
Instead of manually installing things inside a container, we script the creation of images using a `Dockerfile`.

## Basic Dockerfile Example
Create a file named `Dockerfile`:
```dockerfile
# 1. Start from a base OS image
FROM ubuntu:20.04

# 2. Run instructions
RUN apt update && apt install -y python3

# 3. Copy files from host to image
COPY . /app

# 4. Command to run when container starts
CMD ["python3", "/app/script.py"]
```

## Building the Image
```bash
# Syntax: docker build -t <tag_name> <path_to_dockerfile>
docker build -t my-python-app .
```
*(The `.` denotes the current directory).*

**Deep Concept:** Docker creates a new layer for every line in the `Dockerfile`. Organizing layers matters for speed!
