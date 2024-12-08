# [`cert-manager-linode`](https://github.com/ice-bergtech/ice-helm)

> Linode Cert-Manager Webhook

[](https://github.com/ice-bergtech/ice-helm)[![Version: 0.3.0](https://img.shields.io/badge/Version-0.3.0-informational?style=flat-square) ](https://github.com/ice-bergtech/ice-helm)

## Requirements

- [`helm`](https://helm.sh) - Refer to their [docs](https://helm.sh/docs) to get started.

## Usage

**Note:** This chart is a library chart which can not be used directly!

## Values

The following values can be used to adjust the helm chart.

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| certManager.namespace | string | `"cert-manager"` |  |
| certManager.serviceAccountName | string | `"cert-manager"` |  |
| fullnameOverride | string | `""` |  |
| groupName | string | `"acme.cluster.local"` |  |
| image.pullPolicy | string | `"Always"` |  |
| image.repository | string | `"monostream/cert-manager-linode"` |  |
| image.tag | string | `"latest"` |  |
| nameOverride | string | `""` |  |
| resources | object | `{}` |  |
| service.port | int | `443` |  |
| service.type | string | `"ClusterIP"` |  |

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Iceberg Tech |  | <https://ice-bergtech.github.io/> |

## License

[MIT](../LICENSE.md) – © 2024 [Iceberg Tech](https://icebergtech.xyz)