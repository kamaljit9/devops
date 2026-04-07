# 🧹 Cleanup & Pruning

Over time, Docker can consume a lot of disk space with old images, stopped containers, and unused volumes. Here is how to clean it up safely.

## System Prune
The most powerful cleanup command.
```bash
docker system prune
```
**This deletes:**
- All stopped containers
- All unattached networks
- All unused images (dangling images)
- Build cache

To include all unused volumes as well:
```bash
docker system prune --volumes
```

## Pruning Individually
```bash
# Remove dangling images only
docker image prune

# Remove all stopped containers
docker container prune
```
