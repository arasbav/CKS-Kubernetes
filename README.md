## Enable kubectl autocompletion

```
echo 'source <(kubectl completion bash)' >>~/.bashrc
echo 'alias k=kubectl' >>~/.bashrc
echo 'complete -F __start_kubectl k' >>~/.bashrc
```

## Always use kubectl help mode to generate a right command
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
