CloudWatch Prometheus Agent Chart
======
A Helm chart for cloudwatch-prometheus-agent

## Installing the Chart

```console
$ helm repo add mitene https://mitene.github.io/helm-charts
$ helm install --name my-release mitene/cloudwatch-prometheus-agent
```

## Chart Values

| Parameter | Description | Default |
|-----|------|---------|
| config.cwagent    | Contents of cwagentconfig.json | |
| config.prometheus | Contents of prometheus.yaml | |
