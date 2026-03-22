# 🐳 Docker — Complete Guide: Beginner to Legend
> **Author-Ready README** | Upload to GitHub and help the world learn Docker!  
> Covers: Installation → Commands → Networking → Volumes → Docker Compose → Deploying Websites → Best Practices → Advanced Tricks

---

## 📚 Table of Contents

1. [What is Docker?](#1-what-is-docker)
2. [Why Use Docker?](#2-why-use-docker)
3. [Core Concepts & Terminology](#3-core-concepts--terminology)
4. [Installing Docker](#4-installing-docker)
   - [Windows](#41-install-on-windows)
   - [macOS](#42-install-on-macos)
   - [Ubuntu / Debian Linux](#43-install-on-ubuntu--debian-linux)
   - [Fedora / RHEL / CentOS](#44-install-on-fedora--rhel--centos)
   - [Verify Installation](#45-verify-installation)
5. [Docker Architecture](#5-docker-architecture)
6. [Essential Docker Commands](#6-essential-docker-commands)
   - [docker version & info](#61-docker-version--info)
   - [Images](#62-working-with-images)
   - [Containers](#63-working-with-containers)
   - [Exec & Logs](#64-exec--logs)
   - [Copy Files](#65-copy-files-tofrom-container)
   - [Inspect & Stats](#66-inspect--stats)
7. [Dockerfile — Build Your Own Image](#7-dockerfile--build-your-own-image)
   - [Dockerfile Instructions](#71-dockerfile-instructions-full-reference)
   - [Build Commands](#72-build-commands)
   - [Multi-Stage Builds](#73-multi-stage-builds)
8. [Docker Volumes](#8-docker-volumes)
9. [Docker Networking](#9-docker-networking)
10. [Docker Compose](#10-docker-compose)
    - [Install Compose](#101-install-docker-compose)
    - [Compose File Reference](#102-compose-file-full-reference)
    - [Compose Commands](#103-docker-compose-commands)
11. [Deploying a Website with Docker](#11-deploying-a-website-with-docker)
    - [Deploy Static HTML Site](#111-deploy-a-static-html-website)
    - [Deploy React App](#112-deploy-a-react-app)
    - [Deploy Python Flask App](#113-deploy-a-python-flask-app)
    - [Deploy Node.js App](#114-deploy-a-nodejs-app)
    - [Deploy with Nginx Reverse Proxy](#115-deploy-with-nginx-reverse-proxy)
12. [Docker Registry](#12-docker-registry)
    - [Docker Hub](#121-docker-hub)
    - [Private Registry](#122-private-registry)
    - [GitHub Container Registry](#123-github-container-registry)
13. [Docker Swarm — Orchestration](#13-docker-swarm--orchestration)
14. [Environment Variables & Secrets](#14-environment-variables--secrets)
15. [Docker Security Best Practices](#15-docker-security-best-practices)
16. [Docker Resource Management](#16-docker-resource-management)
17. [Docker Prune & Cleanup](#17-docker-prune--cleanup)
18. [Docker Troubleshooting](#18-docker-troubleshooting)
19. [Advanced Docker Tips](#19-advanced-docker-tips)
20. [Quick Reference Cheat Sheet](#20-quick-reference-cheat-sheet)

---

## 1. What is Docker?

Docker is an **open-source platform** that allows you to **package, ship, and run applications** inside lightweight, portable units called **containers**.

Think of it like this:

```
🏠 Traditional Server           🐳 Docker Container
─────────────────────           ───────────────────
Your App                        Your App
+ OS Libraries                  + Only what your app needs
+ Runtime                       + Runtime
+ Entire Operating System  vs.  Shared OS Kernel (lightweight!)
= Heavy, slow, inconsistent     = Fast, portable, consistent
```

> **One liner:** "Build once, run anywhere." — Docker's core promise.

---

## 2. Why Use Docker?

| Problem Without Docker | Solution With Docker |
|------------------------|----------------------|
| "It works on my machine!" | Same container runs everywhere |
| App setup takes hours | `docker run` in seconds |
| Dependency conflicts | Each container is isolated |
| Difficult scaling | Spin up 100 containers instantly |
| Hard to reproduce bugs | Identical environments |
| Complex deployment | Ship the container, not the code |

### Real-World Use Cases:
- 🌐 Deploying web applications (React, Flask, Node.js, Django)
- 🤖 Running ML/AI models in isolated environments
- 🔄 CI/CD pipelines (GitHub Actions, Jenkins)
- 📦 Microservices architecture
- 🧪 Testing in clean environments
- 🗄️ Running databases locally without installing them

---

## 3. Core Concepts & Terminology

| Term | Description |
|------|-------------|
| **Image** | A read-only blueprint/template to create containers. Like a class in Python |
| **Container** | A running instance of an image. Like an object created from a class |
| **Dockerfile** | A text file with instructions to build a Docker image |
| **Docker Hub** | Cloud registry to store and share Docker images (like GitHub for images) |
| **Volume** | Persistent storage that survives container restarts |
| **Network** | Allows containers to communicate with each other |
| **Docker Compose** | Tool to define and run multi-container apps using a YAML file |
| **Registry** | A storage system for Docker images (Docker Hub, GHCR, ECR) |
| **Layer** | Each instruction in Dockerfile creates a cached layer |
| **Daemon** | Background service that manages Docker objects (`dockerd`) |
| **Docker Client** | The CLI tool you use to talk to the Docker daemon (`docker`) |

### Visual Architecture:
```
You (Developer)
     │
     │ docker commands
     ▼
Docker Client (CLI)
     │
     │ REST API
     ▼
Docker Daemon (dockerd)   ← runs in background
     │
     ├──── Images
     ├──── Containers
     ├──── Volumes
     └──── Networks
```

---

## 4. Installing Docker

### 4.1 Install on Windows

**Requirements:** Windows 10/11 (64-bit), WSL2 enabled

**Step 1:** Enable WSL2
```powershell
# Run PowerShell as Administrator
wsl --install
# Restart your computer
```

**Step 2:** Download Docker Desktop
- Go to: https://www.docker.com/products/docker-desktop/
- Download the `.exe` installer for Windows
- Run the installer

**Step 3:** Configure Docker Desktop
- Open Docker Desktop
- Go to **Settings → General** → Enable "Use WSL 2 based engine"
- Click **Apply & Restart**

**Step 4:** Verify
```powershell
docker --version
docker run hello-world
```

---

### 4.2 Install on macOS

**Requirements:** macOS 11+ (Big Sur or later), Apple Silicon or Intel

**Method 1: Docker Desktop (Recommended)**
```bash
# Download from:
# https://www.docker.com/products/docker-desktop/

# Or use Homebrew:
brew install --cask docker

# Start Docker Desktop from Applications
# Verify:
docker --version
```

**Method 2: Colima (Lightweight alternative for macOS)**
```bash
brew install colima docker
colima start
docker --version
```

---

### 4.3 Install on Ubuntu / Debian Linux

```bash
# Step 1: Update package index
sudo apt-get update

# Step 2: Install required packages
sudo apt-get install -y \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

# Step 3: Add Docker's official GPG key
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
    sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# Step 4: Set up the Docker repository
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Step 5: Update and install Docker Engine
sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io \
    docker-buildx-plugin docker-compose-plugin

# Step 6: Start and enable Docker
sudo systemctl start docker
sudo systemctl enable docker

# Step 7: Run Docker without sudo (optional but recommended)
sudo usermod -aG docker $USER
newgrp docker   # Apply group changes without logout

# Step 8: Verify
docker --version
docker run hello-world
```

---

### 4.4 Install on Fedora / RHEL / CentOS

```bash
# Step 1: Remove old versions
sudo dnf remove docker docker-client docker-client-latest \
    docker-common docker-latest docker-latest-logrotate \
    docker-logrotate docker-selinux docker-engine-selinux docker-engine

# Step 2: Add Docker repo
sudo dnf -y install dnf-plugins-core
sudo dnf config-manager \
    --add-repo \
    https://download.docker.com/linux/fedora/docker-ce.repo

# Step 3: Install Docker
sudo dnf install -y docker-ce docker-ce-cli containerd.io \
    docker-buildx-plugin docker-compose-plugin

# Step 4: Start Docker
sudo systemctl start docker
sudo systemctl enable docker

# Step 5: Add user to docker group
sudo usermod -aG docker $USER
newgrp docker

# Verify
docker --version
docker run hello-world
```

---

### 4.5 Verify Installation

```bash
# Check Docker version
docker --version
# Output: Docker version 26.x.x, build xxxxxxx

# Check Docker daemon status (Linux)
sudo systemctl status docker

# Run hello-world to confirm everything works
docker run hello-world

# Check detailed system info
docker info
```

**Expected output of `docker run hello-world`:**
```
Hello from Docker!
This message shows that your installation appears to be working correctly.
```

---

## 5. Docker Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        Docker Host                               │
│                                                                   │
│  ┌──────────────┐    REST API    ┌─────────────────────────────┐ │
│  │ Docker Client│ ◄───────────► │      Docker Daemon (dockerd) │ │
│  │   (docker)   │               │                              │ │
│  └──────────────┘               │  ┌──────────┐  ┌──────────┐ │ │
│                                 │  │ Container│  │ Container│ │ │
│  ┌──────────────┐               │  │  (app1)  │  │  (app2)  │ │ │
│  │Docker Compose│               │  └──────────┘  └──────────┘ │ │
│  └──────────────┘               │                              │ │
│                                 │  ┌──────────┐  ┌──────────┐ │ │
│                                 │  │  Images  │  │ Volumes  │ │ │
│                                 │  └──────────┘  └──────────┘ │ │
│                                 └─────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
                          │
                          │ Pull/Push
                          ▼
                   ┌─────────────┐
                   │  Docker Hub │
                   │  (Registry) │
                   └─────────────┘
```

---

## 6. Essential Docker Commands

### 6.1 Docker Version & Info

```bash
docker --version                 # Short version info
docker version                   # Full client & server version
docker info                      # System-wide Docker info
docker system df                 # Disk usage by Docker objects
```

---

### 6.2 Working with Images

#### Search Images
```bash
docker search nginx              # Search Docker Hub for nginx
docker search --limit 5 python   # Limit results to 5
docker search --filter stars=100 ubuntu  # Filter by star rating
```

#### Pull Images
```bash
docker pull ubuntu               # Pull latest ubuntu image
docker pull ubuntu:22.04         # Pull specific version (tag)
docker pull python:3.11-slim     # Pull slim python image
docker pull nginx:alpine         # Alpine = very small image
```

#### List Images
```bash
docker images                    # List all local images
docker image ls                  # Same as above
docker images -a                 # Include intermediate images
docker images --filter dangling=true  # Show dangling (untagged) images
docker images --format "table {{.Repository}}\t{{.Tag}}\t{{.Size}}"
```

#### Inspect Image
```bash
docker inspect ubuntu            # Detailed JSON info about image
docker image inspect ubuntu      # Same as above
docker history ubuntu            # Show layers of an image
docker image history nginx --no-trunc  # Full commands in each layer
```

#### Tag an Image
```bash
docker tag myapp:latest myusername/myapp:v1.0
# Format: docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
```

#### Remove Images
```bash
docker rmi ubuntu                # Remove image by name
docker rmi ubuntu:22.04          # Remove specific tag
docker rmi abc123def456          # Remove by image ID
docker rmi $(docker images -q)   # Remove ALL images (careful!)
docker image prune               # Remove dangling images
docker image prune -a            # Remove all unused images
```

#### Save & Load Images (offline transfer)
```bash
docker save -o myapp.tar myapp:latest     # Save image to file
docker load -i myapp.tar                  # Load image from file
docker export container_name > myapp.tar  # Export container filesystem
docker import myapp.tar myapp:restored    # Import as image
```

---

### 6.3 Working with Containers

#### Run Containers
```bash
# Basic run
docker run ubuntu

# Run with name
docker run --name mycontainer ubuntu

# Run interactively (keeps terminal open)
docker run -it ubuntu bash

# Run in background (detached mode)
docker run -d nginx

# Run and auto-remove when stopped
docker run --rm ubuntu echo "Hello World"

# Run with port mapping: host_port:container_port
docker run -d -p 8080:80 nginx
# Now visit http://localhost:8080

# Run with multiple port mappings
docker run -d -p 8080:80 -p 8443:443 nginx

# Run with environment variables
docker run -d -e MYSQL_ROOT_PASSWORD=secret mysql

# Run with volume mount
docker run -d -v /host/path:/container/path nginx

# Run with resource limits
docker run -d --memory="256m" --cpus="1.5" nginx

# Run with custom hostname
docker run --hostname myserver ubuntu

# Run with restart policy
docker run -d --restart always nginx
# restart options: no, always, on-failure, unless-stopped

# Full example combining options:
docker run -d \
  --name my-nginx \
  -p 8080:80 \
  -v ./html:/usr/share/nginx/html \
  -e NGINX_HOST=localhost \
  --restart unless-stopped \
  nginx
```

#### List Containers
```bash
docker ps                        # Running containers only
docker ps -a                     # All containers (including stopped)
docker ps -q                     # Only show container IDs
docker ps --filter status=exited # Show only stopped containers
docker ps --filter name=nginx    # Filter by name
docker ps --format "table {{.ID}}\t{{.Names}}\t{{.Status}}\t{{.Ports}}"
```

#### Start / Stop / Restart Containers
```bash
docker start mycontainer         # Start a stopped container
docker stop mycontainer          # Gracefully stop (SIGTERM, waits 10s)
docker stop -t 30 mycontainer    # Wait 30 seconds before killing
docker kill mycontainer          # Force stop immediately (SIGKILL)
docker restart mycontainer       # Stop then start
docker pause mycontainer         # Pause all processes in container
docker unpause mycontainer       # Resume paused container
```

#### Remove Containers
```bash
docker rm mycontainer            # Remove stopped container
docker rm -f mycontainer         # Force remove running container
docker rm $(docker ps -aq)       # Remove all stopped containers
docker container prune           # Remove all stopped containers
```

#### Rename Containers
```bash
docker rename old_name new_name
```

---

### 6.4 Exec & Logs

#### Execute Commands in Running Container
```bash
docker exec mycontainer ls /app           # Run single command
docker exec -it mycontainer bash          # Interactive bash shell
docker exec -it mycontainer sh            # For alpine (no bash)
docker exec -u root mycontainer bash      # Run as root user
docker exec -e VAR=value mycontainer env  # With env variable
docker exec -w /app mycontainer ls        # Set working directory
```

#### View Logs
```bash
docker logs mycontainer                   # All logs
docker logs -f mycontainer               # Follow/tail logs (live)
docker logs --tail 50 mycontainer        # Last 50 lines
docker logs --since 1h mycontainer       # Logs from last 1 hour
docker logs --since "2024-01-01" mycontainer  # Since a date
docker logs --timestamps mycontainer     # Include timestamps
docker logs -f --tail 20 mycontainer     # Follow + last 20 lines
```

---

### 6.5 Copy Files To/From Container

```bash
# Copy file FROM container TO host
docker cp mycontainer:/app/file.txt ./file.txt

# Copy file FROM host TO container
docker cp ./file.txt mycontainer:/app/file.txt

# Copy entire directory
docker cp mycontainer:/app/logs ./local_logs/
docker cp ./local_files/ mycontainer:/app/files/
```

---

### 6.6 Inspect & Stats

```bash
docker inspect mycontainer           # Full JSON metadata
docker inspect --format='{{.NetworkSettings.IPAddress}}' mycontainer  # Get IP
docker inspect --format='{{.State.Running}}' mycontainer  # Check if running
docker stats                         # Live resource usage (all containers)
docker stats mycontainer             # Stats for specific container
docker stats --no-stream             # One-time snapshot (not live)
docker top mycontainer               # Processes running inside container
docker diff mycontainer              # File changes since container started
```

---

## 7. Dockerfile — Build Your Own Image

A **Dockerfile** is a recipe to create your own Docker image.

### 7.1 Dockerfile Instructions (Full Reference)

```dockerfile
# ============================================================
# FULL DOCKERFILE REFERENCE — Every Instruction Explained
# ============================================================

# FROM — Base image (must be first instruction)
# Syntax: FROM <image>[:<tag>] [AS <name>]
FROM ubuntu:22.04
FROM python:3.11-slim AS builder  # Named stage for multi-stage build
FROM scratch                       # Empty image (for Go binaries etc.)


# LABEL — Add metadata to the image
LABEL maintainer="yourname@email.com"
LABEL version="1.0"
LABEL description="My awesome application"
LABEL org.opencontainers.image.source="https://github.com/user/repo"


# ARG — Build-time variables (not available in running container)
# Syntax: ARG <name>[=<default>]
ARG APP_VERSION=1.0
ARG BUILD_DATE


# ENV — Environment variables (available in container at runtime)
# Syntax: ENV <key>=<value>
ENV APP_HOME=/app
ENV NODE_ENV=production
ENV PORT=8080
ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1


# WORKDIR — Set working directory (creates it if doesn't exist)
# All subsequent RUN, CMD, COPY, ADD use this as base path
WORKDIR /app


# COPY — Copy files/dirs from build context into image
# Syntax: COPY [--chown=user:group] <src> <dest>
COPY . .                          # Copy everything
COPY requirements.txt .           # Copy single file
COPY src/ ./src/                  # Copy directory
COPY --chown=1000:1000 . .        # Copy with ownership


# ADD — Like COPY but supports URLs and auto-extracts tar files
# Use COPY instead of ADD unless you need URL/tar features
ADD https://example.com/file.tar.gz /tmp/
ADD myarchive.tar.gz /app/        # Auto-extracts archive


# RUN — Execute commands during build (creates new image layer)
# Shell form:
RUN apt-get update && apt-get install -y curl wget

# Exec form (preferred, no shell interpretation):
RUN ["apt-get", "install", "-y", "curl"]

# Best practice: chain commands to reduce layers
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        curl \
        wget \
        git \
    && rm -rf /var/lib/apt/lists/*   # Clean up to reduce image size


# USER — Set user for subsequent instructions and container runtime
# Always use non-root user for security!
RUN groupadd -r appuser && useradd -r -g appuser appuser
USER appuser
# Or by UID/GID:
USER 1000:1000


# EXPOSE — Document which port the container listens on
# NOTE: This does NOT actually publish the port. Use -p in docker run
EXPOSE 80
EXPOSE 8080/tcp
EXPOSE 53/udp


# VOLUME — Create a mount point for external storage
VOLUME ["/data"]
VOLUME /app/logs


# CMD — Default command when container starts
# Only the LAST CMD instruction takes effect
# Can be overridden by: docker run myimage <command>

# Shell form:
CMD python app.py

# Exec form (preferred):
CMD ["python", "app.py"]
CMD ["nginx", "-g", "daemon off;"]
CMD ["node", "server.js"]


# ENTRYPOINT — Sets the main process; cannot be overridden easily
# Use with CMD to allow default arguments
ENTRYPOINT ["python"]
CMD ["app.py"]
# docker run myimage = python app.py
# docker run myimage other.py = python other.py

# Override entrypoint: docker run --entrypoint bash myimage


# HEALTHCHECK — Tell Docker how to test container health
HEALTHCHECK --interval=30s --timeout=10s --start-period=5s --retries=3 \
    CMD curl -f http://localhost/ || exit 1

HEALTHCHECK NONE  # Disable inherited healthcheck


# SHELL — Override the default shell used for shell-form commands
SHELL ["/bin/bash", "-c"]          # Use bash (default on Linux is /bin/sh)
SHELL ["powershell", "-command"]   # For Windows containers


# STOPSIGNAL — Set signal sent to container to stop it
STOPSIGNAL SIGTERM


# ONBUILD — Trigger instructions for child images
# Only runs when image is used as base for another build
ONBUILD COPY . /app
ONBUILD RUN pip install -r requirements.txt
```

---

### 7.2 Build Commands

```bash
# Basic build (uses Dockerfile in current directory)
docker build -t myapp .

# Build with tag
docker build -t myapp:1.0 .
docker build -t myapp:latest -t myapp:1.0 .  # Multiple tags

# Build from different Dockerfile name/location
docker build -f ./docker/Dockerfile.prod -t myapp:prod .

# Build with build arguments
docker build --build-arg APP_VERSION=2.0 -t myapp .
docker build --build-arg ENV=production --build-arg PORT=3000 -t myapp .

# Build with no cache (force rebuild all layers)
docker build --no-cache -t myapp .

# Build and remove intermediate containers
docker build --rm -t myapp .

# Build for specific platform (cross-compilation)
docker build --platform linux/amd64 -t myapp .
docker build --platform linux/arm64 -t myapp .

# Build for multiple platforms
docker buildx build --platform linux/amd64,linux/arm64 -t myapp .

# Verbose output during build
docker build --progress=plain -t myapp .

# Squash all layers into one (experimental)
docker build --squash -t myapp .
```

---

### 7.3 Multi-Stage Builds

Multi-stage builds let you use one image to build and another (smaller) to run — keeping final images tiny.

```dockerfile
# ──────────────────────────────────────────
# Stage 1: Build Stage
# ──────────────────────────────────────────
FROM node:20-alpine AS builder

WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm ci --only=production

# Copy source and build
COPY . .
RUN npm run build


# ──────────────────────────────────────────
# Stage 2: Production Stage (final image)
# ──────────────────────────────────────────
FROM nginx:alpine AS production

# Copy only the built files from Stage 1
COPY --from=builder /app/dist /usr/share/nginx/html

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

**Result:** Final image is only ~25MB instead of ~1.2GB (the node:20 image)!

---

### 7.4 Complete Dockerfile Examples

#### Python Flask App
```dockerfile
FROM python:3.11-slim

WORKDIR /app

# Install dependencies first (cached layer if requirements don't change)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy source code
COPY . .

# Create non-root user
RUN adduser --disabled-password --gecos '' appuser
USER appuser

EXPOSE 5000

HEALTHCHECK --interval=30s --timeout=5s \
    CMD curl -f http://localhost:5000/health || exit 1

CMD ["python", "-m", "flask", "run", "--host=0.0.0.0"]
```

#### Node.js App
```dockerfile
FROM node:20-alpine

WORKDIR /app

COPY package*.json ./
RUN npm ci --only=production

COPY . .

RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser

EXPOSE 3000

CMD ["node", "server.js"]
```

#### Go App (Scratch image — tiny!)
```dockerfile
# Build stage
FROM golang:1.21-alpine AS builder
WORKDIR /app
COPY go.* ./
RUN go mod download
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build -o server .

# Final stage — empty image!
FROM scratch
COPY --from=builder /app/server /server
EXPOSE 8080
ENTRYPOINT ["/server"]
```

---

## 8. Docker Volumes

Volumes provide **persistent storage** that survives container restarts and removals.

### Types of Storage

```
┌─────────────────────────────────────────────────────┐
│                  Storage Types                       │
├────────────────┬────────────────┬───────────────────┤
│  Named Volumes │ Bind Mounts    │ tmpfs Mounts       │
│  (Managed by   │ (Your host     │ (In memory,        │
│   Docker)      │  filesystem)   │  not persisted)    │
└────────────────┴────────────────┴───────────────────┘
```

### Volume Commands

```bash
# Create a named volume
docker volume create mydata

# List volumes
docker volume ls

# Inspect volume (see location on host)
docker volume inspect mydata

# Remove volume
docker volume rm mydata

# Remove all unused volumes
docker volume prune

# Remove all volumes (DANGER!)
docker volume prune -a
```

### Using Volumes

```bash
# Named volume (Docker manages location)
docker run -d \
  --name mydb \
  -v mydata:/var/lib/mysql \
  mysql:8

# Bind mount (you specify host path)
docker run -d \
  -v /home/user/data:/app/data \
  myapp

# Bind mount with current directory (great for development!)
docker run -d \
  -v $(pwd):/app \
  -w /app \
  myapp

# Read-only bind mount
docker run -d \
  -v $(pwd)/config:/app/config:ro \
  myapp

# tmpfs mount (in-memory, lost on stop)
docker run -d \
  --tmpfs /app/cache:size=100m \
  myapp

# Multiple volumes
docker run -d \
  -v mydata:/data \
  -v myconfig:/config:ro \
  -v $(pwd)/logs:/logs \
  myapp
```

### Backup & Restore Volumes

```bash
# Backup a volume to tar file
docker run --rm \
  -v mydata:/data \
  -v $(pwd):/backup \
  ubuntu \
  tar czf /backup/mydata-backup.tar.gz -C /data .

# Restore volume from tar file
docker run --rm \
  -v mydata:/data \
  -v $(pwd):/backup \
  ubuntu \
  tar xzf /backup/mydata-backup.tar.gz -C /data
```

---

## 9. Docker Networking

### Network Types

| Type | Description | Use Case |
|------|-------------|----------|
| **bridge** | Default. Containers can communicate via container names | Single host apps |
| **host** | Container uses host's network directly | Performance-critical apps |
| **none** | No network access | Isolated processing |
| **overlay** | Multi-host networking (Docker Swarm) | Distributed apps |
| **macvlan** | Container gets its own MAC address | Legacy apps |

### Network Commands

```bash
# List networks
docker network ls

# Create a network
docker network create mynetwork
docker network create --driver bridge mynetwork
docker network create --subnet=172.20.0.0/16 mynetwork

# Inspect a network
docker network inspect mynetwork

# Connect container to network
docker network connect mynetwork mycontainer

# Disconnect container from network
docker network disconnect mynetwork mycontainer

# Remove a network
docker network rm mynetwork

# Remove unused networks
docker network prune
```

### Container Communication via Network

```bash
# Create a custom network
docker network create appnetwork

# Run containers on the same network (they can talk by name!)
docker run -d --name database --network appnetwork mysql:8
docker run -d --name webserver --network appnetwork myapp

# webserver can now reach database at hostname "database"
# e.g., mysql://database:3306/mydb

# Run container on multiple networks
docker run -d \
  --name myapp \
  --network frontend-net \
  myapp
docker network connect backend-net myapp
```

---

## 10. Docker Compose

Docker Compose lets you define and run **multi-container applications** using a single YAML file.

### 10.1 Install Docker Compose

```bash
# Docker Compose is included with Docker Desktop (Windows/macOS)

# For Linux (if not installed):
sudo apt-get install docker-compose-plugin

# Verify:
docker compose version

# Legacy standalone binary (if needed):
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" \
    -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

---

### 10.2 Compose File Full Reference

```yaml
# docker-compose.yml — Complete Reference

version: '3.8'  # Compose file format version

# ─────────────────────────────────────────
# SERVICES — Define each container
# ─────────────────────────────────────────
services:

  # ── Web Application ──
  web:
    image: nginx:latest              # Use existing image
    # OR build from Dockerfile:
    build:
      context: ./frontend            # Build context (directory)
      dockerfile: Dockerfile.prod    # Custom Dockerfile name
      args:                          # Build arguments
        APP_ENV: production
    
    container_name: my-web-app      # Custom container name
    
    ports:
      - "80:80"                      # host:container
      - "443:443"
      - "127.0.0.1:8080:8080"        # Bind to specific host IP
    
    environment:                     # Environment variables
      NODE_ENV: production
      PORT: 3000
    # OR use .env file:
    env_file:
      - .env
      - .env.production
    
    volumes:
      - ./html:/usr/share/nginx/html  # Bind mount
      - nginx_logs:/var/log/nginx     # Named volume
      - ./nginx.conf:/etc/nginx/nginx.conf:ro  # Read-only
    
    networks:
      - frontend
      - backend
    
    depends_on:                      # Start order
      db:
        condition: service_healthy   # Wait for healthcheck
      redis:
        condition: service_started
    
    restart: unless-stopped          # Restart policy
    # Options: no, always, on-failure, unless-stopped
    
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost/health"]
      interval: 30s
      timeout: 10s
      retries: 3
      start_period: 40s
    
    deploy:                          # Resource limits
      resources:
        limits:
          cpus: '0.5'
          memory: 512M
        reservations:
          memory: 256M
    
    logging:
      driver: "json-file"
      options:
        max-size: "10m"
        max-file: "3"
    
    labels:
      - "com.example.description=My web app"
      - "com.example.version=1.0"
    
    command: ["nginx", "-g", "daemon off;"]   # Override CMD
    entrypoint: ["./entrypoint.sh"]           # Override ENTRYPOINT
    
    stdin_open: true                 # docker run -i
    tty: true                        # docker run -t
    
    working_dir: /app                # Working directory
    user: "1000:1000"                # User to run as

  # ── Database ──
  db:
    image: mysql:8.0
    container_name: mysql-db
    environment:
      MYSQL_ROOT_PASSWORD: ${DB_ROOT_PASSWORD}
      MYSQL_DATABASE: myapp
      MYSQL_USER: appuser
      MYSQL_PASSWORD: ${DB_PASSWORD}
    volumes:
      - mysql_data:/var/lib/mysql
      - ./sql/init.sql:/docker-entrypoint-initdb.d/init.sql:ro
    ports:
      - "3306:3306"
    networks:
      - backend
    healthcheck:
      test: ["CMD", "mysqladmin", "ping", "-h", "localhost"]
      interval: 10s
      timeout: 5s
      retries: 5
    restart: always

  # ── Redis Cache ──
  redis:
    image: redis:7-alpine
    container_name: my-redis
    command: redis-server --requirepass ${REDIS_PASSWORD}
    volumes:
      - redis_data:/data
    ports:
      - "6379:6379"
    networks:
      - backend
    restart: unless-stopped

  # ── Adminer (Database UI) ──
  adminer:
    image: adminer
    ports:
      - "8080:8080"
    networks:
      - backend
    depends_on:
      - db
    profiles:                        # Only start with: docker compose --profile tools up
      - tools

# ─────────────────────────────────────────
# VOLUMES — Named volumes
# ─────────────────────────────────────────
volumes:
  mysql_data:                        # Docker-managed volume
    driver: local
  redis_data:
  nginx_logs:
  external_data:
    external: true                   # Volume created outside Compose

# ─────────────────────────────────────────
# NETWORKS
# ─────────────────────────────────────────
networks:
  frontend:
    driver: bridge
  backend:
    driver: bridge
    internal: true                   # No external access (isolated)
  external_network:
    external: true                   # Network created outside Compose
```

---

### 10.3 Docker Compose Commands

```bash
# Start all services (build if needed)
docker compose up

# Start in detached mode (background)
docker compose up -d

# Start only specific services
docker compose up -d web redis

# Build images before starting
docker compose up --build

# Force rebuild even if unchanged
docker compose up --build --force-recreate

# Scale a service to N replicas
docker compose up -d --scale web=3

# Stop all services
docker compose down

# Stop and remove volumes too (DANGER: deletes data!)
docker compose down -v

# Stop and remove images too
docker compose down --rmi all

# List running services
docker compose ps

# List all services (including stopped)
docker compose ps -a

# View logs
docker compose logs
docker compose logs -f             # Follow/tail logs
docker compose logs -f web         # Logs for specific service
docker compose logs --tail=50      # Last 50 lines

# Execute command in service
docker compose exec web bash
docker compose exec db mysql -u root -p

# Run a one-off command
docker compose run --rm web python manage.py migrate
docker compose run --rm web sh

# Pull latest images
docker compose pull

# Build images only (don't start)
docker compose build
docker compose build web           # Build specific service
docker compose build --no-cache    # Rebuild without cache

# Restart services
docker compose restart
docker compose restart web

# Stop without removing
docker compose stop
docker compose stop web

# Start stopped services
docker compose start

# Pause/unpause
docker compose pause
docker compose unpause

# See config (merged & resolved)
docker compose config

# See which images are used
docker compose images

# Check Compose file version
docker compose version

# Use specific compose file
docker compose -f docker-compose.prod.yml up -d

# Use multiple compose files (merged)
docker compose -f docker-compose.yml -f docker-compose.override.yml up -d

# Use profiles
docker compose --profile tools up -d
```

---

## 11. Deploying a Website with Docker

### 11.1 Deploy a Static HTML Website

**Project structure:**
```
mywebsite/
├── index.html
├── style.css
├── script.js
└── Dockerfile
```

**Dockerfile:**
```dockerfile
FROM nginx:alpine

# Copy website files to nginx's default serve directory
COPY . /usr/share/nginx/html

# Optional: Custom nginx config
# COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
```

**Deploy:**
```bash
cd mywebsite

# Build the image
docker build -t mywebsite:latest .

# Run it!
docker run -d \
  --name mywebsite \
  -p 80:80 \
  --restart unless-stopped \
  mywebsite:latest

# Visit http://localhost
```

**Without Dockerfile (one-liner!):**
```bash
docker run -d \
  --name mywebsite \
  -p 80:80 \
  -v $(pwd):/usr/share/nginx/html:ro \
  nginx:alpine
```

---

### 11.2 Deploy a React App

**Project structure:**
```
my-react-app/
├── public/
├── src/
├── package.json
└── Dockerfile
```

**Dockerfile (Multi-stage):**
```dockerfile
# Stage 1: Build
FROM node:20-alpine AS builder

WORKDIR /app

COPY package*.json ./
RUN npm ci

COPY . .
RUN npm run build

# Stage 2: Serve with Nginx
FROM nginx:alpine

# Copy built React app
COPY --from=builder /app/build /usr/share/nginx/html

# nginx config to handle React Router (client-side routing)
RUN echo 'server {
    listen 80;
    location / {
        root /usr/share/nginx/html;
        index index.html index.htm;
        try_files $uri $uri/ /index.html;
    }
}' > /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

**Deploy:**
```bash
# Build
docker build -t my-react-app .

# Run
docker run -d \
  --name react-app \
  -p 3000:80 \
  --restart unless-stopped \
  my-react-app

# Visit http://localhost:3000
```

---

### 11.3 Deploy a Python Flask App

**Project structure:**
```
flask-app/
├── app.py
├── requirements.txt
├── templates/
├── static/
└── Dockerfile
```

**app.py:**
```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def home():
    return '<h1>Hello from Docker + Flask!</h1>'

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
```

**requirements.txt:**
```
flask==3.0.0
gunicorn==21.2.0
```

**Dockerfile:**
```dockerfile
FROM python:3.11-slim

WORKDIR /app

# Install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy app source
COPY . .

# Non-root user for security
RUN adduser --disabled-password appuser
USER appuser

EXPOSE 5000

# Use gunicorn for production (not flask dev server)
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "--workers", "4", "app:app"]
```

**Deploy:**
```bash
docker build -t flask-app .

docker run -d \
  --name flask-app \
  -p 5000:5000 \
  -e FLASK_ENV=production \
  --restart unless-stopped \
  flask-app

# Visit http://localhost:5000
```

---

### 11.4 Deploy a Node.js App

**server.js:**
```javascript
const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;

app.get('/', (req, res) => {
  res.send('<h1>Hello from Docker + Node.js!</h1>');
});

app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
```

**Dockerfile:**
```dockerfile
FROM node:20-alpine

WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm ci --only=production

# Copy source
COPY . .

# Security: non-root user
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser

EXPOSE 3000

HEALTHCHECK --interval=30s --timeout=3s \
  CMD wget -qO- http://localhost:3000/health || exit 1

CMD ["node", "server.js"]
```

**Deploy:**
```bash
docker build -t node-app .

docker run -d \
  --name node-app \
  -p 3000:3000 \
  -e NODE_ENV=production \
  --restart unless-stopped \
  node-app
```

---

### 11.5 Deploy with Nginx Reverse Proxy

Real-world setup: Multiple apps behind one Nginx reverse proxy.

**docker-compose.yml:**
```yaml
version: '3.8'

services:
  nginx:
    image: nginx:alpine
    container_name: nginx-proxy
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./nginx/nginx.conf:/etc/nginx/nginx.conf:ro
      - ./nginx/certs:/etc/nginx/certs:ro
    depends_on:
      - flask-app
      - node-app
    networks:
      - webnet
    restart: unless-stopped

  flask-app:
    build: ./flask-app
    container_name: flask-app
    expose:
      - "5000"       # Only expose inside Docker network
    environment:
      FLASK_ENV: production
    networks:
      - webnet
    restart: unless-stopped

  node-app:
    build: ./node-app
    container_name: node-app
    expose:
      - "3000"
    environment:
      NODE_ENV: production
    networks:
      - webnet
    restart: unless-stopped

networks:
  webnet:
    driver: bridge
```

**nginx/nginx.conf:**
```nginx
events {
    worker_connections 1024;
}

http {
    upstream flask {
        server flask-app:5000;
    }

    upstream node {
        server node-app:3000;
    }

    server {
        listen 80;

        location /api/ {
            proxy_pass http://flask;
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
        }

        location / {
            proxy_pass http://node;
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
        }
    }
}
```

```bash
# Start everything
docker compose up -d

# Check logs
docker compose logs -f nginx
```

---

## 12. Docker Registry

### 12.1 Docker Hub

```bash
# Create account at: https://hub.docker.com

# Login
docker login
docker login -u yourusername

# Logout
docker logout

# Tag your image for Docker Hub
docker tag myapp:latest yourusername/myapp:latest
docker tag myapp:latest yourusername/myapp:v1.0.0

# Push to Docker Hub
docker push yourusername/myapp:latest
docker push yourusername/myapp:v1.0.0

# Pull from Docker Hub
docker pull yourusername/myapp:latest
```

---

### 12.2 Private Registry

```bash
# Run your own registry
docker run -d \
  --name registry \
  -p 5000:5000 \
  -v registry_data:/var/lib/registry \
  registry:2

# Tag for private registry
docker tag myapp:latest localhost:5000/myapp:latest

# Push
docker push localhost:5000/myapp:latest

# Pull
docker pull localhost:5000/myapp:latest

# List repositories in registry
curl http://localhost:5000/v2/_catalog
```

---

### 12.3 GitHub Container Registry

```bash
# Login with GitHub Personal Access Token
echo $GITHUB_TOKEN | docker login ghcr.io -u USERNAME --password-stdin

# Tag image
docker tag myapp:latest ghcr.io/yourusername/myapp:latest

# Push
docker push ghcr.io/yourusername/myapp:latest

# Pull
docker pull ghcr.io/yourusername/myapp:latest
```

---

## 13. Docker Swarm — Orchestration

Docker Swarm turns multiple Docker hosts into a single virtual Docker host.

```bash
# Initialize Swarm (on manager node)
docker swarm init --advertise-addr <MANAGER-IP>

# Get join token for workers
docker swarm join-token worker
docker swarm join-token manager

# Join as worker (run on worker machine)
docker swarm join --token <TOKEN> <MANAGER-IP>:2377

# List nodes
docker node ls

# Promote worker to manager
docker node promote worker-node

# Deploy a stack (like Compose for Swarm)
docker stack deploy -c docker-compose.yml mystack

# List stacks
docker stack ls

# List services in stack
docker stack services mystack

# Scale a service
docker service scale mystack_web=5

# Update a service
docker service update --image myapp:v2 mystack_web

# View service logs
docker service logs mystack_web

# Remove a stack
docker stack rm mystack

# Leave swarm (on worker)
docker swarm leave

# Force disband swarm (on manager)
docker swarm leave --force
```

---

## 14. Environment Variables & Secrets

### Using .env Files

```bash
# .env file (same directory as docker-compose.yml)
DB_PASSWORD=mysecretpassword
API_KEY=abc123xyz
PORT=3000
```

```yaml
# docker-compose.yml — variables auto-loaded from .env
services:
  app:
    image: myapp
    environment:
      - DB_PASSWORD=${DB_PASSWORD}
      - API_KEY=${API_KEY}
    ports:
      - "${PORT}:3000"
```

### Docker Secrets (Swarm)

```bash
# Create a secret
echo "mysecretpassword" | docker secret create db_password -

# Create from file
docker secret create ssl_cert ./certificate.pem

# List secrets
docker secret ls

# Inspect secret metadata
docker secret inspect db_password

# Remove secret
docker secret rm db_password

# Use in service (secret mounted at /run/secrets/db_password)
docker service create \
  --name myapp \
  --secret db_password \
  myapp:latest
```

```yaml
# docker-compose.yml with secrets
version: '3.8'

services:
  app:
    image: myapp
    secrets:
      - db_password
    environment:
      DB_PASSWORD_FILE: /run/secrets/db_password

secrets:
  db_password:
    external: true
```

---

## 15. Docker Security Best Practices

```dockerfile
# ✅ BEST PRACTICE 1: Always use specific image tags, not 'latest'
FROM python:3.11.7-slim   # Not: FROM python:latest

# ✅ BEST PRACTICE 2: Run as non-root user
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser

# ✅ BEST PRACTICE 3: Use .dockerignore to exclude sensitive files
```

**.dockerignore:**
```
.git
.env
.env.*
*.pem
*.key
node_modules
__pycache__
*.pyc
.DS_Store
*.log
secrets/
```

```bash
# ✅ BEST PRACTICE 4: Scan images for vulnerabilities
docker scout cves myapp:latest
docker scan myapp:latest   # Older command

# ✅ BEST PRACTICE 5: Use read-only filesystem
docker run --read-only myapp

# ✅ BEST PRACTICE 6: Drop Linux capabilities
docker run --cap-drop ALL --cap-add NET_BIND_SERVICE myapp

# ✅ BEST PRACTICE 7: No privileged containers
# NEVER do this unless absolutely required:
# docker run --privileged myapp   ← VERY DANGEROUS

# ✅ BEST PRACTICE 8: Use security options
docker run --security-opt no-new-privileges myapp

# ✅ BEST PRACTICE 9: Limit resources
docker run --memory="256m" --cpus="0.5" myapp

# ✅ BEST PRACTICE 10: Use multi-stage builds to minimize attack surface
# (Shown in section 7.3)

# ✅ BEST PRACTICE 11: Set user namespace remapping (in daemon.json)
# /etc/docker/daemon.json
{
  "userns-remap": "default"
}
```

---

## 16. Docker Resource Management

```bash
# ── Memory ──
docker run -m 512m myapp               # Max 512MB memory
docker run --memory="1g" myapp         # Max 1GB memory
docker run --memory-swap="1g" myapp    # Including swap
docker run --memory-reservation="256m" myapp  # Soft limit

# ── CPU ──
docker run --cpus="1.5" myapp          # 1.5 CPU cores
docker run --cpu-shares=512 myapp      # Relative CPU weight (default 1024)
docker run --cpuset-cpus="0,2" myapp   # Use only CPU 0 and 2

# ── Block I/O ──
docker run --blkio-weight=500 myapp    # I/O weight (default 500, range 10-1000)

# ── PIDs ──
docker run --pids-limit=100 myapp      # Max 100 processes

# ── Update running container limits ──
docker update --memory="1g" mycontainer
docker update --cpus="2" mycontainer

# ── View resource usage ──
docker stats                           # Live stats (all containers)
docker stats --no-stream --format "table {{.Container}}\t{{.CPUPerc}}\t{{.MemUsage}}"
```

---

## 17. Docker Prune & Cleanup

```bash
# ── Remove stopped containers ──
docker container prune

# ── Remove unused images ──
docker image prune          # Remove dangling images
docker image prune -a       # Remove all unused images

# ── Remove unused volumes ──
docker volume prune

# ── Remove unused networks ──
docker network prune

# ── NUCLEAR OPTION: Remove everything unused ──
docker system prune
docker system prune -a                   # Also removes unused images
docker system prune -a --volumes         # Also removes volumes (DANGER!)
docker system prune -a --volumes -f      # Skip confirmation prompt

# ── Check disk usage ──
docker system df
docker system df -v         # Verbose, shows every object

# ── Remove specific resources ──
docker rm $(docker ps -aq -f status=exited)   # All exited containers
docker rmi $(docker images -q -f dangling=true) # All dangling images
```

---

## 18. Docker Troubleshooting

### Common Issues & Fixes

```bash
# ── Container exits immediately ──
docker logs mycontainer        # Check logs for errors
docker run -it myimage bash    # Run interactively to debug

# ── Port already in use ──
# Error: Bind for 0.0.0.0:80 failed: port is already allocated
lsof -i :80                    # Find what's using port 80
kill -9 <PID>                  # Kill that process
# Or use a different port: -p 8080:80

# ── Cannot connect to Docker daemon ──
sudo systemctl start docker    # Start daemon (Linux)
sudo systemctl status docker   # Check daemon status
sudo usermod -aG docker $USER  # Add user to docker group
newgrp docker                  # Apply group change

# ── Image build fails ──
docker build --no-cache .      # Force rebuild
docker build --progress=plain . # Verbose output to see exact error

# ── Container can't reach internet ──
docker run --rm ubuntu curl https://google.com   # Test network
# Fix: check /etc/docker/daemon.json for DNS settings
# Add: { "dns": ["8.8.8.8", "8.8.4.4"] }

# ── Out of disk space ──
docker system df               # Check usage
docker system prune -a         # Clean up
df -h                          # Check host disk space

# ── Inspect container filesystem ──
docker exec -it mycontainer sh    # Get shell
docker export mycontainer | tar t # List all files

# ── Copy config from container to inspect ──
docker cp mycontainer:/etc/nginx/nginx.conf ./nginx.conf

# ── Check container exit code ──
docker inspect mycontainer --format='{{.State.ExitCode}}'

# ── Debug with temporary container ──
docker run --rm -it \
  --network container:mycontainer \
  nicolaka/netshoot          # Network debugging toolkit
```

### Useful Debug Images

```bash
# BusyBox — tiny swiss-army knife
docker run --rm -it busybox sh

# Alpine — minimal linux
docker run --rm -it alpine sh

# Netshoot — network debugging
docker run --rm -it nicolaka/netshoot

# cURL
docker run --rm curlimages/curl https://google.com
```

---

## 19. Advanced Docker Tips

### Docker BuildKit (Faster Builds)

```bash
# Enable BuildKit
export DOCKER_BUILDKIT=1
docker build -t myapp .

# Or set in daemon.json:
# { "features": { "buildkit": true } }

# BuildKit cache mounting (super fast Python/Node builds!)
```

```dockerfile
# syntax=docker/dockerfile:1
FROM python:3.11-slim

# Cache pip downloads between builds!
RUN --mount=type=cache,target=/root/.cache/pip \
    pip install -r requirements.txt

# SSH forwarding during build (for private git repos)
RUN --mount=type=ssh \
    pip install git+ssh://git@github.com/private/repo.git
```

### Docker Context (Remote Docker Hosts)

```bash
# Create a context for remote host
docker context create remote-server \
  --docker "host=ssh://user@192.168.1.100"

# List contexts
docker context ls

# Switch context (now commands run on remote host!)
docker context use remote-server

# Switch back
docker context use default

# Run one command on remote host
docker --context remote-server ps
```

### Watching Files with `--watch` (Compose)

```yaml
# docker-compose.yml — live reload for development!
services:
  web:
    build: .
    develop:
      watch:
        - action: sync
          path: ./src
          target: /app/src
        - action: rebuild
          path: requirements.txt
```

```bash
docker compose watch   # Start with file watching
```

### Multi-Platform Builds

```bash
# Setup buildx for multi-platform
docker buildx create --name multiplatform --use

# Build for multiple architectures
docker buildx build \
  --platform linux/amd64,linux/arm64,linux/arm/v7 \
  -t yourusername/myapp:latest \
  --push \           # Push directly to registry
  .
```

### Limiting Image Size Tricks

```dockerfile
# Use Alpine-based images
FROM python:3.11-alpine   # ~50MB vs ~900MB for python:3.11

# Use slim variants
FROM python:3.11-slim     # ~125MB

# Clean up in same RUN layer
RUN apt-get update \
    && apt-get install -y curl \
    && rm -rf /var/lib/apt/lists/*   # MUST be in same layer!

# Use --no-install-recommends
RUN apt-get install -y --no-install-recommends curl

# .dockerignore everything you don't need
```

---

## 20. Quick Reference Cheat Sheet

```
╔══════════════════════════════════════════════════════════════════╗
║                    🐳 DOCKER CHEAT SHEET                         ║
╠══════════════════════════════════════════════════════════════════╣
║  IMAGES                          CONTAINERS                       ║
║  docker pull <img>               docker run -d -p 8080:80 <img>  ║
║  docker images                   docker ps                        ║
║  docker rmi <img>                docker ps -a                     ║
║  docker build -t <name> .        docker stop <ctr>                ║
║  docker push <img>               docker start <ctr>               ║
║  docker tag <img> <new>          docker rm <ctr>                  ║
║  docker inspect <img>            docker rm -f <ctr>               ║
║  docker history <img>            docker logs -f <ctr>             ║
║                                  docker exec -it <ctr> bash       ║
╠══════════════════════════════════════════════════════════════════╣
║  VOLUMES                         NETWORKS                         ║
║  docker volume create <v>        docker network create <n>        ║
║  docker volume ls                docker network ls                ║
║  docker volume rm <v>            docker network inspect <n>       ║
║  docker volume prune             docker network connect <n> <ctr> ║
╠══════════════════════════════════════════════════════════════════╣
║  DOCKER COMPOSE                  CLEANUP                          ║
║  docker compose up -d            docker system prune -a           ║
║  docker compose down             docker container prune           ║
║  docker compose logs -f          docker image prune -a            ║
║  docker compose ps               docker volume prune              ║
║  docker compose exec web bash    docker system df                 ║
║  docker compose build            docker network prune             ║
╚══════════════════════════════════════════════════════════════════╝
```

### Common Run Flags Quick Reference

| Flag | Full Form | Description |
|------|-----------|-------------|
| `-d` | `--detach` | Run in background |
| `-it` | `--interactive --tty` | Interactive terminal |
| `-p` | `--publish` | Map ports `host:container` |
| `-v` | `--volume` | Mount volume `host:container` |
| `-e` | `--env` | Set environment variable |
| `--name` | `--name` | Assign container name |
| `--rm` | `--rm` | Auto-remove on stop |
| `--network` | `--network` | Connect to network |
| `-m` | `--memory` | Memory limit |
| `--cpus` | `--cpus` | CPU limit |
| `--restart` | `--restart` | Restart policy |
| `-u` | `--user` | Run as user |
| `-w` | `--workdir` | Working directory |
| `--env-file` | `--env-file` | Load env from file |

---

## 🎓 Learning Path

```
Beginner                    Intermediate              Expert / Legend
    │                            │                         │
    ▼                            ▼                         ▼
docker run hello-world      Dockerfile mastery        Docker Swarm
docker pull/push            Multi-stage builds        Kubernetes (K8s)
docker ps / logs            Docker Compose            BuildKit advanced
Basic port mapping          Volumes & Networks        Multi-arch builds
                            Environment management    Custom registries
                            Security practices        CI/CD integration
                            Healthchecks              Service meshes
```

---

## 📖 Official Resources

| Resource | URL |
|----------|-----|
| Docker Documentation | https://docs.docker.com |
| Docker Hub | https://hub.docker.com |
| Docker Compose Spec | https://compose-spec.io |
| Play with Docker (Free Lab) | https://labs.play-with-docker.com |
| Docker GitHub | https://github.com/docker |
| Dockerfile Reference | https://docs.docker.com/engine/reference/builder |

---

## 🤝 Contributing

Found an error or want to add more content? Feel free to:
1. Fork this repository
2. Create a feature branch: `git checkout -b add-kubernetes-section`
3. Commit changes: `git commit -m "Add Kubernetes comparison section"`
4. Push: `git push origin add-kubernetes-section`
5. Open a Pull Request

---

*Made with ❤️ for the developer community | Star ⭐ this repo if it helped you!*

---

> **Next Steps After Mastering Docker:**
> - **Kubernetes (K8s)** — Container orchestration at massive scale
> - **Docker + CI/CD** — GitHub Actions, GitLab CI, Jenkins
> - **Docker + Cloud** — AWS ECS, Google Cloud Run, Azure Container Instances
> - **Service Mesh** — Istio, Linkerd for microservices
