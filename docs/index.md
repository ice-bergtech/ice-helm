# helm-charts

Helm chart for various services

To use the charts, first add the repository to your Helm configuration:

## Usage

[Helm](https://helm.sh/) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs) to get started. 
Once Helm has been set up correctly, add the repo as follows:

```sh
helm repo add ice-charts https://ice-bergtech.github.io/helm-charts/
```

To add:

```sh
helm install <release> ice-charts/<chart> --values values.yaml
```

To remove:

```sh
helm delete <chart>
```

## Peertube

Commands:

```sh
helm repo add ice-charts https://ice-bergtech.github.io/helm-charts/
helm install peertube ice-charts/peertube --version 0.0.1
```

Minimal config:

```sh

```


## References

[Pascal Iske](https://github.com/pascaliske/helm-charts)
# helm-charts

Helm chart for various services

To use the charts, first add the repository to your Helm configuration:

## Usage

[Helm](https://helm.sh/) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs) to get started. 
Once Helm has been set up correctly, add the repo as follows:

```sh
helm repo add ice-charts https://ice-bergtech.github.io/helm-charts/
```

To add:

```sh
helm install <release> ice-charts/<chart> --values values.yaml
```

To remove:

```sh
helm delete <chart>
```

## Peertube

Commands:

```sh
helm repo add ice-charts https://ice-bergtech.github.io/helm-charts/
helm install peertube ice-charts/peertube --version 0.0.1
```

Minimal config:

```sh

```


## References

[Pascal Iske](https://github.com/pascaliske/helm-charts)
