Argo CD Apps Chart
======
A Helm chart for ArgoCD Applications.

Source code can be found [here](https://github.com/mitene/helm-charts/tree/master/charts/argo-cd-apps/)

## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm repo add mitene https://mitene.github.io/helm-charts
$ helm install --name my-release mitene/argo-cd-apps
```

## Example

This chart is especially useful when you define nested ArgoCD applications.

```yaml
# values.yaml
---
applications:
- name: parent
  source:
    repoURL: https://mitene.github.io/helm-charts
    chart: argo-cd-apps
    targetRevision: "0.1.0"  
    helm:
      values: |
        applications:
        - name: child-a
          source:
            repoURL: https://github.com/org/repo
            targetRevision: HEAD
            path: app-a
          destination:
            server: https://kubernetes.default.svc
            namespace: argocd
        - name: child-b
          source:
            repoURL: https://github.com/org/repo
            targetRevision: HEAD
            path: app-b
          destination:
            server: https://kubernetes.default.svc
            namespace: argocd
  destination:
    server: https://kubernetes.default.svc
    namespace: argocd
```

## Chart Values

See https://argoproj.github.io/argo-cd/operator-manual/application.yaml for more details about each parameters.

| Parameter | Description | Default |
|-----|------|---------|
| applications | List of application config | `[]` |
| applications[].name | Application name | |
| applications[].source | Source of the application manifests | |
| applications[].destination | Destination cluster and namespace to deploy the application | |
| applications[].annotations | Application annotations (optional) | |
| applications[].labels | Application labels (optional) | |
| applications[].finalizers | Add a this finalizer ONLY if you want these to cascade delete (optional) | |
| applications[].project | The project the application belongs to (optional) | `"default"` |
| applications[].syncPolicy | Sync policy (optional) | |
| applications[].ignoreDifferences | Ignore differences at the specified json pointers (optional) | |
