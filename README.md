# LibreTranslate Helm Chart

This Helm chart deploys a LibreTranslate instance on a Kubernetes cluster using the Helm package manager.

## Prerequisites

- Kubernetes 1.12+
- Helm 3.0+

## Setup helm chart repository

```bash
helm repo add libretranslate https://libretranslate.github.io/helm-chart/
helm repo update
helm search repo libretranslate
```

## Installing the Chart

To install the chart with the release name `libretranslate`:

```bash
helm install libretranslate libretranslate --namespace libretranslate --create-namespace
```

This command deploys LibreTranslate on the Kubernetes cluster with the default configuration. The [values.yaml](charts/libretranslate/values.yaml) file lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `libretranslate` deployment:

```bash
helm uninstall libretranslate
kubectl delete namespace libretranslate
```

These commands remove all the Kubernetes components associated with the chart and deletes the release.

## Configuration

See [values.yaml](charts/libretranslate/values.yaml) for the full list of parameters that can be configured. You can specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,

```bash
helm install libretranslate libretranslate --namespace libretranslate --create-namespace --set service.port=8080
```

Alternatively, a YAML file that specifies the values for the parameters can be provided while installing the chart. For example,

```bash
helm install libretranslate libretranslate --namespace libretranslate --create-namespace -f values.yaml
```

## Upgrade

Run the following command to upgrade your LibreTranslate installation. This command will use the Helm chart, apply the custom values from values.yaml, and deploy the upgrade to the `libretranslate` namespace:

```bash
helm upgrade --install libretranslate libretranslate --namespace libretranslate -f values.yaml
```

> **Tip**: You can use the default [values.yaml](charts/libretranslate/values.yaml)

# References
- [https://jmrobles.medium.com/libretranslate-your-own-translation-service-on-kubernetes-b46c3e1af630](https://jmrobles.medium.com/libretranslate-your-own-translation-service-on-kubernetes-b46c3e1af630)
- [https://github.com/LibreTranslate/LibreTranslate](https://github.com/LibreTranslate/LibreTranslate)
