@"
# Local GitOps Platform

## Architecture Diagram

This project demonstrates a local Kubernetes GitOps platform built with kind, Argo CD, Argo Rollouts, Linkerd, ingress-nginx, and security controls such as RBAC and NetworkPolicies.



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


```mermaid
flowchart TB
    U[User / Browser]

    subgraph LOCAL[Local Machine]
        K[(kind Kubernetes Cluster)]
    end

    U --> ING

    subgraph CLUSTER[GitOps Platform on Kubernetes]
        ING[Ingress NGINX]

        subgraph MESH[Linkerd Service Mesh]
            FE[Frontend Service]
            API[API Service]
            WORKER[Worker Service]
        end

        DB[(Optional Database / Redis)]

        subgraph GITOPS[GitOps & Delivery]
            ARGOCD[Argo CD]
            APPSET[Argo CD Applications]
            ROLLOUTS[Argo Rollouts]
        end

        subgraph SECURITY[Security Controls]
            RBAC[RBAC Roles / Bindings]
            NETPOL[NetworkPolicies]
            MTLS[mTLS Between Services]
        end
    end

    subgraph GITHUB[GitHub]
        APPREPO[App Source Repo]
        GITOPSREPO[GitOps Manifests Repo]
    end

    APPREPO --> GITOPSREPO
    GITOPSREPO --> ARGOCD
    ARGOCD --> APPSET
    APPSET --> FE
    APPSET --> API
    APPSET --> WORKER
    ROLLOUTS --> FE
    ING --> FE
    FE --> API
    API --> WORKER
    API --> DB
