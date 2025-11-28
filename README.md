# FalconOps Zero-Cost Platform – Infra

This repository contains the **infrastructure and GitOps layer** for the FalconOps Zero-Cost Platform:

- Local k3d cluster (WSL2 / Ubuntu)
- GitOps with Argo CD
- Observability stack (Prometheus, Grafana, Loki)
- OpenSearch + Dashboards
- DevSecOps tooling (Kyverno, Trivy, Checkov)
- Terraform modules for OCI Always Free

## Repositories

- **falcon-infra** – this repo, infra + GitOps + policies
- **falcon-app** – demo application, Dockerfile, app CI

## Structure

- `k8s/base/` – core manifests (namespaces, Argo CD, monitoring, logging, etc.).
- `k8s/apps/` – application-specific manifests (namespaces, services, ingress, etc.).
- `argo/apps/` – Argo CD Application / ApplicationSet definitions.
- `helm/charts/` – custom Helm charts (if needed).
- `infra/oci/` – Terraform configs for OCI Always Free.
- `infra/modules/` – reusable Terraform modules.
- `policies/kyverno/` – Kyverno security policies.
- `.github/workflows/` – CI workflows (Checkov, validation, linting).

## Roadmap (high-level)

1. Local k3d cluster on WSL2.
2. Argo CD + GitOps wiring to this repo.
3. Observability stack (Prometheus, Grafana, Loki).
4. OpenSearch + Dashboards.
5. DevSecOps baseline (Kyverno, Trivy, Checkov).
6. Terraform-based OCI deployment (k3s + Cloudflare Tunnel).

