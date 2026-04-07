# 🏗️ Docker Architecture

## Client-Server Model
Docker uses a client-server architecture to handle the heavy lifting of building, running, and distributing your containers.

### 1. Client (CLI)
This is the interface you use. Every time you type a command like `docker run`, the client passes it to the daemon.

### 2. Docker Daemon (dockerd)
The background service. It listens for Docker API requests and manages Docker objects (images, containers, networks, volumes).

### 3. Registry (Docker Hub)
Where images are stored globally. It acts like an App Store for software packages.

## Core Technologies (Under the Hood)
Docker uses Linux-specific kernel features:
1. **Namespaces:** Provides isolation for workspaces. Every container gets its own isolated network, process tree (PID), and mount points.
2. **Control Groups (cgroups):** Limits hardware resources (CPU/RAM). Prevents one container from eating all the server memory.
