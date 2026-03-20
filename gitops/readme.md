@"
# Local GitOps Platform

## Phase 1 Completed

This project sets up the foundation for a local GitOps platform on Kubernetes using:

- kind
- ingress-nginx
- Argo CD
- Argo Rollouts
- Linkerd

## Current Status

- Local kind cluster created
- ingress-nginx installed
- Argo CD installed
- Argo Rollouts installed
- Linkerd installed

## Repo Structure

- app-source/     -> application source code
- gitops/         -> Kubernetes manifests and GitOps config
- docs/           -> diagrams and runbooks
- scripts/        -> helper scripts

## Next Phase

- Deploy sample apps with GitOps
- Create Argo CD Applications
- Add progressive delivery with Argo Rollouts
- Mesh workloads with Linkerd
"@ | Out-File -Encoding utf8 README.md
