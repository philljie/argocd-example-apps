# vessel-cmtest

Test manifests for validating the customer `argocd-cm` override feature (CR-289260108)
against a live managed Argo CD (Vessel) instance.

- `plain/` — Deployment (replicas target for ignoreDifferences), ConfigMap (customLabels),
  Secret (sensitive annotation masking).
- `kustomize/` — a kustomization using `helmCharts`, which only renders when
  `kustomize build --enable-helm` is in effect. Used to prove that a customer-set
  `kustomize.buildOptions: "--enable-helm"` survives the allowlist filter and is applied.
