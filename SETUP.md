# Setup

## Prerequisites

Before you begin, ensure you have the following installed on your machine:
- Docker Desktop: [Install Docker Desktop](https://docs.docker.com/get-docker/)
- This repo: [Clone the Repository]:

```bash
git clone https://github.com/lavaman131/copilot-api.git
```

## Build the Docker Image

```bash
cd copilot-api
docker build -t copilot-api .
```

## Run the Docker Container

On Windows:

```powershell
docker run -d --restart unless-stopped -p 127.0.0.1:4141:4141 -v "$env:USERPROFILE/copilot-data:/root/.local/share/copilot-api" copilot-api
```

On macOS/Linux:

```bash
docker run -d --restart unless-stopped -p 127.0.0.1:4141:4141 -v "$HOME/copilot-data:/root/.local/share/copilot-api" copilot-api
```