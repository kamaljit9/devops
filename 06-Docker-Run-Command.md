# ⭐ The `docker run` Command 

## Definition
The MOST IMPORTANT command in Docker. It creates a container from an image and starts it.

## Syntax
```bash
docker run [OPTIONS] IMAGE
```

## Essential Flags

### 1. Interactive Mode (`-it`)
Allows you to directly interact with the container.
```bash
docker run -it ubuntu bash
```
*💡 Real-life Example:* Opening a terminal inside another computer.

### 2. Detached Mode (`-d`)
Runs the container in the background.
```bash
docker run -d nginx
```
*💡 Real-life Example:* Running WhatsApp or Spotify in the background.

### 3. Naming (`--name`)
Assign a readable name instead of a random string.
```bash
docker run --name my-web-server nginx
```

### 4. Port Mapping (`-p`)
Maps host ports to container ports (See Port Mapping guide for details).
```bash
docker run -p 8080:80 nginx
```
