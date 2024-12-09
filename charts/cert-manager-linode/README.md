# [`cert-manager-linode`](https://github.com/ice-bergtech/ice-helm)

> Linode Cert-Manager Webhook

[![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ](https://github.com/ice-bergtech/ice-helm)[![Version: 0.4.0](https://img.shields.io/badge/Version-0.4.0-informational?style=flat-square) ](https://github.com/ice-bergtech/ice-helm)

* <https://github.com/ice-bergtech/cert-manager-linode>

## Requirements

- [`helm`](https://helm.sh) - Refer to their [docs](https://helm.sh/docs) to get started.

## Usage

Performs the ACME DNS verification on behalf of cert-manager using the Linode API.
Cert-manager dispatches requests through a dns01 webhook: https://cert-manager.io/docs/configuration/acme/dns01/webhook/

To use, Create or modify a ClusterIssuer to point to the deployment.

```yaml
apiVersion: cert-manager.io/v1
kind: ClusterIssuer
metadata:
  name: letsencrypt-prod
spec:
  acme:
    email: your-email-address
    privateKeySecretRef:
      name: letsencrypt-prod
    server: https://acme-v02.api.letsencrypt.org/directory
    solvers:
      - dns01:
          webhook:
            groupName: acme.cluster.local
            solverName: linode
            config:
              apiKey: <your-api-key>
```

To not have the api key as plaintext, it can also be passed as a secret:
Pass API Key with a Secret:

```yaml
apiVersion: cert-manager.io/v1
kind: ClusterIssuer
metadata:
  name: letsencrypt-prod
spec:
  acme:
    email: your-email-address
    privateKeySecretRef:
      name: letsencrypt-prod
    server: https://acme-v02.api.letsencrypt.org/directory
    solvers:
      - dns01:
          webhook:
            groupName: acme.cluster.local
            solverName: linode
            config:
              apiKeySecretRef:
                name: linode-token
                key: data
---
apiVersion: v1
kind: Secret
metadata:
  name: 'linode-token'
  namespace: cert-manager
stringData:
  data: 'your-api-key'
---
```

## Values

The following values can be used to adjust the helm chart.

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| certManager | object | `{"namespace":"cert-manager","serviceAccountName":"cert-manager"}` | certManager contains config shared with cert-manager deployment |
| certManager.namespace | string | `"cert-manager"` | name of the deployment namespace |
| certManager.serviceAccountName | string | `"cert-manager"` | name of the service account |
| fullnameOverride | string | `""` | Override chart full name |
| groupName | string | `"acme.cluster.local"` | the APIService group name to attach to |
| image.pullPolicy | string | `"Always"` | image pull policy |
| image.repository | string | `"ghcr.io/ice-bergtech/cert-manager-linode"` | repository to pull the image from |
| image.tag | string | `"0.4.0"` | image tag to pull |
| nameOverride | string | `""` | Override chart name  |
| resources | object | `{}` | additional resources to deploy |
| service.port | int | `443` | service port |
| service.type | string | `"ClusterIP"` | service type |

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Iceberg Tech |  | <https://ice-bergtech.github.io/> |

## License

[MIT](../LICENSE.md) – © 2024 [Iceberg Tech](https://icebergtech.xyz)