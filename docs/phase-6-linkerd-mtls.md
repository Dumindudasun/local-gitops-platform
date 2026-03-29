## Phase 6 — Service-to-Service Security with Linkerd

This phase adds service-to-service security to the platform using Linkerd.

### What was implemented
- Enabled automatic Linkerd proxy injection for the `demo` namespace
- Meshed `frontend` and `api` workloads
- Verified Linkerd sidecar injection on application pods
- Validated mutual TLS (mTLS) between meshed services
- Captured Linkerd dashboard and traffic evidence

### Security outcome
Traffic between meshed services is automatically encrypted and authenticated with mTLS, providing east-west traffic protection inside the cluster.
# Preflight checks
linkerd check --pre

# Install control plane
linkerd install | kubectl apply -f -
linkerd check

# Install viz extension (metrics + dashboard components)
linkerd viz install | kubectl apply -f -
linkerd check

# Enable proxy injection for your app namespace(s)
kubectl create namespace demo || true
kubectl annotate namespace demo linkerd.io/inject=enabled --overwrite

### Evidence
- `linkerd check --proxy -n demo`
- `linkerd viz edges -n demo deploy`
- Linkerd dashboard screenshots
