# MultiClaw MLflow

**MultiClaw MLflow** is the model lifecycle lane for AIML Solutions.

It provides experiment tracking, artifact/version management, and reproducible training workflows for PyTorch + Hugging Face models used across MultiClaw departments.

## What this repo delivers

- MLflow tracking server and registry
- PostgreSQL backend for metadata
- MinIO (S3-compatible) artifact storage
- Baseline training script demonstrating MLflow + HF + PyTorch logging
- Documentation for architecture and operational runbook

## Current status

- Docker stack validated (mlflow-db, mlflow-minio, mlflow-tracking)
- Tracking UI reachable on `http://localhost:5000`
- Artifact store verified (`mlflow-artifacts` bucket)
- Sample run completed and logged successfully

## Quick start

```bash
cd infra
cp .env.example .env
docker compose up -d

# run sample experiment
MLFLOW_TRACKING_URI=http://127.0.0.1:5000 \
MLFLOW_S3_ENDPOINT_URL=http://127.0.0.1:9000 \
AWS_ACCESS_KEY_ID=minio \
AWS_SECRET_ACCESS_KEY=minio_dev_change_me \
python3 services/training/sample_mlflow_hf_torch_run.py
```

## Repository layout

- `infra/` — compose stack + env template
- `services/training/` — training experiment scripts
- `docs/architecture.md` — system architecture
- `docs/runbook.md` — operational guide
- `docs/ROADMAP.md` — near/mid-term milestones

## License

MIT — see [LICENSE](LICENSE).
