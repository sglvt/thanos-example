# thanos-example

## Download and examine chart
```
helm repo add bitnami https://charts.bitnami.com/bitnami
export TARGET_VERSION=$(helm search repo bitnami/thanos -o json | jq -r ".[0].version")
helm pull bitnami/thanos --version ${TARGET_VERSION}
tar -xvf thanos-${TARGET_VERSION}.tgz
rm thanos-${TARGET_VERSION}.tgz
```

## Install/upgrade
```
cd thanos
helm upgrade -i th .
```

## Set up port-forwarding
```
kubectl port-forward svc/th-thanos-query-frontend 30000:9090
```