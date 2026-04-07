# 💾 Docker Volumes & Storage

## Concept
By default, data inside a container is temporary. If the container is deleted, the data is gone forever! Volumes provide persistent storage.

## Creating and Managing Volumes
```bash
# Create persistent storage volume
docker volume create my_database_data

# List volumes
docker volume ls
```

## Attaching a Volume (-v)
```bash
# Syntax: -v <volume_name_or_path>:<container_path>
docker run -v my_database_data:/var/lib/mysql mysql
```
*Explanation:* Even if the `mysql` container is deleted, the database tables remain safely stored inside `my_database_data` on the host machine.

## Bind Mounts (Local Directory Sync)
Map an exact host directory to the container. Great for live-reloading code.
```bash
docker run -v $(pwd)/src:/app/src my_react_app
```
