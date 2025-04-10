# Open WebUI with LiteLLM Integration

## Overview
This Docker Compose configuration sets up Open WebUI with LiteLLM for an integrated AI chat interface and model management system.

## Prerequisites
- Docker
- Docker Compose
- NVIDIA GPU (optional, for CUDA support)
- NVIDIA Container Toolkit (if using GPU)

## Services
### Open WebUI
- Image: `ghcr.io/open-webui/open-webui:cuda`
- Port: 3000
- GPU-enabled
- Persistent data volume

### LiteLLM
- Image: `ghcr.io/berriai/litellm:main-latest`
- Port: 4000
- Configurable via `litellm.env`

## Configuration

### Environment Variables
Create a `litellm.env` file with the following structure:
```
LITELLM_MASTER_KEY=your_master_key
LITELLM_SALT_KEY=your_salt_key
DATABASE_URL=postgres://username:password@hostname:5432/dbname
PORT=4000
STORE_MODEL_IN_DB=True
```

## Installation

1. Clone the repository
2. Configure `litellm.env`
3. Run:
```bash
docker-compose up -d
```

## Accessing Services
- Open WebUI: http://localhost:3000
- LiteLLM API: http://localhost:4000

## Notes
- Ensure GPU drivers and NVIDIA Container Toolkit are installed for CUDA support
- Customize ports and configurations as needed