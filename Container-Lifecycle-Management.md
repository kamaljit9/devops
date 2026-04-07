# 🔄 Container Lifecycle Management: Start, Stop, and ps

## 1. Defining the Container Lifecycle
Containers are not rigidly active entities. They exist in various states based on the requirements of the system and user commands. Understanding how to track and manipulate these states is the absolute responsibility of a DevOps engineer. A container broadly possesses three core operational states:
1. **Running:** Actively executing processes, consuming RAM and CPU time.
2. **Exited/Stopped:** The primary process has been forcefully halted or naturally crashed. It consumes absolutely zero CPU or RAM, but continues to occupy physical disk storage space on the host drive.
3. **Deleted:** Completely purged from the host system environment.

---

## 2. Telemetry and Tracking: The `docker ps` Command
When managing multiple concurrent web applications, you desperately require an immediate overview of exactly what is running. This is where `docker ps` (Process Status) becomes essential.

### Viewing Active Workloads
```bash
docker ps
```
Executing this command generates a tabular readout containing:
* **CONTAINER ID:** The truncated system identifier hash.
* **IMAGE:** The template from which it was constructed (e.g., `nginx:latest`).
* **COMMAND:** The PID 1 command holding it open (e.g., `nginx -g 'daemon off;'`).
* **CREATED:** Timeline since the container creation string.
* **STATUS:** Explicit uptime (e.g., `Up 3 hours`).
* **PORTS:** Mapped logical routing endpoints.
* **NAMES:** The human-readable string identifier.

### Viewing Historical and Dormant Workloads
By default, `docker ps` acts like a filter, exclusively visualizing "Up" containers. What if a database container crashed overnight? It will completely disappear from standard telemetry.
```bash
docker ps -a
```
The `-a` (All) flag aggressively fetches every container that exists on the hard drive, regardless of current operating status. If you see a status of `Exited (137) 10 hours ago`, you have instantly confirmed a system crash.

---

## 3. Controlling State: Stop and Start Transitions
Just as you would not delete an entire virtual machine simply to reboot its engine, you do not use `docker rm` to restart a web server. 

### Graceful Shutdown Execution
```bash
docker stop web_server
```
When you execute `docker stop`, Docker transmits an elegant `SIGTERM` (Signal Terminate) to the primary process inside the container. This grants the internal software approximately 10 seconds to save state, close database connections gracefully, and log shutdown operations. If the application freezes and fails to halt within 10 seconds, Docker issues a merciless `SIGKILL`, brutally severing the process instantly.

### Reinitialization and Awakening
To wake up dormant infrastructure:
```bash
docker start web_server
```
This rapidly resurrects the container using the precise configuration state, mounted volumes, and environmental variables it possessed prior to stopping. The startup latency is historically measured in mere milliseconds, heavily contrasting against traditional hypervisor virtual machines.

---

## 4. Total Purge Operations: The `docker rm` Command
If a container configuration is hopelessly broken, or an application update renders it obsolete, it must be eradicated from disk memory.

```bash
docker rm web_server
```
**Critical Academic Exam Note:** If a container is actively running (Status: Up), Docker's engine protection logic will explicitly reject the `rm` command to prevent catastrophic accidental data loss. You are conceptually forced to sequentially execute `docker stop` followed by `docker rm`. 
*(Alternatively, advanced users occasionally apply `docker rm -f` to violently force-kill and delete simultaneously, though this invokes dirty database shutdowns).*

## 5. Lab Examination Scenario
A developer asks you to halt a corrupted Nginx load balancer to deploy an urgent patch. The mandated professional workflow:
1. `docker ps` (To locate the running Container ID)
2. `docker stop <Container_ID>` (To sever connections gracefully)
3. `docker rm <Container_ID>` (To clear the disk state pipeline)
4. `docker run -d --name new_lb nginx` (To redeploy cleanly)
