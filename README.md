# thanos-example

```
helm repo add bitnami https://charts.bitnami.com/bitnami
export TARGET_VERSION=$(helm search repo bitnami/thanos -o json | jq -r ".[0].version")
helm pull bitnami/thanos --version ${TARGET_VERSION}
tar -xvf thanos-${TARGET_VERSION}.tgz
```