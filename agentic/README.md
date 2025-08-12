## setup for [etx-agentic-ai](https://github.com/redhat-ai-services/etx-agentic-ai)

Installs:

- ACM (Policy as code)
- cluster-admin ArgoCD instance in `openshift-policy` namespace
- Hashi Vault instance for app secrets

From the top level directory run:

```bash
kustomize build --enable-helm agentic/ | oc apply -f-
```

You will need to re-run this multiple times until success whilst CRDs install.
