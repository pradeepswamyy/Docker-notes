# <img src="https://raw.githubusercontent.com/docker/cli/master/docs/static_files/docker-logo.png" width="50" align="center"> Docker Fundamentals

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)


---

## 🟦 1. The Problem: Environmental Inconsistency
Before containerization, **"It works on my machine"** was a primary bottleneck. Differences in OS versions and libraries led to frequent deployment failures.
> [!IMPORTANT]
> **Analogy:** Think of it as a recipe that tastes different in every kitchen.

---

## 🟦 2. Docker Architecture & Core Components

### 🐳 The Docker Daemon
The Docker Daemon is a background service managing Docker objects. It sits on top of the Host OS kernel, making it lightweight compared to Virtual Machines.
* **Efficiency:** It shares the host's OS kernel, significantly reducing RAM and CPU overhead.

### 📝 Dockerfile (Build Instructions)
A `Dockerfile` is a text document containing all commands to assemble an image.
* **Key Instructions:** `FROM`, `COPY`, `RUN`, and `CMD`.
> [!NOTE]
> **Analogy:** This is your automated recipe card that ensures the exact same result every time.

### 📦 Docker Image (The Template)
An Image is a read-only, immutable snapshot including application code, runtime, and libraries.
* **Immutability:** Once built, an image cannot be changed; updates require a new build.
> [!TIP]
> **Analogy:** It is like a sealed, dry-ingredient packet ready for distribution.

### 🏪 Docker Registry (The Distribution Hub)
A Registry is a server-side application that stores and distributes Docker images.
* **Examples:** Docker Hub (Public), Amazon ECR, or Azure ACR (Private).
> [!NOTE]
> **Analogy:** The central supermarket shelf where images are stored and shared.

### 🏗️ Docker Container (The Runtime)
A Container is a live, running instance of an image. It is isolated from the host, ensuring process independence.
> [!TIP]
> **Analogy:** The final ready-to-eat meal served exactly as the recipe intended.

---

## 🟦 3. Essential Command Reference

| Command Syntax | Technical Purpose | Example |
| :--- | :--- | :--- |
| `docker build -t <name>:<tag> .` | Compiles a Dockerfile into an Image. | `docker build -t web-app:v1 .` |
| `docker pull <image>:<tag>` | Retrieves an image from a registry. | `docker pull node:18-alpine` |
| `docker run -d -p <h>:<c> <img>` | Starts a container in detached mode. | `docker run -d -p 80:80 nginx` |
| `docker ps -a` | Displays status of all containers. | `docker ps -a` |
| `docker exec -it <name> <cmd>` | Runs a process inside a container. | `docker exec -it api-srv bash` |
| `docker logs -f <name>` | Streams container console output. | `docker logs -f api-srv` |
| `docker stop <name>` | Gracefully shuts down a container. | `docker stop api-srv` |
| `docker rm <name>` | Removes a stopped container. | `docker rm api-srv` |
| `docker rmi <image>` | Deletes a local image from storage. | `docker rmi web-app:v1` |
| `docker push <repo>:<tag>` | Uploads image to a remote registry. | `docker push user/app:v1` |

---

