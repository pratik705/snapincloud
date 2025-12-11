# Snapincloud Cluster (Local k3d Testing)

This tree holds everything needed to stand up and iterate on the Snapincloud Kubernetes environment, primarily on a local laptop via k3d. FluxCD reconciles manifests from this repo, and components/apps live in their own folders.

## Layout

```
clusters/snapincloud-cluster
├── demo-app1             # App resources and sealed demo DB secret
├── flux-system           # Flux controllers and sync settings
├── k3d                   # Local cluster config and validation notes
├── kustomization.yaml    # Root kustomize entrypoint
└── sealed-secrets        # Sealed Secrets controller and cert handling
```

## Quick start (local)

1) Create/refresh the local cluster with `k3d` using `k3d/config.yaml`.  
2) Bootstrap Flux from this repo (`flux-system/README.md`).  
3) Verify controllers and nodes are healthy (`k3d/README.md`).  
4) Apply or tweak app manifests (e.g., `demo-app1`) and let Flux reconcile.

## Pointers

- `k3d/README.md` for local cluster creation and basic checks.
- `flux-system/README.md` for installing Flux CLI and bootstrapping sync.
- `sealed-secrets/README.md` for sealing workflow, cert handling, and recovery.
- `demo-app1/README.md` for sealing and managing the demo DB secret.
