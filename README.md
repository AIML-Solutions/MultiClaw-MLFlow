# MLFlow Lab (MultiClaw)

Open-source ML platform lane for experiment tracking, model registry, and reproducible training with PyTorch + Hugging Face.

## Mission
Build a practical ML stack that sits alongside QuantConnect/LEAN workflows and can share infra patterns with MultiClaw AgentOps.

## Stack (initial)
- MLflow Tracking + Model Registry
- PostgreSQL backend store
- MinIO artifact store (S3-compatible)
- PyTorch + HF Transformers for training/inference experiments
- Optional GraphQL read layer for experiment metadata

## Layout
- `infra/` Docker Compose and environment files
- `services/training/` training pipeline stubs
- `services/data/` dataset ingestion/prep stubs
- `services/registry/` model promotion/evaluation stubs
- `docs/` architecture + runbook

## First actions
1. Configure `.env` from `.env.example`.
2. Start infra with Docker Compose.
3. Point local MLflow client to tracking URI.
4. Run a baseline training experiment and log metrics/artifacts.
