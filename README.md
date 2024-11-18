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

##

```sh
task chart:template -- <chart>
```

## References

[Pascal Iske](https://pascaliske.dev/): [pascaliske/helm-charts](https://github.com/pascaliske/helm-charts)
