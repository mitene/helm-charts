CloudWatch Agent Chart
======
A Helm chart for cloudwatch-agent

## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm repo add mitene https://mitene.github.io/helm-charts
$ helm install --name my-release mitene/cloudwatch-adapter
```

## Chart Values

| Parameter | Description | Default |
|-----|------|---------|
| regionName            | | |
| clusterName           | | |
| image.repository      | | "amazon/cloudwatch-agent" |
| image.tag             | | "1.245315.0" |
| nameOverride          | | |
| fullnameOverride      | | |
| serviceAccount.create | | true |
| serviceAccount.name   | | |
| podSecurityContext    | | |
| priorityClassName     | | |
