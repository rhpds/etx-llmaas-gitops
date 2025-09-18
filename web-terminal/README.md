# Web Terminal

Install Web Terminal.

Do not use the `base` directory directly, as you will need to patch the `channel` based on the version of OpenShift you are using, or the version of the operator you want to use.

The current *overlays* available are for the following channels:

* [fast](operator/overlays/fast)

We maintain a custom web terminal image for ETX as well as attach PVC storage to the web-terminal.

Most custom configurations are set in [web-terminal-tooling-template.yaml](web-terminal/chart/templates/web-terminal-tooling-template.yaml) and the image itself.

## Usage

If you have cloned the `gitops-catalog` repository, you can install Web Terminal based on the overlay of your choice by running from the root (`gitops-catalog`) directory.

```
oc apply -k web-terminal/operator/overlays/<channel>
```

Or, without cloning:

```
oc apply -k https://github.com/redhat-cop/gitops-catalog/web-terminal/operator/overlays/<channel>
```

As part of a different overlay in your own GitOps repo:

```
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization
resources:
  - https://github.com/redhat-cop/gitops-catalog/web-terminal/operator/overlays/<channel>?ref=main
```
