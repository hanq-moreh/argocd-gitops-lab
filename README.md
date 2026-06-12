# argocd-gitops-lab

GitOps source of truth for the **Argo CD × vLLM + llm-d** hands-on lab running on
the `mi250-052` node (a throwaway `kind` cluster). Argo CD watches this repo and
reconciles the cluster to match it.

Companion write-ups (concept + per-phase execution logs):
<https://han-oqo.github.io/logs/> → the `argocd-*` pages.

## Layout

```
apps/         # Argo CD Application CRs (live in the `argocd` namespace)
manifests/    # the actual workloads each Application syncs
  phase2-hello/   # trivial Deployment — sync / self-heal / rollback drills
```

This repo is intentionally public so Argo CD can pull it over plain HTTPS with no
credentials. Nothing here is secret — only generic Kubernetes manifests.
