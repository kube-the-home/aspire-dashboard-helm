[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/aspire-dashboard)](https://artifacthub.io/packages/search?repo=aspire-dashboard)
![Release](https://github.com/kube-the-home/aspire-dashboard-helm/actions/workflows/release.yaml/badge.svg)
# Aspire-Dashboard Helm

This is a Helm Chart that can be used to install the standalone Dotnet Aspire Dashboard to your Kubernetes-Cluster.

## Reference
- [dotnet aspire dashboard standalone](https://learn.microsoft.com/en-us/dotnet/aspire/fundamentals/dashboard/standalone?tabs=bash)

## Installation

```sh
helm repo add aspire-dashboard https://kube-the-home.github.io/aspire-dashboard-helm/
helm install aspire-dashboard/aspire-dashboard
```

### Values

```yaml
ui:
  ingress:
    enabled: true
    host: aspire.example.com
    annotations:
      cert-manager.io/cluster-issuer: letsencrypt-dns01-issuer
    tls:
      - hosts:
          - aspire.example.com
        secretName: aspire-tls

otlp:
  clusterip:
    enabled: true

``` 

## Documentation
- [All](https://kube-the-home.github.io/kube-the-home/)
- [Contributing](https://kube-the-home.github.io/kube-the-home/Contribution/)
- [Helm Chart](https://kube-the-home.github.io/kube-the-home/Helm-Charts/aspire-dashboard/)

## Todo

#### Allow Anonymous
Currently this Helm Chart will always set `DOTNET_DASHBOARD_UNSECURED_ALLOW_ANONYMOUS` to true. If this is the case the dashboard can be accessed publicly. The values.yaml has already been adapted with the flag `ui.anonymous` but currently this does not change anything.
But as this Dashboard is more for test than production use cases this should not be that critical.
