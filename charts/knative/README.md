# knative

knative for direktiv

![Version: 0.4.0](https://img.shields.io/badge/Version-0.4.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.1.0](https://img.shields.io/badge/AppVersion-1.1.0-informational?style=flat-square)

## Additional Information

This chart installs Knative for Direktiv. It configures Knative with correct values in Direktiv's context and adds
 support to provide proxy values for corporate proxies.

## Installing the Chart

To install the chart with the release name `knative`:

```console
$ helm repo add direktiv https://charts.direktiv.io
$ helm install knative direktiv/knative
```

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.konghq.com | kong-external(kong) | 2.3.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| autoscaler.grace-period | string | `"120s"` |  |
| autoscaler.max-scale-limit | string | `"5"` |  |
| autoscaler.retention-period | string | `"120s"` |  |
| defaults.max-timeout-seconds | string | `"7200"` | maximum timeout for knative functions in seconds |
| defaults.timeout-seconds | string | `"900"` | default timeout for knative functions in seconds |
| deployment.skip-tag | string | `"kind.local,ko.local,dev.local,localhost:5000,localhost:31212"` |  |
| http_proxy | string | `""` | HTTP proxy information for knative |
| https_proxy | string | `""` | HTTPS proxy information for knative |
| kong-external | object | `{"env":{"plugins":"key-auth,request-transformer","prefix":"/kong_prefix/"},"proxy":{"http":{"servicePort":8080},"tls":{"servicePort":8443}}}` | Kong for Direktiv's UI / API. Based on Kong Helm chart. |
| no_proxy | string | `"localhost,127.0.0.1,10.0.0.0/8,.svc,.cluster.local"` | No proxy information for knative |
