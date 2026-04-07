# 📡 Docker Networking

## Concept
Containers communicate via virtual bridge networks. Each container gets its own IP address internally.

## Network Commands
```bash
# List all Docker networks
docker network ls

# Create a custom bridge network
docker network create mynet
```

## Attaching Containers to Networks
If you want a frontend app to talk to a backend app, they need to be on the same network!
```bash
# Run a container attached to 'mynet'
docker run --network=mynet nginx
```

## Available Network Drivers
1. **Bridge:** The default network for isolated containers.
2. **Host:** Removes network isolation; the container uses the host machine’s networking directly.
3. **None:** Disables all networking for a highly secure container.
