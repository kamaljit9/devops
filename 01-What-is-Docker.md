# 🐳 What is Docker?

## Definition
Docker is a platform that allows you to create, run, and manage applications inside **containers**. It packages an application and its dependencies together so it can run seamlessly across different environments.

## Real-life Example
Think of Docker like a **lunchbox** (container):
- **Food** = your application
- **Lunchbox** = container
No matter where you carry it (school, bus, train), the food remains the same. 
✔ **Same way → Docker ensures your app runs exactly the same everywhere.**

## Docker vs Virtual Machines
| Feature | Virtual Machines (VMs) | Docker Containers |
| :--- | :--- | :--- |
| **Architecture** | Heavyweight, uses Hypervisor | Lightweight, uses Host OS kernel directly |
| **Speed** | Slow to boot (minutes) | Milliseconds to start |
| **Resource Usage** | High (fixed RAM mapping) | Low (isolated processes) |

## Quick Start Commands
```bash
# Check Docker version
docker --version

# System-wide info (System settings -> storage, apps, RAM)
docker info
```
