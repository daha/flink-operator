# flink-operator

Current chart version is `0.8.2`

## Chart Values

The following table lists the configurable parameters of the chart and their default values.

| Parameter                              | Description                                                  | Default                      |
| -------------------------------------- | ------------------------------------------------------------ | ---------------------------- |
| `operatorImageName`                    | The name of the operator image                               | `lyft/flinkk8soperator`      |
| `operatorVersion`                      | The version of the operator to install                       | `b5eb19657df91782e51028019e89a7c1badd30d1` |
| `imagePullPolicy`                      | Docker image pull policy                                     | `IfNotPresent`               |
| `flinkJobNamespace`                    | K8s namespace where Flink jobs are to be deployed.           | `default`                    |
| `limitNamespace`                       | Comma separated list of namespaces that the operator is configured to watch. Empty string by default, which indicates all namespaces will be watched. | ""                           |
| `resyncPeriod`                         | The resync period for all watchers                           | "30s"                        |
| `metricsPrefix`                        | Prefix for metrics propagated to Prometheus                  | "flinkk8soperator"           |
| `profilerPort`                         | Profiler port                                                | "10254"                      |
| `ingressUrlFormat`                     | Ingress URL format                                           | ""                           |
| `useKubectlProxy`                      | Whether to use `kubectl` proxy                               | `false`                      |
| `containerNameFormat`                  | Container name format                                        | ""                           |
| `workers`                              | Number of routines to process custom resource                | 4                            |
| `baseBackoffDuration`                  | The base backoff for exponential retries                     | "100ms"                      |
| `maxBackoffDuration`                   | The max backoff for exponential retries                      | "30s"                        |
| `maxErrDuration`                       | The max time to wait on errors                               | "5m"                         |
| `prometheusMetrics.create`             | Whether to create service monitor and service for Prometheus | `true`                       |
| `rbac.create`                          | Whether to create required roles and bindings                | `true`                       |
| `resourcesRequests.memory`             | Requested memory for the operator deployment                 | 1G                           |
| `resourcesRequests.cpu`                | Requested CPU for the operator deployment                    | 0.5                          |
| `resourcesLimits.memory`               | Memory limits for the operator deployment                    | 1G                           |
| `resourcesLimits.cpu`                  | CPU limits for the operator deployment                       | 2                            |
| **Name-related configs**               |                                                              |                              |
| `serviceAccounts.flink.create`         | Create Flink operator ServiceAccount name using fully qualified app name | `true`           |
| `serviceAccounts.flink.name`           | ServiceAccount name for the Flink operator                   | `default` if not created     |
| `serviceAccounts.flinkoperator.create` | Create Flink job ServiceAccount name using release name      | `true`                       |
| `serviceAccounts.flinkoperator.name`   | ServiceAccount name for the Flink jobs                       | `default` if not created     |