# Demo App 1

The demo app uses a sealed database credential so plaintext never lands in Git.

## Secrets workflow

- Keep `secret-plain.yaml` local only; it is provided as a template for rendering a `Secret`.
- Seal with the controller cert (`tls.crt` from `../sealed-secrets/README.md`):

```bash
kubeseal --cert tls.crt \
  --controller-namespace sealed-secrets \
  --controller-name sealed-secrets \
  --format yaml < secret-plain.yaml > demo-db-encrypted.yaml
```

If the controller key rotates, re-seal the secret using the latest public cert and replace `demo-db-encrypted.yaml`.
