## Enable kubectl autocompletion

```
https://kubernetes.io/docs/tasks/tools/included/optional-kubectl-configs-bash-linux/#enable-kubectl-autocompletion

echo 'source <(kubectl completion bash)' >>~/.bashrc
echo 'alias k=kubectl' >>~/.bashrc
echo 'complete -F __start_kubectl k' >>~/.bashrc
```

## Use kubectl --dry-run=client to generate Pods or Deployments manifests
```
# Pod
kubectl run pod-name --image=nginx --dry-run=client -oyaml
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: pod-name
  name: pod-name
spec:
  containers:
  - image: nginx
    name: pod-name
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}

# Deployment
kubectl create deploy deploy-name --image=nginx --dry-run=client -oyaml
```

## Use kubectl help mode to generate a right command
```
kubectl -n psp-test create clusterrole --help
Create a ClusterRole.

Examples:
  # Create a ClusterRole named "pod-reader" that allows user to perform "get", "watch" and "list" on pods
  kubectl create clusterrole pod-reader --verb=get,list,watch --resource=pods
  
  Usage:
  kubectl create clusterrole NAME --verb=verb --resource=resource.group [--resource-name=resourcename]
[--dry-run=server|client|none] [options]

```
