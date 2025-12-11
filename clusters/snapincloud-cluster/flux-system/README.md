# Flux System

Flux installs and reconciles the manifests under `clusters/snapincloud-cluster`. Use the Flux CLI to bootstrap and verify controllers.

## Install CLI

```bash
curl -s https://fluxcd.io/install.sh | sudo bash
```

## Bootstrap this repo

```bash
flux bootstrap github \
  --token-auth \
  --owner=pratik705 \
  --repository=snapincloud \
  --branch=main \
  --path=clusters/snapincloud-cluster \
  --personal
```

## Verify controllers

```bash
kubectl get pods -n flux-system
```

Ensure `helm-controller`, `kustomize-controller`, `notification-controller`, and `source-controller` are all `Running` before relying on reconciliation.
