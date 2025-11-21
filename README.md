# Eaglercraft Docker

A simple Docker-based setup for running both the **EaglercraftX 1.8.8 Offline Client** and the **Eaglercraft Paper Server**.

This repository includes:

* **client/Dockerfile** – Builds the Eaglercraft web client
* **server/Dockerfile** – Builds and runs the Eaglercraft server (Paper-based)
* **compose.yml** – Deploys both services together with a single command

---

## 📦 Features

* Fully containerized Eaglercraft environment
* Zero manual configuration—just build and run
* Automatic hosting of the web client
* Server and client run on separate containers
* Ready for LAN or public hosting depending on your environment

---

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/prmiguel/eaglercraft-docker.git
cd eaglercraft-docker
```

### 2. Start Everything

Use Docker Compose to build and run both the Eaglercraft server and client:

```bash
docker compose up -d
```

### 3. Access the Client

Open your browser and go to:

```
http://localhost:80
```

(Port may vary if you configured differently.)

### 4. Connect to the Server

Inside the client, connect using:

```
ws://localhost:25565
```

---

## 🖥️ Client Details

This Dockerfile hosts the **EaglercraftX 1.8.8 Offline** client, downloaded from:

**Eaglercraft Client Download:**
[https://eaglercraft.com/p/downloads/](https://eaglercraft.com/p/downloads/)

The client is served via a lightweight web nginx server and exposed on **port 80** by default.

---

## 🖧 Server Details

The server container builds and runs the official **Eaglercraft Paper Server**, sourced from:

**Eaglercraft Paper Server:**
[https://github.com/Eaglercraft-Templates/Eaglercraft-Server-Paper](https://github.com/Eaglercraft-Templates/Eaglercraft-Server-Paper)

It exposes **port 25565** for WebSocket connections.
The server world data is stored inside the container unless you mount a volume (recommended).

---

## ⚙️ docker compose.yml Overview

The compose file:

* Builds both Docker images
* Exposes client and server ports
* Automatically handles networking between containers
* Enables one-command deployment

---

## 🔧 Rebuilding Containers

If you modify any Dockerfile, rebuild using:

```bash
docker compose up -d --build
```

---

## 🙌 Credits

* **EaglercraftX Client** – © LAX1DUDE
* **Eaglercraft Paper Server Template** – [https://github.com/Eaglercraft-Templates/Eaglercraft-Server-Paper](https://github.com/Eaglercraft-Templates/Eaglercraft-Server-Paper)
* Docker configuration written by this repository’s authors

---

If you'd like, I can also generate badges, screenshots, or an ASCII-style project logo for the top of the README.
