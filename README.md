# Project Monitoring

**Due to a limitation in Fleet please set the [targetCustomization](https://github.com/dgiebert/fleet-project-monitoring/blob/main/prometheus-federator/fleet.yaml#L25)**

```yaml
apiVersion: fleet.cattle.io/v1alpha1
kind: GitRepo
metadata:
  name: test
  namespace: fleet-default
spec:
  branch: main
  forceSyncGeneration: 16
  insecureSkipTLSVerify: false
  paths:
  - /mimir/
  - /rancher-monitoring-crd/
  - /rancher-monitoring/
  - /prometheus-federator/
  # - /s3gw/
  repo: https://github.com/dgiebert/fleet-project-monitoring.git
  targets:
  - clusterSelector:
      matchExpressions:
      - key: provider.cattle.io
        operator: NotIn
        values:
        - harvester
```

