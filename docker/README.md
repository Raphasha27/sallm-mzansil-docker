# Running MzansiLM Locally with Docker

This Docker Compose setup runs MzansiLM-compatible models locally using Ollama.

## Quick Start

```bash
docker compose up -d
```

Ollama will be available at `http://localhost:11434`.

## Pulling a Model

```bash
curl http://localhost:11434/api/pull -d '{"name": "mzansilm:latest"}'
```

## Usage

```python
import requests

response = requests.post("http://localhost:11434/api/generate", json={
    "model": "mzansilm:latest",
    "prompt": "Sawubona! Ungakwazi ukungisiza?",
    "stream": False
})
print(response.json()["response"])
```

## Requirements

- Docker Desktop 4.0+ or Docker Engine 24.0+
- At least 4GB RAM for 3B models, 8GB for 7B models