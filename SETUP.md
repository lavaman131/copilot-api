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

## Claude Code Settings

Modify your Claude Code settings to use the proxy.

Use the following configuration in your `~/.claude/settings.json` file:

```json
{
  "env": {
    "ANTHROPIC_BASE_URL": "http://localhost:4141",
    "ANTHROPIC_AUTH_TOKEN": "dummy",
    "ANTHROPIC_MODEL": "claude-opus-4.5",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "claude-opus-4.5",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "claude-sonnet-4.5",
    "ANTHROPIC_SMALL_FAST_MODEL": "claude-haiku-4.5",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "claude-haiku-4.5",
    "DISABLE_NON_ESSENTIAL_MODEL_CALLS": "1",
    "CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC": "1"
  },
  "includeCoAuthoredBy": false,
  "permissions": {
    "defaultMode": "bypassPermissions"
  },
  "model": "opus",
  "enableAllProjectMcpServers": true,
  "enabledPlugins": {},
  "autoUpdatesChannel": "latest"
}
```