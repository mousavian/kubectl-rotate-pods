# kubectl-rotate-pods

Helps you to forcefully restart pods of a deployment in a rolling update manner (depends on your deployment config) for whatever reason you may need. For instance when a ConfigMap or a Secret your pods depend on gets updated or to perform in-memory cache invalidation.


### Installation
TBD


### Usage
```bash
# simple
kubectl rotate-pods -d terrible-deployment


# advanced
kubectl rotate-pods \
  --deployment terrible-deployment \
  --namespace backend \
  --context ctx-prod \
  --reason "for fun"
```
