# Aspire-Dashboard Helm

This is a Helm Chart that can be used to install the standalone Dotnet Aspire Dashboard to your Kubernetes-Cluster.

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
  ingress:
    enabled: true
    host: in-aspire.example.com
    annotations:
      cert-manager.io/cluster-issuer: letsencrypt-dns01-issuer
    tls:
      - hosts:
          - in-aspire.example.com
        secretName: in-aspire-tls


``` 

## Documentation
- [All](https://kube-the-home.github.io/kube-the-home/)
- [Contributing](https://kube-the-home.github.io/kube-the-home/Contribution/)
- [Helm Chart](https://kube-the-home.github.io/kube-the-home/Helm-Charts/aspire-dashboard/)
