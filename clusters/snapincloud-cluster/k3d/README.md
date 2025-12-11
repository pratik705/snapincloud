# k3d Cluster Notes

`config.yaml` defines the local k3d cluster. After starting the cluster, verify connectivity:

```bash
kubectl get node
```

Expect the `k3d-snapincloud-cluster-*` nodes to be `Ready`. Once the cluster is reachable, check Flux controllers as noted in `../flux-system/README.md`.
