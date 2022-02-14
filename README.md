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
mkdir /tmp/thanos-0
chmod o+rwx /tmp/thanos-0/
kubectl apply -f demo-persistence.yaml
helm upgrade -i th .
```

## Set up port-forwarding
```
kubectl port-forward svc/thanos-query-frontend 30000:9090
```