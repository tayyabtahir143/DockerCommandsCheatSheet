# Docker Commands Cheat Sheet 🐳

A quick reference guide for Docker commands, optimized for developers and DevOps.

---

## 🔹 Container Management

| Command | Description |
|---------|-------------|
| `docker run -d --name <name> <image>` | Run a container in detached mode |
| `docker start <container>` | Start a stopped container |
| `docker stop <container>` | Stop a running container |
| `docker restart <container>` | Restart a container |
| `docker rm <container>` | Remove a stopped container |
| `docker rm -f <container>` | Force remove a running container |
| `docker ps` | List running containers |
| `docker ps -a` | List all containers (including stopped) |
| `docker exec -it <container> /bin/bash` | Open interactive shell in running container |
| `docker logs <container>` | View container logs |
| `docker logs -f <container>` | Follow logs in real-time |

---

## 🔹 Image Management

| Command | Description |
|---------|-------------|
| `docker images` | List all local images |
| `docker pull <image>` | Download an image from registry |
| `docker push <image>` | Push an image to registry |
| `docker build -t <name> .` | Build image from Dockerfile in current dir |
| `docker rmi <image>` | Remove an image |
| `docker image prune` | Remove dangling images |
| `docker history <image>` | Show image layers |

---

## 🔹 Networking

| Command | Description |
|---------|-------------|
| `docker network ls` | List all networks |
| `docker network create <name>` | Create a new network |
| `docker network inspect <network>` | Inspect a network |
| `docker network connect <network> <container>` | Connect container to network |
| `docker network disconnect <network> <container>` | Disconnect container |

---

## 🔹 Volumes & Storage

| Command | Description |
|---------|-------------|
| `docker volume ls` | List all volumes |
| `docker volume create <name>` | Create a new volume |
| `docker volume inspect <volume>` | Inspect a volume |
| `docker run -v /host/path:/container/path` | Bind mount host directory |
| `docker run -v volume_name:/container/path` | Use named volume |

---

## 🔹 Docker Compose

| Command | Description |
|---------|-------------|
| `docker-compose up -d` | Start services in detached mode |
| `docker-compose down` | Stop and remove containers/networks |
| `docker-compose ps` | List running compose services |
| `docker-compose logs` | View compose service logs |
| `docker-compose build` | Rebuild images |
| `docker-compose exec <service> <command>` | Execute command in service |

---

## 🔹 System & Cleanup

| Command | Description |
|---------|-------------|
| `docker info` | Display system-wide info |
| `docker stats` | Live resource usage stats |
| `docker system df` | Show disk usage |
| `docker system prune` | Remove unused data |
| `docker system prune -a` | Remove all unused images |
| `docker top <container>` | List processes in container |

---

## 🔹 Advanced Commands

| Command | Description |
|---------|-------------|
| `docker save <image> > file.tar` | Save image to tar archive |
| `docker load < file.tar` | Load image from tar archive |
| `docker inspect <container>` | Inspect container metadata |
| `docker port <container>` | List port mappings |
| `docker update --memory 512M <container>` | Update container resources |

---

## 🔹 Useful Flags

| Flag | Description |
|------|-------------|
| `-p 8080:80` | Port mapping (host:container) |
| `-e VAR=value` | Set environment variable |
| `--env-file .env` | Load env vars from file |
| `--restart always` | Auto-restart policy |
| `--link <container>` | Legacy container linking |
| `--cpu-shares 512` | CPU resource limit |

---

## 📝 Example Workflows

**1. Run Nginx with port mapping:**
```bash
docker run -d --name webserver -p 8080:80 nginx
