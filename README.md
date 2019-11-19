
### :warning: Notice:
This was only an experiment with kubectl plugins.
kubectl itself has `rollout restart` subcommand [[1](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#-em-restart-em-)] in version >1.15 which can be used as follow:

```
kubectl rollout restart deployment/nginx
```



# kubectl-rotate-pods

Helps you to forcefully restart pods of a deployment in a rolling update manner (depends on your deployment config) for whatever reason you may need. For instance when a ConfigMap or a Secret your pods depend on gets updated or to perform in-memory cache invalidation.


### Installation
```bash
curl -sLo kubectl-rotate_pods https://github.com/mousavian/kubectl-rotate-pods/raw/v1.0.0/src/kubectl-rotate_pods && \
  chmod +x kubectl-rotate_pods && mv -i kubectl-rotate_pods /usr/local/bin

# Verify
kubectl rotate-pods --version
```


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
