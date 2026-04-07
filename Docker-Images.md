# 🖼️ Docker Images

## What is a Docker Image?
An image is a read-only template that contains a set of instructions for creating a Docker container. 
**Deep Concept:** Docker images use a layered filesystem. Each line is its own layer → these layers are cached, resulting in faster rebuilds.

## Pulling Images
Used to download an image from Docker Hub without running it immediately.
```bash
# Download the latest Ubuntu image
docker pull ubuntu

# Download Nginx web server
docker pull nginx
```
*💡 Real-life Example: Like downloading an app from the Google Play Store.*

## Managing Images
```bash
# List all locally available images
docker images

# Result shows: REPOSITORY, TAG, IMAGE ID, CREATED, SIZE
```

## Tagging and Renaming
```bash
docker tag old_image:latest my_custom_name:v1
```
